## Требования к проекту

Создать приложение «Расписание поездов»
WebAPI-сервер, WPF-клиент

* Данные о пользователе:
  * ID_пользователя  — ключ
  * Логин
  * Пароль
  * ID_pоль (обычный/админ) 
  
* Просмотр списка поездов.
* Просмотр определенного поезда.
* Просмотр расписания поездов.
* Покупка билета.

Дополнительно для администратора
* Добавление, изменение, удаление поездов.
* Добавление, изменение, удаление расписания поездов.

Информация о поезде включает в себя:
  * Номер поезда
  * Место начала маршрута (откуда выезжает поезд)
  * Место завершения маршрута (куда приезжает поезд)

Веб-приложение использует Swagger
  
  ## База данных
  ![бд](https://user-images.githubusercontent.com/101638603/198398047-73e4dec3-a458-4501-bd78-bec8e1921f7a.png)

  Пояснение к расписанию:
   * Дата прибытия поезда на какую-то станцию
   * Дата отправления поезда с какой-то станции
   * Название станции
   * Номер поезда, который совершает маршрут
  

  ## Структура проекта
  
  TrainTimetable.Entities:
   * Migration
   * Models (описание всех сущностей)
   * Context (описание dbContext)
  
  TrainTimetable.Repository:
   * IRepository<T>
   * Repository<T>
 
   Бизнес-логика (TrainTimetable.Service):
   * Abstract (интерфейсы для всех сущностей)
   * Implementation (реализация)
 
   TrainTimetable.WebApi (основное веб-апи)
 
   ## Скрин запуска
 ![скрин](https://github.com/SysuevaAnastasia/TrainTimetableRb/assets/101638603/52884736-bb86-4684-bc8f-9d17f506ed30)


 
