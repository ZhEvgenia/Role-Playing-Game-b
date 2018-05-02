# Role-Playing-Game
Unity Game Project for University

TODO:
1. Настроить анимацию первого моба(ассет уже в проетке(слизняк))
2. Найти ассеты других мобов(У меня пару есть, но для начала нужно с первым разобраться)
3. Написать ИИ для противников(Скорее всего сделаю сам, если вы не изъявите желание сделать самим). Думаю сюда стоит ещё стоит включит обработку событий потери здоровья и т.д.
4. Найти ассет для главного героя(У меня есть пару вариантов, но я ими не очень доволен. Решим коллективно. Предлагайте свои варианты). 
5. Написать скрипт контроля персонажем(Думаю это стоит делать после того, как мы персонажа сделаем). Он должен будет включать перемещение, удары
6. Генерация сцен, т.к. в падлу рисовать и так более интересно(Я сейчас этим занимаюсь)
7. Дописать 2-ю и 3-ю часть класса.(Первую я уже написал, хотя я ещё в ней покапаюсь, может в ней что-то не так. Остальные части советую написать вам, но придётся разобраться в первой части(что желательно даже если класс писать не будете). Если же вы не захотите то доделаю я(Я кстати и хотел бы доделать, но я думаю, что это будет больше всего на баллы влиять))
8. Скрипт следования камеры за персонажем


Замечания: 
1. Реализацию 2-й и 3-й части будет делать когда предыдущие пункты будут выполнены. 
2. Жду ваших предложений, решений, критики и ассетов.



Пример игры, которая будет реализована:

Часть 1

Создать класс «персонаж ролевой игры». Включить в описание класса следующие
поля:
- уникальный числовой идентификатор (*);
- имя персонажа (*);
- состояние (нормальное, ослаблен, болен, отравлен, парализован, мёртв);
- возможность разговаривать в текущий момент времени;
- возможность двигаться в текущий момент времени;
- раса (человек, гном, эльф, орк, гоблин) (*);
- пол (*);
- возраст;
- текущее значение здоровья персонажа (неотрицательная величина);
- максимальное значение для здоровья персонажа;
- количество опыта, набранное персонажем.
Звездочкой помечены поля, не изменяющиеся после создания персонажа.
Реализовать:
- конструктор, задающий значения неизменяемых полей и обеспечивающий
уникальность идентификатора для нового объекта;
- свойства для всех полей (доступ к полям может быть реализован только при
помощи свойств);
- сравнение персонажей по опыту через реализацию интерфейса IComparable;
- если процент здоровья персонажа (отношение текущего здоровья персонажа
к максимальному количеству здоровья) становится менее 10, персонаж
автоматически переходит из состояния «здоров» в состояние «ослаблен».
Если процент здоровья персонажа становится большим или равным 10,
персонаж автоматически переходит из состояния «ослаблен» в состояние
«здоров». Если текущее значение здоровья равно 0, персонаж автоматически
переходит из любого состояния в состояние «мертв».
- вывод информации о персонаже в строку (через метод ToString).
Создать класс-потомок «персонаж, владеющий магией». Дополнительно включить в
описание этого класса следующие поля:
- текущее значение магической энергии (маны) (неотрицательная величина);
- максимальное значение маны.
Мана расходуется на произнесение заклинаний. Если текущее значение маны
меньше того количества, которое требуется для произнесения какого-либо
заклинания, заклинание не может быть произнесено, а количество маны остается
неизменным.
Некоторые заклинания обладают силой, причем сила заклинания задается
волшебником в момент его произнесения. Расход маны в этом случае
пропорционален силе заклинания. Сила заклинания ограничивается текущим
значением маны.
Реализовать заклинание «добавление здоровья». Суть этого заклинания – увеличить
текущее значение здоровья какого-либо персонажа (в том числе и себя) до
максимального или до предела, задаваемого текущим значением маны. На единицу
добавленного здоровья расходуется две единицы маны.

