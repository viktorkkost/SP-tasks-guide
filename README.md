**Съдържание**

[1. Не знам какво да правя](#h1)

[2. Не знам какво е автомат](#h2)

[3. Не знам как се синтезира/кодира автомат](#h3)

[4. Не знам какви са дефинициите на числови константи, които броим](#h4)

[5. Не знам как се синтезира автомата за тази задача](#h5)

[6. Не знам как се кодира автомата за тази задача](#h6)

# 1. Не знам какво да правя<a name="h1"></a>
Задачата е да се построи схема на автомат и по нея да се напише код на C. Автоматът трябва да брои числовите константи от текстов файл. "873" и "12.1f" са примери за числови константи. В текстовия файл има множество такива разделени с whitespaces, вероятно има и подвеждащи числа.

# 2. Не знам какво е автомат<a name="h2"></a>
Автоматът описва някаква логика за правене на изчисления. Обикновено автомат се представя чрез схема. По тази схема може да се напише код, който "движи" автомата и съответно прави изчисленията. Потърсете някое видео за нагледно обяснение, ключовите думи са "state machine" и "finite state automata". Без това няма как да се оправите.

# 3. Не знам как се синтезира/кодира автомат<a name="h3"></a>
Ако знаете какво е автомат би трябвало да можете и да синтезирате нов автомат, който описва някоя елементарна система, напр. за някой прост regex от рода на "ab*". Кодирането също е лесно, отново се насочете към някое видео на език, който разбирате. В цикъл имате switch/case върху state-а и във всеки case правите проверка какъв е следващия символ, за да направите преход към нов state. Препоръчвам да правите схемите на компютър, защото иначе е много драскане. Пример за такъв сайт:
https://matthewscholefield.github.io/fsm/

# 4. Не знам какви са дефинициите на числови константи, които броим<a name="h4"></a>
Формалните дефиниции са описани по-долу. В това repo може да намерите тестов файл [tests.txt](tests.txt), който съдържа ВАЛИДНИ и НЕВАЛИДНИ примери за константи. Може да го използвате за информация или директно за тестване на автомата чрез код.

Част от правилата са описани на примери на тези две страници:

https://learn.microsoft.com/en-us/cpp/c-language/c-integer-constants

https://learn.microsoft.com/en-us/cpp/c-language/c-floating-point-constants

А това е останалата част от правила:

1. Константите не се броят ако участват в израз. Например ако автомата
срещне "5+7" не брои нито 5, нито 7 като константа.
2. Константите са валидни САМО ако са обградени от whitespaces, тоест
разстояния, tab, EOF или нови редове. Тоест "7;" не е константа.
3. Ако има знак минус точно преди octal число, hex число или какъвто и да е
int с unsigned suffix, това число НЕ се брои. Само реални числа или signed десетични може да са отрицателни.
4. Няма нужда да включвате 64-bit-integer-suffix в автомата.

===== За следващите дефиниции не съм 100% сигурен. Попитах преподавателя и още не съм получил отговор.

1. Положителните константи може да започват с плюс. Тоест "+58" е
валидно.
2. По дефинициите всяко целочислено число, което започва с 0, се брои
за осмично. Тоест самотна отрицателна нула ("-0") също е осмична и
следователно невалидна.

# 5. Не знам как се синтезира автомата за тази задача<a name="h5"></a>
Запознайте се с т.2 и т.3, както и с дефинициите. След това започвате да работите по някоя дефиниция на метода проба-грешка и най-вероятно ще се ориентирате.
Няколко съвета:
- Не е нужно да правите един автомат за цялата задача. Може да направите напр. един за цели числа и един за реални и програмата ви да минава и през двата. Може и да ги разделите на отделни страници.
- Може автомата да чете целия файл символ по символ или само отделни "думи", но това зависи от т.6 и как вие мислите да го реализирате.
- Няма нужда да правите преходи към fail state. Така си спеститявате по една стрелка от всеки state и правите автомата по-четим.
- Кръщавайте си стейтовете като кратки променливи, за да се ориентирате по-лесно в автомата.
- Не се мъчете да правите всичко от първия път. Направете част от него и го надграждайте постепенно.

# 6. Не знам как се кодира автомата за тази задача<a name="h6"></a>
Запознайте се с т.3 и с дефинициите, за да имате представа как ще направите кода. Както беше споменато в т.5, имате варианти да направите няколко по-малки автомата, съответно може да ги изнесете в отделни функции. За броене, край на програмата и т.н. функциите може да връщат някакви кодове, а може да проектирате цялата система като друг автомат. Това е най-лесната част от задачата и имате най-много свобода в нея. В интернет има повече от достатъчно ресурси как се пише код по автомат, като цяло кода е сравнително дълъг но елементарен. Какви ще бъдат по-специфичните детайли е ваш избор.
