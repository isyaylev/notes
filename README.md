на всех собеседованиях рассказываю примерно об одном и том же. Что бы как-то упростить процесс - записал один раз на бумаге. Откровений и новаторвств здесь нет, вся эта информация может быть найдена во множестве замечательных книжек.

# Любимая Методология
Я недавно вычитал, что применяемая нами (в многих последних проектах) методология называется DSDM (https://ru.wikipedia.org/wiki/DSDM). 
Отличительные черты: 
* при фиксированном времени и качестве мы играем скоупом,
* чёткая фиксация бизнесового смысла фичи,
* самостоятельность команды в принятии многих продуктовых решений,
* интеграция qa в процесс разработки,
* итеративная и инкрементальная разработка ради быстрой поставки хорошего (не идеального) решения

При этом способ организации работы над задачами может быть любой. Мне больше нравиться итеративный канбан.

Бывает сложный пайплайн разработки: 
* аналитика
* дизайн
* фронт (web)
* бэк (C#)
* бэк (C++)
* БД
* дока разных видов (пользовательская, админская, программерская)
* тестирование ручное
* автотестирование
* инсталлятор
* юридические аспекты

И это всё разные люди. Некоторые этапы можно распараллелить за счёт заранее проработанного _технического решения_ и прописанных в нём заранее _интерфейсов взаимодействия_. Но значительная часть работ - это цепочка последовательных действий. 
Нарезка на итерации по scrum - за итерацию делаем фичу целиком - начинает превращаться в театр абсурда - слишком много перекосов в нагрузке. 
Поэтому мне больше импонирует _итеративный канбан с максимально ранним демо по готовности_ и обязательные спринт-ревью, на которых мы смотрим именно "что делалось". 

Про спринт-ревью - внешним участникам (бизнесу) обычно интересно смотреть на результаты, для них это событие будет не интересно. Для команды и мня как руководителя это очень важное событие - во первых оно мотивационное, во вторых нужно для поддержки плана, в третьих руководителю важно видеть ещё _и процессы и сложности_, а не только достигаемые результаты. 

Онлайн сервис

Ожидания бизнеса к RnD-отделу обычно формулируются так: Разработка - это конвеер по производству фич + безотказная эксплуатация.
Метрики в целом - соответствующие этой формулировке.
Два важных аспекта для управления командой разработки - входят ли тестирование и эксплуатация в ответственности команды разработки. 

Обычно структура RnD-отдела выглядит так
* руководитель\CTO\VP of Engineering,
* отдел product management (аналитики, project manager, product manager, product owner),
* отдел эксплуатации (админы, devops, дежурные), 
* отдел тестирования - функциональные группы тестирования,
* отдел разработки - функциональные группы разработки,
* отдел дизайна
* отдел сбора и интерпретации бизнес-метрик сервиса 

Часто слышал желание иметь heap (неорганизованную кучу) кросс-функциональных специалистов из которых можно собирать рабочие группы для различных фич. Мне не довелось увидеть что бы это работало хоть сколько-нибудь длительное время. Во первых частое переключение людей с функционала на функционал требует больших издержек, увеличивает требования к техническому документированию, требует роли выделенного архитектора, да и плохо сказывается на коллективе. 
Группы разработки и тестирования сами собой получаются закреплёнными каждая за своим функционалом, разумеется, это не отменяет потребности в кросс-компетенциях.


Основные производственные процессы RnD-отдела (касаемые разработки) и метрики для их контроля:
* _Цикл выпуска фичи_ (проектная деятельность) - проработка, реализация, qa, delivery - за каждым словом свой большой набор процессов
* _Обслуживание прода_ - что прилетает из эксплуатации, экстренные изменения от бизнеса, перманентный поиск проблем (безопасности, нагрузки, ошибок алгоритмов и данных и т.п.), 3 линия поддержки
* Предпроектная проработка фичи - аналитическая работа, доказательство реализуемости и целесообразности, ресёрч и эксперименты, проверка гипотез, наколенные прототипы, оценка
* Производства средств производства (точить пилу) - ci\cd, рефакторинг, техдолг, миграция, адаптация новых технологий, перманентный аудит и т.п.
* Цикл разработки перспективных фич - работа над фичами, которые делаются ради эксперимента и вероятно мир их не увидит - разведдеятельность, mvp, прототипы и т.п.
* Процессные наценки - демо, ретро, перманентная прокачка команды



Основная проектная деятельность (поддаётся планированию) и обслуживание прода вместе с экстренными задачами от бизнеса (не поддаётся ни планированию ни прогнозированию) - два конкурирующих процесса, один мешает другому. 
Два приёма борьбы с непрерывным потоком срочных проблем -
1. выделить отдельный ресурс только на "пожары" и 
1. лечить боль бизнеса быстрым "обезболивающим" и тут же стартовать проектную задачу по излечению проблемы

Когда _проблем на проде больше чем ресурсов на их решение_ нужно иметь грамотные приоритеты. В первую очередь сегодня нужно решать задачи, которые завтра высвободят тебе время.

Метрики:
* Цикл выпуска фичи
	* успеваемость "по школьному дневнику" - в сроки выполнили те фичи, которые сами пообещали 
	* развёрнутые за недавнее время на проде фиче не приводят к значимым для бизнеса проблемам
	* время вывода фичи на прод
	* внутренняя - количество возвратов из тестирования\количество критичных багов найденных на этапе qa
	* внутренняя - количество факапов при деплое
	* внутренняя - успеваемость по графику.
* Обслуживание прода 
	* соблюдение установленных сроков на реакцию на внешние раздражители (своеобразный SLA)
	* количество зафиксированных критичных для бизнеса инцидентов (например падение дневной выручки на 10% и более по вине разработки)
	* Предпроектная проработка фичи. все метрики внутренние
	* количество времени затрачиваемого на этот процесс (близость к золотой середине)
	* количество возникших при реализации проблем по причине того что задача была плохо проработана
	* соблюдение при реализации оценок данных при проработке
* Производства средств производства (точить пилу). все метрики внутренние
	* количество времени затрачиваемого на этот процесс (близость к золотой середине)
	* сопровождаемость кода, готовность к его быстрой но без-баговой модификации - формально не оцениваемая, но пожалуй самая важная метрика кода
	* количество действий (строк кода, штук комитов, штук изменённых разных компонентов) необходимое для производства фичи (меньше - лучше)
	* удобство и эффективность работы исполнителей. Соблюдение условия: разработчик локально разрабатывает и отлаживается, тестировщик тестирует на стенде, и всё это условиях максимально приближенных к проду, перенос изменений со стенда на стенд происходит одной кнопкой, затраты времени исполнителем на создание окружения разработки\тестирования сведено к минимуму
	* количество ручного труда по настройке\доводке окружения (меньше - лучше)
* Цикл разработки перспективных фич
	* время производства демо-решения
	* количество ресурсов, отнимаемых у основной проектной деятельности (близость к золотой середине)
	* Процессные наценки. все метрики внутренние
	* эффективность взаимодействия со смежными подразделениями (колво раз, когда взаимодействие могло быть более эффективным)
	* количество ресурсов потраченных на процессы (близость к золотой середине)
	* достижение целей проводимых процессов

# Коробочный продукт со средним релизным циклом (1-3 месяца)
Ожидания бизнеса: в нужный срок получить бетту, а позднее (в срок) готовый релиз в заданном качестве с запланированными фичами.
К сожалению, а может быть к счастью, по ходу разработки фичёвый состав часто меняется, часто по инициативе бизнеса.

Процессы примерно те же самые что в онлайн-сервисе, но отсутствует деплой и прод, усложняются процессы 3ей линии поддержки и перманентного поиска проблем, добавляется релиз (и сопутствующие активности), добавляется документация пользователя и инсталлятор, усложняется предпроектная фаза. Появляются доп. активности тестирования такие как авто-тестирование инсталлятора или авто-тестирование энтерпрайзного приложения (обычно ведь это формы и таблицы, иногда даже на WPF).

Сложности планирования - нагрузка на инсталлятор начинается не раньше второй половины. На документацию - аналогично. Фичи выполненные самыми первыми могут "протухнуть" и может потребоваться их актуализация в конце цикла. Нагрузка на тестирование - сугубо под конец. А разработка (в хорошем случае) в конце релиза вынуждена переключать голову на проблемы следующего релиза, что для разработчиков всегда стресс. 

Сложности эксплуатации - она происходит не у тебя, и данных всегда не хватает. 

Сложности взаимодействия со смежниками - в отличае от онлайн сервиса, тебе сложно перенести релиз из-за того что тебе не удалось подстроить смежников в свой цикл.
Смежники это, например, команда делающая защиту на все продукты компании, или salesforce специалисты через который продукт продают. 

Сложности зависимости фич друг от друга - невозможность (из за юридических проблем, например) релизить одну из фич может обернуться тяжкими последствиями для других фич. Не говоря уже о последствиях для кода. 

Сложность большого скоупа - если релиз слишком большой - бывает тяжело переварить всю аналитику в одной голове. А вернее в голове каждого из: тимлидов, всех сеньёров разработчиков и тестировщиков, аналитиков, юристов, PM-ов и PO-ов, вышестоящих менеджеров.


# Алгоритм работы над регулярной фичей

Под теми кто делает понимается вся команда (pm + разработка + qa), под тем с кем договариваемся - бизнес.
* что нужно? помочь бизнесу сформулировать задачу
* возможно ли? определить целесообразность и выполнимость задачи
* как делать? придумать идею технического решения 
* как делать? предложить как поделить фичу по этапам
* сколько стоит? дать оценку на идею технического решения по этапам
* как проверять? придумать критерий выполненности (приёмки)
* запланировать! выбрать идею решения (вместе с этапами, оценкой и критериями приёмки) и поставить в план
* сделать! сесть и сделать.
* продемонстрировать! верификация - сделали что должны были. демо перед выкаткой. если делать долго - устраивать демо по ходу. 
* проверить! валидация - нет ошибок. начинать проверять нужно на самом деле по готовности кусков. 
* доставить на прод! и доказать что а) ничего не сломалось б) бизнес-цель достигнута. при необходимости - откатить.
* разбор полётов! что было хорошо и как закрепить, что было плохо и как в следующий раз недопустить.