Часть 2
Создать интерфейс «волшебство», включающий перегруженные методы
«выполнить волшебное воздействие». В качестве параметра указать персонажа
ролевой игры, на которого может быть направлено воздействие, а также силу
воздействия. Оба параметра могут отсутствовать.
Создать абстрактный класс «заклинание», реализующий указанный интерфейс.
Включить в описание класса следующие поля:
- минимальное значение маны, требуемое для выполнения заклинания (может
быть равно 0);
- наличие вербальной компоненты (заклинание нужно произносить);
- наличие моторной компоненты (необходимо выполнять какие-то движения);
Реализовать классы заклинаний:
1) «Добавить здоровье». Суть этого заклинания – увеличить текущее значение
здоровья какого-либо персонажа на заданную величину или до предела,
задаваемого текущим значением маны. На единицу добавленного здоровья
расходуется две единицы маны.
2) «Вылечить». Суть этого заклинания – перевести какого-либо персонажа из
состояния «болен» в состояние «здоров или ослаблен». Текущая величина
здоровья не изменяется. Заклинание требует 20 единиц маны.
3) «Противоядие». Суть этого заклинания – перевести какого-либо персонажа
из состояния «отравлен» в состояние «здоров или ослаблен». Текущая
величина здоровья не изменяется. Заклинание требует 30 единиц маны.
4) «Оживить». Суть этого заклинания – перевести какого-либо персонажа из
состояния «мертв» в состояние «здоров или ослаблен». Текущая величина
здоровья становится равной 1. Заклинание требует 150 единиц маны.
5) «Броня». Персонаж, на которого обращено заклинание, становится
неуязвимым в течение некоторого промежутка времени, определяемого
силой заклинания. Заклинание требует 50 единиц маны на единицу времени.
6) «Отомри!» Суть этого заклинания – перевести какого-либо персонажа из
состояния «парализован» в состояние «здоров или ослаблен». Текущая
величина здоровья становится равной 1. Заклинание требует 85 единиц маны.
Создать абстрактный класс «артефакт», реализующий указанный интерфейс.
Включить в описание класса следующие поля:
- мощность артефакта (величина, аналогичная количеству маны у персонажа,
владеющего магией) – может быть равен 0;
- признак возобновляемости артефакта.
Реализовать классы артефактов:
1) Бутылка с живой водой – увеличивает здоровье персонажа. Здоровье
персонажа не может превысить максимальную величину, но артефакт
используется полностью! Могут быть малые, средние и большие бутылки,
увеличивающие здоровье соответственно на 10, 25 и 50 единиц. Не
возобновляемый.
2) Бутылка с мертвой водой – увеличивает ману персонажа, владеющего
магией. Мана не может превысить максимальную величину, но артефакт
используется полностью! Могут быть малые, средние и большие бутылки
увеличивающие ману соответственно на 10, 25 и 50 единиц. Не
возобновляемый.
3) Посох «Молния». Уменьшает количество здоровья персонажа, против
которого был применен этот артефакт, на величину, заданную мощностью
(мощность задаётся персонажем при использовании артефакта). Мощность

посоха уменьшается на эту величину. Возобновляемый, но непригоден для
использования, если его мощность равна нулю.
4) Декокт из лягушачьих лапок. Переводит какого-либо персонажа из состояния
«отравлен» в состояние «здоров или ослаблен». Текущая величина здоровья
не изменяется. Не возобновляемый.
5) Ядовитая слюна (накладка на зубы, через которую надо плевать). Переводит
какого-либо персонажа из состояния «здоров или ослаблен» в состояние
«отравлен». Текущая величина здоровья уменьшается на величину,
задаваемую мощностью артефакта. При применении этого артефакта
персонаж, против которого он был применен, может умереть!
Возобновляемый.
6) Глаз василиска. Переводит любого не мёртвого персонажа в состояние
«парализован». Не возобновляемый.
Реализовать лечение, которое было описано в части 1, через произнесение
соответствующего заклинания и использование артефакта.

Часть 3
Дополнить созданные в частях 1 и 2 классы следующими возможностями:
1) У каждого персонажа игры есть мешок (inventory), куда можно помещать
различные артефакты (количество артефактов одного вида неограниченно) и
использовать их. Если артефакт не является возобновляемым, он исчезает из
мешка. Можно использовать только те артефакты, которые имеются в мешке.
2) Персонаж, владеющий магией, может изучить различные заклинания. После
изучения заклинания могут быть реализованы. Можно реализовывать только
изученные заклинания.
Реализовать методы:
«Подобрать артефакт и пополнить мешок»
«Выбросить артефакт из мешка»
«Передать артефакт другому персонажу»
«Использовать артефакт»
«Выучить заклинание»
«Забыть заклинание»
«Произнести заклинание»
