# Products
Основное задание 
1. Создать объект, представляющий инвормацию о продукте:
  1. Lable=Product Table
  2. Object Name=ProductTable
2. Создать поля для объектп Product Table.
  1.Поля для хранения цены
    1.Type=Currency
    2.Lable=Price
    3.Field Name=Price
  2. Поля для хранения количества товаров
    1.Type=Number
    2.Lable=Amount
    3.Field Name=Amount
  3. Поля для хранения типа товара 
    1.Type=Picklist
    2.Lable=ProductType
    3.Field Name=ProductType
  4. Поля для хранения даты выпуска
    1.Type=Date
    2.Lable=ReleaseDate
    3.Field Name=ReleaseDate
  5. Поле для хранения даты добавления товара
    1.Type=DateTime
    2.Lable=AddedDate
    3.Field Name=AddedDate
  6. Поле определяющее доступен ли товар
    1.Type=Checkbox
    2.Lable=Available
    3.Field Name=Available
3. Создать триггер для нашего объекта и хелпер класс для триггера. Вся логика обработки должна быть написана в хеллпере.
  1.Trigger Name= ProductTableTrigger
  2.Helper Class Name= ProductTableTriggerHelper
  3.Events=befor insert/update
  4.Поле Available должно автоматически заполняться при создании или обновлении товара.
    1. Если Amount>0 выставляем в true
    2. Если Amount<=0 выставляем в false
  5. Поле AddedDate должно автоматически заполняться временем создания при создании продукта
    1. Используйте класс Datetime чтобы заполнять это поле
4. Создать 3 Validation Rule, которые будут контролировать правильность заполнения полей Amount, Price, Release Date
  1. 1-й Validation Rule, Name=VakidateAmount
    1. Если Amount<0, нужно показать сообщение об ошибке
  2. 2-й Validation Rule
    1. Если Price<0, нужно показать сообщение об ошибке
  3. 3-й Validation Rule
    1. Если поле Realease Date позднее сегодняшней даты, нужно показать сообщение об ошибке
5. Создать Aura Component -- ProductTableApp.
6. Создать Aura Component -- ProductTableCmp. Компонента должна отображать список товаров в виде таблицы.
  1. Компонент должен использоваться в ProductTableApp
  2. В таблице обязательно должны быть колонки, расположенные в следующем порядке (имена колонок должны совпадать с теми, что указаны ниже):
    1. Name
    2. Amount
    3. Price
    4. Product Type
    5. Realese Date
    6. Available
  3.Данные в таблице должны быть отсортированы по полю AddedDate так, чтобы недавно добавленные продукты были вверху списка.
7. Создать Apex Class -- ProductTableCmpController. Класс будет использоваьбся в качестве контроллера для нашего Aura Component.
  1. Класс должен обязательно содержать метод getProducts. Метод будет возвращать список продуктов с нужными для отображениия полями.
8. Расширить функционал компоненты так, чтобы были следующие возможности:
  1. Создавать товар
    1. Для этого обязательно надо добавить в контроллер метод insertNewProductTable
  2. Удалять товар из списка
    1. Для этого обязательно надо добавить в контроллер метод deleteNewProductTable
  3. Редактировать товар из списка
    1. Для этого обязательно надо добавить в контроллер метод updateNewProductTable
  4. Искать товар по части имени
    1. Расширить метод getProducts так, чтобы он возварщал либо все продукты, либо те, которые подходят по имени
9. Создать для тестирования написанного кода. Общее покрытие должно быть не менее 75%
  1. Name=TestProductTableApplcation
  2. Класс должен покрывать тестами следующее классы:
    1. ProductTableTrigger
    2. ProductTableCmpController
    
Задание для дополнительных баллов
Добавить к компоненте возможности сортировки списка товаров по полям:
Name
Added Date
Release Date
Price
Расширить возможности поиска
  Поиск должен осуществляться по дате добавления
  Для поиска по обоим полям должно использоваться одно и то же поле ввода
Добавить плагинацию для навигации по списку товаров.

  
