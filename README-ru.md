<div id="content" class="pages">
  <h2>Руководство: Пишем код пригодный для тестирования | поддающийся тестированию</h2>
  <div class="entry">
    <p
      style="
        margin: 0.14in 0in 0in;
        background: transparent none repeat scroll 0% 50%;
      "
      align="left">
      To keep our code at Google in the best possible shape we provided our
      software engineers with these constant reminders. Now, we are happy to
      share them with the world.
    </p>
    <p
      style="
        margin: 0.14in 0in 0in;
        background: transparent none repeat scroll 0% 50%;
        background-color:#FCC;
      "
      align="left">
      Чтобы поддерживать наш код в Google в наилучшем виде, мы предоставили нашим
      программистам эти неизменные напоминаниями. Теперь мы рады
      поделиться ими со всем миром.
    </p>
    <p
      style="
        margin: 0.14in 0in 0in;
        background: transparent none repeat scroll 0% 50%;
      "
      align="left"></p>
    <p
      style="
        margin: 0.14in 0in 0in;
        background: transparent none repeat scroll 0% 50%;
      "
      align="left">
      Many thanks to these folks for inspiration and hours of hard work getting
      this guide done:
    </p>
    <p
      style="
        margin: 0.14in 0in 0in;
        background: transparent none repeat scroll 0% 50%;
        background-color:#FCC;
      "
      align="left">
      Большое спасибо этим людям за вдохновение и часы напряженной работы над
      созданием этого руководства:
    </p>
    <ul>
      <li>Jonathan Wolter</li>
      <li>Russ Ruffer</li>
      <li>Miško Hevery</li>
    </ul>
    <p>
      Also thanks to&nbsp;Blaine R Southam who has turned it into a
      <a
        href="./Guide-Writing Testable Code.pdf">pdf book</a>.
    </p>
    <p
      style="
        background-color:#FCC;
      "
    >
      Также спасибо Blaine R Southam, который превратил это в книгу в формате
      <a
        href="./Guide-Writing Testable Code.pdf">pdf</a>.
    </p>
    <p>
      <a
        href="./flaw-constructor-does-work.md">Flaw #1: Constructor does Real Work</a>
    </p>
    <p
      style="
        margin: 0.14in 0in 0in;
        background: transparent none repeat scroll 0% 50%;
        background-color:#FCC;
      "
    >
      <a
        href="./flaw-constructor-does-work-ru.md">Недостаток (Ошибка|Изъян|Дефект) № 1: Конструктор выполняет Реальную Работу</a>
    </p>
    <p
      style="
        margin-left: 0.06in;
        margin-top: 0in;
        margin-bottom: 0in;
        font-style: normal;
      "
      align="left">
      <strong>Warning Signs</strong>
    </p>
    <p
      style="
        margin-left: 0.06in;
        margin-top: 0in;
        margin-bottom: 0in;
        font-style: normal;
        background-color:#FCC;
      "
      align="left">
      <strong>Тревожные симптомы</strong>
    </p>
    <ul>
      <li>
        <span style="font-family: Courier New, monospace">new</span> keyword in
        a constructor or at field declaration
      </li>
      <li
          style="
            background-color:#FCC;
          "
      >
        Ключевое слово <span style="font-family: Courier New, monospace">new</span> 
        в конструкторе или в объявлении поля
      </li>
      <li>Static method calls in a constructor or at field declaration</li>
      <li
          style="
            background-color:#FCC;
          "
      >
      Вызовы статических методов в конструкторе или в объявлении поля</li>
      <li>Anything more than field assignment in constructors</li>      
      <li
          style="
            background-color:#FCC;
          "
      >
      Что-то большее, чем назначение полей в конструкторах</li>
      <li>
        Object not fully initialized after the constructor finishes (watch out
        for
        <span style="font-family: Courier New, monospace">initialize</span>
        methods)
      </li>
      <li
          style="
            background-color:#FCC;
          "
      >
        Объект не полностью инициализирован после завершения работы конструктора
        (следите за методами <span style="font-family: Courier New, monospace">инициализации</span>)
      </li>
      <li>Control flow (conditional or looping logic) in a constructor</li>
      <li
          style="
            background-color:#FCC;
          "
      >
      Порядок выполнения (условная или циклическая логика) в конструкторе
      </li>
      <li>
        Code does complex object graph construction inside a constructor rather
        than using a factory or builder
      </li>
      <li
          style="
            background-color:#FCC;
          "
      >
        Код выполняет построение сложного объектного графа внутри конструктора,
        а не с помощью Фабрики (Factory) или Сроителя (Builder)
      </li>
      <li>Adding or using an initialization block</li>
      <li
          style="
            background-color:#FCC;
          "
      >
      Добавление или использование блока инициализации
      </li>
    </ul>
    <p
      style="
        margin: 0.14in 0in 0in;
        background: transparent none repeat scroll 0% 50%;
      "
      align="left">
      <a
        href="./flaw-digging-into-colaborators.md">Flaw #2: Digging into Collaborators</a>
    </p>
    <p
      style="
        margin-left: 0.06in;
        margin-top: 0in;
        margin-bottom: 0in;
        font-style: normal;
      "
      align="left">
      <strong>Warning Signs</strong>
    </p>
    <ul>
      <li>
        Objects are passed in but never used directly (only used to get access
        to other objects)
      </li>
      <li>
        Law of Demeter violation: method call chain walks an object graph with
        more than one dot (<span style="font-family: Courier New, monospace">.</span>)
      </li>
      <li>
        Suspicious names:
        <span style="font-family: Courier New, monospace">context</span>,
        <span style="font-family: Courier New, monospace">environment</span>,
        <span style="font-family: Courier New, monospace">principal</span>,
        <span style="font-family: Courier New, monospace">container</span>, or
        manager
      </li>
    </ul>
    <p
      style="
        margin: 0.14in 0in 0in;
        background: transparent none repeat scroll 0% 50%;
      "
      align="left">
      <a
        href="./flaw-brittle-global-state-singletons.md">Flaw #3: Brittle Global State &amp; Singletons</a>
    </p>
    <p
      style="
        margin-left: 0.06in;
        margin-top: 0in;
        margin-bottom: 0in;
        font-style: normal;
      "
      align="left">
      <strong>Warning Signs</strong>
    </p>
    <ul>
      <li>Adding or using singletons</li>
      <li>Adding or using static fields or static methods</li>
      <li>Adding or using static initialization blocks</li>
      <li>Adding or using registries</li>
      <li>Adding or using service locators</li>
    </ul>
    <p
      style="
        margin: 0.14in 0in 0in;
        background: transparent none repeat scroll 0% 50%;
      "
      align="left">
      <a
        href="./flaw-class-does-too-much.md">Flaw #4: Class Does Too Much</a>
    </p>
    <p
      style="
        margin-left: 0.06in;
        margin-top: 0in;
        margin-bottom: 0in;
        font-style: normal;
      "
      align="left">
      <strong>Warning Signs</strong>
    </p>
    <ul>
      <li>Summing up what the class does includes the word “and”</li>
      <li>
        Class would be challenging for new team members to read and quickly “get
        it”
      </li>
      <li>Class has fields that are only used in some methods</li>
      <li>Class has static methods that only operate on parameters</li>
    </ul>
  </div>
</div>