# Критерии успеха выполнения фичи командой

Команда - это и PM\PO и разрабочик и тестировщик и техпис и devops.
_В команде должны найтись исполнители на каждую из ролей_:
* транслятор целей - помогает команде удерживать цель.
* креативный юнит - генерит идеи выхода из любой ситуации.
* визионер - додумывает что нужно делать исходя из цели (не отвлекая бизнес).
* рабочий юнит - основная рабочая сила.
* контроллёр - валидирует и верифицирует решение.
* координатор - координирует команду так, что бы решение срасталось, взаимодействует с внешним миром.
* коммутатор - способствует эффективным коммуникациям внутри команды.
* эксперт - технический или бизнесовый носитель экспертизы.
* владелец артефактов - архитектуры, кода, тестпланов, автотестов, техрешений, доки и т.п. - заботится о развитии не-бизнесовой составляющей проекта

_Нужно выполнение таких вот тезисов_:
* прозрачность и однозначность понимания цели и (возможно) предлагаемого технического решения всеми участниками команды.
* вовлечённость, ответственность, креативность, мотивация, самоактуализация - желательные качества любого участника команды.
* эффективные быстрые (устные) командные коммуникации, позволяющие всей команде пользоваться сильными сторонами каждого из участников.
* достаточный уровень базовой квалификации каждого члена команды и кросс-компетенции.
* наличие надёжного инструментария адекватного техническому решению, и надёжного окружения (среды резработки и тестирования, попросту стендов).

