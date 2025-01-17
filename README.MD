## запрос(ы) для вставки данных минимум о двух книгах в коллекцию books

```javascript
db.books.insertMany(
    [
        {
            title: "Нажми Reset. Как игровая индустрия рушит карьеры и дает второй шанс ",
            description: `Внутри: реальные истории разработчиков Irrational Games, 2K Marin, Visceral и других студий, чье падение стало для сотрудников шоком.
        Вы — игровой разработчик, и ваша мечта — делать игры, в которые будут играть миллионы геймеров. Но реальный мир — не сказка. Студии закрываются, сделанные с любовью проекты отправляются в мусорный бак, а люди остаются без работы.
        `,
            authors: "Шрейер Джейсон"
        },
        {
            title: "Кровь, пот и пиксели. Обратная сторона индустрии видеоигр.",
            description: `Почему Diablo III чуть не стала крупнейшим провалом Blizzard? Как Halo превратилась в стратегию? Через что прошла студия, создавшая Uncharted? Всё, что вы хотели знать о разработке Witcher-3 и Destiny, а также многие другие эксклюзивные истории, рассказанные автору этой книги теми, кто создавал самые популярные игры последнего десятилетия. Узнайте, почему игровая индустрия — это не только престиж и огромные зарплаты, но и проверка на стрессоустойчивость и выносливость, которую проходят далеко не все.`,
            authors: "Шрейер Джейсон"
        }
    ]
)
```

## запрос для поиска полей документов коллекции books по полю title

```javascript
db.books.find({title: /^Кровь/})
```

## запрос для редактирования полей: description и authors коллекции books по _id записи

```javascript
db.books.updateOne(
    { _id: ObjectId("Ид объекта") },
    {
        $set: {
            description: 'Новое описание',
            authors: 'Новый автор'
        },
        $currentDate: { lastModified: true }
    }
)
```