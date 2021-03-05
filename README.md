# Angular-Interview-Questions

Constructor - специальный метод, служащий для создания и инициализации объектов, созданных с использованием class. <br><br>

Основные составляющие ангуляра ?
<br>
- Directive
- Module
- Service
- Component
- Guard
- Pipe

Что такое интерполяция в Angular? <br>
Разметка интерполяции с внедренными выражениями используется в Angular для присвоение данных текстовым нодам и значения аттрибутов. Например: <br>
`<a href="img/{{username}}.jpg">Hello {{username}}!</a>` <br><br>

Что такое Data Binding и какие проблемы связанные с ним вы знаете?
- Angular поддерживает одностороннюю и двустороннюю Data Binding. Это механизм координации частей шаблона с частями компонента.
Добавление специальной разметки сообщает Angular как соединять обе стороны. Следующая диаграмма показывает четыре формы привязки данных.
Односторонние:
От компонента к DOM с привязкой значения: {{hero.name}}
От компонента к DOM с привязкой свойства и присвоением значения: [hero]="selectedHero"
От DOM к компоненту с привязкой на ивент: (click)="selectHero(hero)"

Двусторонняя в основном используется в template-driven forms, сочетает в себе параметр и ивент. Вот пример, использующий привязку с директивой ngModel.
`<input [(ngModel)]="hero.name">`

Здесь значение попадает в input из компонента, как при привязке значения, но при изменении юзером значения новое передается в компонент и переопределяется
<br><br>

Что такое promise ? <br>
Promise - объект используется для отложенных и асинхронных вычислений.

- Основные принципы ООП
  Инкапсуляция
  Абстракция
  Полиморфизм
  Наследование
  <br><br>
 
Что такое Directive ? Module ? Service ? Component ? Pipe ? Guard ? <br>

- Angular модуль - это класс с декоратором @NgModule(), который служит изолирующей логической объединяющей структурой для компонентов, директив, фильтров и сервисов. Все перечисленные сущности определяются и конфигурируются с помощью @NgModule(). <br>
- Guards позволяют ограничить навигацию по определенным маршрутам. <br>
- Сервис это класс с узкой, четко определенной целью. Это может быть значение, функция, запрос, etc. Главное в них то, что они повторно используются, отделяя чистую функциональность компонента.<br><br>
- Пайп преобразует отображение значений в шаблоне, к примеру отображение дат в разных локалях или изменяют в отображении регистр строк. <br><br>

Какие бывают директивы ? Что они делают ? <br>
- Структурные директивы влияют на DOM и могут добавлять/удалять элементы (ng-template, NgIf, NgFor, NgSwitch, etc) <br>
- Атрибутные директивы меняют внешний вид или поведение элементов, компонентов или других директив (NgStyle, NgClass, etc). <br>

Что такое декоратор и какие виды декораторов вы знаете? <br>
Декоратор - способ добавления метаданных к объявлению класса. Это специальный вид объявления, который может быть присоединен к объявлению класса, методу, методу доступа, свойству или параметру. <br>
Декораторы используют форму @expression, где expression - функция, которая будет вызываться во время выполнения с информацией о декорированном объявлении.

Чтобы написать собственный декоратор, нам нужно сделать его factory и определить тип: <br>
- ClassDecorator
- PropertyDecorator
- MethodDecorator
- ParameterDecorator
<br><br>

Работали ли вы с NGRX ?

Какой флоу ? (Action -> effect -> запрос на сервер -> reducer)

Что такое Singleton Service и с какой целью его используют в Angular ?

Как сделать сервис Singleton ?

Что такое Observable ?
- Observable — это набюдатель, который подписывается и реагирует на все события до момента отписки. <br><br>

Что такое Dependency Injection? <br>
Это важный паттерн шаблон проектирования приложений. В Angular внедрение зависимостей реализовано из-под капота. <br>
Зависимости - это сервисы или объекты, которые нужны классу для выполнения своих функций. DI -позволяет запрашивать зависимости от внешних источников.

В чём разница между Observable и Promise ?

Расскажите про lazy load и как оно работает ?

Расскажите про OnPush Change Detection Strategy

Что такое ViewEncapsulation ?

Что такое Change Detection, как работает Change Detection Mechanism?
<br>
- Change Detection - процесс синхронизации модели с представлением. В Angular поток информации однонаправленный, даже при использовании ngModel для реализации двустороннего связывания, которая является синтаксическим сахаром поверх однонаправленного потока.
- Change Detection Mechanism <br>
Change Detection Mechanism - продвигается только вперед и никогда не оглядывается назад, начиная с корневого (рут) компонента до последнего. В этом и есть смысл одностороннего потока данных. Архитектура Angular приложения очень проста — дерево компонентов. Каждый компонент указывает на дочерний, но дочерний не указывает на родительский. Односторонний поток устраняет необходимость $digest цикла.
<br><br>

Какие существуют стратегии обнаружения изменений? <br>
- Всего есть две стратегии - Default и OnPush. Если все компоненты используют первую стратегию, то Zone проверяет все дерево независимо от того, где произошло изменение. Чтобы сообщить Angular, что мы будем соблюдать условия повышения производительности нужно использовать стратегию обнаружения изменений OnPush. Это сообщит Angular, что наш компонент зависит только от входных данных и любой объект, который передается ему должен считаться immutable. Это все построено на принципе автомата Мили, где текущее состояние зависит только от входных значений. <br><br>