При отсутствии любого из этих пунктов (исполнителей ролей или тезисов) разработка будет плохо-управляемой, плохо-прогнозируемой (и плохо-планируемой) с гарантированно плохим результатом. 

_Владелец артефактов_ - очень важная роль. _Везде выше я писал только об удовлетворении бизнесовых потребностей, а артефакты (например код) - это лишь способ такого удовлетворения_. 
Но есть ещё оборотная сторона медали о которой бизнес всей душой не хочет знать - инструменты, технологии, чистота и сопровождаемость кода, архитектурная надёжность и т.п. 
Их содержание - это очень значимая часть нашей работы в которую мы бизнес посвящаем, но дозированно и по необходимости, и в основном ради того что бы он (бизнес) мог генерить технически-адекватные бизнес-идеи.

Сениор И Техлид обычно выполняют роли креативного юнита, иногда визионера, рабочего юнита, контроллёра, координатора, эксперта, владелец артефактов.
Тимлид - это обычно техлид + иногда транслятор целей, иногда визионет, коммутатор.
PM\PO\Аналитик - это транслятор целей, визионер, контроллёр, бизнесовый эксперт и в некоторых ситуациях креативный юнит.
_Это всё тоже роли, которые могут сочетаться в одном человеке_. Например тестировщика в некоторых ситуациях можно нагружать аналитикой, и наоборот PO в сугубо-техническом проекте может выполнять роль тестировщика.

# Контроль выполнения фичи командой, если ты сам над этой фичей не работаешь
При выполнении фичи командой, важно следить за тем что:
* понимают что делают и зачем это нужно (в смысле цели и в смысле задачи)
* делают что нужно
* им в этом ничего не мешает
* они умеют это делать
* они понимают роадмап - следующие свои шаги и куда они свернут в случае проблем
* имеют достаточную мотивацию для решения _бизнесовой_ задачи

Мне большей частью везло с коллегами - проблемы возникали в основном с первым пунктом. Если грамотно транслировать цели и мало-мальски координировать\направлять их действия - нужную часть работы они выполняли сами. 

Проверять ход работы особо тщательно нужно в начале цикла, обязателен контроль в середине (что бы "довернуть руль" вовремя) и на финальной фазе приёмки и деплоя.

Главный инструмент для мониторинга:
* стендапы, статусники, 5-и минутки
* спринт\ревью
* демо "снятого с монтажного стола сырого материала"
* демо этапов
* ревью кода 
* сторонний аудит
* интервью один на один с участниками команды

# Заказная разработка, подрядные отношения
TBD

# Если проект не терпит
