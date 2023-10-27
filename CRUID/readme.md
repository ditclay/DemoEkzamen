Вывод базы данных может в виде таблицы или плитки(часто одна страница под каждый вывод)

За таблицу отвечает Grid, за плитку ListView.

Алгортим:

Для получения данных нужно создать контекст

    public static Sport_AppEntities1 contextSp;

        public static Sport_AppEntities1 GetContext()
        {
            if (contextSp == null)
                contextSp = new Sport_AppEntities1();
            return contextSp;
        }
  Вторая таблица для кнопки
  
        <Grid.RowDefinitions>
            <RowDefinition></RowDefinition>
            <RowDefinition Height="50"></RowDefinition>
        </Grid.RowDefinitions>

 Данные из таблицы DataGrid и названин таблицы из которой берем данные 

 Создаем столбцы:
 
     <DataGrid.Columns>
                <DataGridTextColumn

Структура столбца:
1. заголовок(желательно на русском)
2. указание на столбец таблицы(Binding="{Binding id})
3. ширина(auto)

выводы данных:
1. название DataGrid
2. элементы(ItemsSource)
3. название папки
4. название бд
5. название контекста
6. таблица
7. список
DGusers.ItemsSource = models.Sport_AppEntities1.GetContext().users.ToList();
