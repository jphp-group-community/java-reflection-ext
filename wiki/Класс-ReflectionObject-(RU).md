PHP SDK: [ReflectionObject.php](https://github.com/VenityStudio/java-reflection-ext/blob/master/sdk/java/reflection/ReflectionObject.php) <br>
Java Source: [ReflectionObject.java](https://github.com/VenityStudio/java-reflection-ext/blob/master/src-jvm/main/java/org/venity/javareflection/classes/ReflectionObject.java) <br>
Namespace: ``java\reflection``

### Описание:

Класс ``ReflectionObject`` представляет из себя обёрткой над ``java.lang.Object``.
Этот класс предназначен для хранения классов **Java** в контексте **jPHP**.

Так же в этом классе есть статические функции для перевода **Java** классов в **jPHP** и на оборот. Но перевод классов в **jPHP** работает не всегда. Связано это с тем что этот класс не описан для ядра **jPHP**, в этом случаи будет возвращена стандартная обёртка над ``java.lang.Object`` которая не имеет функционала, кроме как выводить полный ``namespace`` класса.

### Функции класса:

* **getReflectionClass** - возвращает экземпляр ``Class`` ([ReflectionClass]()). Обёртка над функцией ``getClass``
* **equals** - принимает в себя любой объект и возвращает ``bool``. Обёртка над функцией ``equals``
* **toMemory** - переводит объект из **Java** в **jPHP** класс.

### Статические функции: 

* **fromMemory** - принимает любой класс из **jPHP** и возвращает экземпляр [ReflectionObject]()
* **fromCallback** - возвращает экземпляр [ReflectionObject]() за основу взяв ``php.runtime.invoke.Invoker``. В основном нужен для [java-dynamic-compile-ext](https://github.com/VenityStudio/java-dynamic-compile-ext)
