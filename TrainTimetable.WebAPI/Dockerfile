FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /src
COPY ["TrainTimetable.WebAPI/TrainTimetable.WebAPI.csproj", "TrainTimetable.WebAPI/"]
COPY ["TrainTimetable.Entities/TrainTimetable.Entities.csproj", "TrainTimetable.Entities/"]
COPY ["TrainTimetable.Repository/TrainTimetable.Repository.csproj", "TrainTimetable.Repository/"]
COPY ["TrainTimetable.Services/TrainTimetable.Services.csproj", "TrainTimetable.Services/"]
RUN dotnet restore "TrainTimetable.WebAPI/TrainTimetable.WebAPI.csproj"
COPY . .
WORKDIR "/src/TrainTimetable.WebAPI"
RUN dotnet build "TrainTimetable.WebAPI.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "TrainTimetable.WebAPI.csproj" -c Release -o /app/publish /p:UseAppHost=false

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "TrainTimetable.WebAPI.dll"]