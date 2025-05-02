# Практическая работа №1  
## Выполнил: Клишенков Артём Игоревич, БСБО-06-23  
Был создан проект "Lesson1", который содержит в себе несколько модулей. Каждый модуль отведён на отдельное практическое задание в рамках данного проекта.  
Для тестирования приложения использовался эмулятор Android устройства Pixel 9 Api 35:
  
![](https://github.com/alinaklishenkova/Lesson1/blob/master/screenshots/5350285042196281890.jpg)  

После создания эмулятора в менеджере виртуальных устройств созданное устройство при запуске отображается следующим образом:  

![](https://github.com/alinaklishenkova/Lesson1/blob/master/screenshots/5350285042196281899.jpg)

Далее был выбран модуль "layouttype" в выпадающем списке, запущенный эмулятор и нажата кнопка "Run":  

![](https://github.com/alinaklishenkova/Lesson1/blob/master/screenshots/5350285042196281901.jpg)

После успешной сборки приложение отобразило на экране эмулятора:

![](https://github.com/alinaklishenkova/Lesson1/blob/master/screenshots/5348541332718742945.jpg)  

В созданной директории "layouttype" в файл "activity_main.xml" был добавлен на экран элемент "TextView2" и изменен отображаемый текст на "Привет, мир!":

![](https://github.com/alinaklishenkova/Lesson1/blob/master/screenshots/5366412253550734516.jpg)  

В этой же директории был создан новый "Layout resource file" с именем "linear_layout.xml". Был создан экран с шестью кнопками с помощью "LinearLayout", а именно было вложено в один "LinearLayout" два других и внутри размещены элементы "button". Значение ориентации корневого "LinearLayout" устанавливалось как "вертикальное", а двух вложенных макетов – "горизонтальное":

![](https://github.com/alinaklishenkova/Lesson1/blob/master/screenshots/5366412253550734611.jpg)

Следующим шагом в этой же директории был создан файл разметки "table_layout.xml" с корневым элементом "TableLayout" и добавлен в корневой элемент три "TableRow"-строки. У каждого вложенного элемента назначен атрибут "layout_weight", определяющий весовой коэффициент представления. В первую строку "TableRow" было добавлено две кнопки и "textView", во вторую - одна кнопка и "checkBox", а в третью - две кнопки и "imageButton" с изображением стрелки:
 
![](https://github.com/alinaklishenkova/Lesson1/blob/master/screenshots/5366412253550734654.jpg)

В директории "layouttype" был создан файл "constraint_layout.xml". В нем добавлены три элемента "textView" с соответствующими надписями, также задана связь между этими элементами:

![](https://github.com/alinaklishenkova/Lesson1/blob/master/screenshots/5366412253550734695.jpg)

Далее был создан новый модуль "control_lesson1". Был создан экран авторизации с использованием изученных элементов:

![](https://github.com/alinaklishenkova/Lesson1/blob/master/screenshots/5366412253550734967.jpg)

При запуске модуля "control_lesson1" на эмуляторе отображается следующий экран приложения:

![](https://github.com/alinaklishenkova/Lesson1/blob/master/screenshots/5366412253550734991.jpg)

Далее был создан новый модуль "number_five" и в нем создан layout-файл "activity_second.xml". В созданном layout-файле добавлен на экран элемент "PlainText" с текстом "New life for mirea activity!" и 6 кнопок button:

![](https://github.com/alinaklishenkova/Lesson1/blob/master/screenshots/5368796218098053984.jpg)

Для того, чтобы activity использовало новый файл "activity_second.xml", а не "activity_main.xml", в "MainActivity.java" изменен аргумент метода setContentView на `R.layout.activity_second`:

```
public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        EdgeToEdge.enable(this);
        setContentView(R.layout.activity_second);
        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.editTextText), (v, insets) -> {
            Insets systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars());
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom);
            return insets;
        });
    }
}
```
Далее было вызвано контекстное меню у директории "res" и выбраны команды "New | Layout Resource File". Имя файла было записано как "activity_main". В списке "Available qualifiers" расположен элемент "Orientation", который был перенесен в правую часть "Chosen qualifiers": с помощью кнопки с двумя стрелками. По умолчанию значение поля "Directory name" изменилось на "layout-port". Т.к. основной целью является поддержка горизонтальной ориентации в выпадающем списке "Screen orientation" выбран "Landscape":

![](https://github.com/alinaklishenkova/Lesson1/blob/master/screenshots/5368796218098054473.jpg)

Таким же способом был добавлен файл "activity_second.xml" (land):

![](https://github.com/alinaklishenkova/Lesson1/blob/master/screenshots/5368796218098054472.jpg)

В файле "activity_second.xml" (land) изменено расположение кнопок так, чтобы все из них были отображены при горизонтальной ориентации:

![](https://github.com/alinaklishenkova/Lesson1/blob/master/screenshots/5368796218098054525.jpg)

При запуске модуля "number_five" и выбранного эмулятора при горизонтальной ориентации отображается следующий экран:

![](https://github.com/alinaklishenkova/Lesson1/blob/master/screenshots/5371048017911738336.jpg)

Далее в модуле "control_lesson1" также добавлена горизонтальная разметка:

![](https://github.com/alinaklishenkova/Lesson1/blob/master/screenshots/5371048017911738350.jpg)

При запуске данного модуля и выбранного эмулятора при горизонтальной ориентации мы видим следующий экран:

![](https://github.com/alinaklishenkova/Lesson1/blob/master/screenshots/5371048017911738354.jpg)

Далее был создан новый модуль "number_six2". В класс "MainActivity.java" после метода связывания файла разметки "setContentView" добавлено создание объекта "TextView":
```
TextView myTextView = (TextView) findViewById(R.id.textViewStudent);
```
После успешной инициализации применен метод setText к "myTextView":
```
myTextView.setText("New text in MIREA");
```
Далее мы скомпилировали и запустили проект для отображения нового текста в поле:

![](https://github.com/alinaklishenkova/Lesson1/blob/master/screenshots/5377536399235999654.jpg)

В файл разметки добавили кнопку "Button" и установить идентификатор "id=@+id/button", а в классе "MainActivity" создали переменную типа "Button" и вызвали метод "setText" с аргументом измение значения текста кнопки:

```
Button button = findViewById(R.id.button);
button.setText("MireaButton");
```
Для элемента "CheckBox" также установили идентификатор "id=@+id/check_box". Для установки метки используется метод "setChecked", меняющий параметр на значение "Checked":
```
CheckBox checkBox = findViewById(R.id.check_box);
checkBox.setChecked(true);
```
При запуске данного модуля на экране эмулятора отображается:

![](https://github.com/alinaklishenkova/Lesson1/blob/master/screenshots/5377536399235999675.jpg)

Следующим шагом был создан новый модуль "ButtonClicker". В разметке "activity_main.xml" дбавлены "TextView" с идентификатором "id="@+id/tvOut" и две кнопки: "WhoAmI" (id="@+id/btnWhoAmI") и "ItIsNotMe" (id="@+id/btnItIsNotMe"). Также был добавлен элемент "CheckBox". Внешний вид экрана представляет себя:

![](https://github.com/alinaklishenkova/Lesson1/blob/master/screenshots/5377536399235999814.jpg) 

Данный экран связан с классом "MainActivity.java". Объявление объектов вынесены за пределы метода "onCreate" и сделаны глобальными переменными. В методе "onCreate" производится инициализация объектов с помощью метода "findViewById":
```
public class MainActivity extends AppCompatActivity {
    private TextView tvOut;
    private Button btnWhoAmI;
    private Button btnItIsNotMe ;
    private CheckBox checkBox;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        tvOut = findViewById(R.id.tvOut);
        btnWhoAmI = findViewById(R.id.btnWhoAmI);
        btnItIsNotMe = findViewById(R.id.btnItIsNotMe);
        checkBox = findViewById(R.id.checkBox);
}
```
Реализация нажатия на кнопку "WHO AM I?":
```
View.OnClickListener oclBtnWhoAmI = new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                tvOut.setText("Мой номер по списку № 14");
                checkBox.setChecked(!checkBox.isChecked());
            }
        };
        btnWhoAmI.setOnClickListener(oclBtnWhoAmI);
```
Реализация нажатия на кнопку "IT'S NOT ME" вторым способом, а также добавление элемента "CheckBox", изменяющий свое состояние при нажатии на кнопки вместе "TextView":
```
public void onMyButtonClick(View view) {
        tvOut.setText("Это не я сделал");
        Toast.makeText(this, "Ещё один способ!", Toast.LENGTH_SHORT).show();
        checkBox.setChecked(!checkBox.isChecked());
    }
```
При запуске данного модуля и нажатия на экране эмулятора на кнопку "WHO AM I?" выводится текст: "Мой номер по списку № 14":

![](https://github.com/alinaklishenkova/Lesson1/blob/master/screenshots/5377536399235999815%20(1).jpg)

При запуске данного модуля и нажатия на экране эмулятора на кнопку "IT'S NOT ME" выводится текст: "Это не я сделал":

![](https://github.com/alinaklishenkova/Lesson1/blob/master/screenshots/5377536399235999818.jpg)
