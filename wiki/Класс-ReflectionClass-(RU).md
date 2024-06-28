PHP SDK: [ReflectionClass.php](https://github.com/VenityStudio/java-reflection-ext/blob/master/sdk/java/reflection/ReflectionClass.php) <br>
Java Source: [ReflectionClass.java](https://github.com/VenityStudio/java-reflection-ext/blob/master/src-jvm/main/java/org/venity/javareflection/classes/ReflectionClass.java) <br>
Namespace: ``java\reflection``

### Описание:

``ReflectionClass`` представляет с собой обёртку над ``Class`` из **Java**. этот класс предназначен для манипуляции **Java** классами. Этот класс может создавать экземпляры [ReflectionObject](https://github.com/VenityStudio/java-reflection-ext/wiki/%D0%9A%D0%BB%D0%B0%D1%81%D1%81-ReflectionObject-(RU)) а так же находить и выполнять методы классов. 

### Функции класса:

* **newInstance** - создаёт новый экземпляр класса без вызова конструктора. Возвращает [ReflectionObject](https://github.com/VenityStudio/java-reflection-ext/wiki/%D0%9A%D0%BB%D0%B0%D1%81%D1%81-ReflectionObject-(RU))
* **getConstructor** - получить получить экземпляр [ReflectionConstructor]() данного класса, по массиву из [ReflectionClass]()
* **getDeclaredConstructor** - почти тоже самое что **getConstructor**, только ищет и по родителям класса
* **getMethod** - получить получить экземпляр [ReflectionMethod]() для данного метода, по массиву из [ReflectionClass]()
и имени метода
* **getDeclaredMethod** - почти тоже самое что **getMethod**, только ищет и по родителям класса
* **getField** - получить получить экземпляр [ReflectionField]() для данного поля класса по имени
* **getDeclaredField** - почти тоже самое что **getField**, только ищет и по родителям класса
* **getMethods** - получить массив всех методов данного класса
* **getDeclaredMethods** - получить массив всех методов данного и родительских классов
* **getConstructors** - получить массив всех конструкторов данного класса
* **getDeclaredConstructors** - получить массив всех конструкторов данного и родительских классов
* **getFields** - получить массив всех полей данного класса
* **getDeclaredFields** - получить массив всех полей данного и родительских классов
* **getName** - возвращает имя класса
* **getCanonicalName** - возвращает полное имя класса 

### Статические функции:

* **forName** - принимает в себя строку с полным именем **Java** класса и возвращает экземпляр [ReflectionClass]().

### Пример: 

```php
use java\reflection\ReflectionClass;

$class = ReflectionClass::forName("javax.swing.JFrame"); // Получаем ReflectionClass для javax.swing.JFrame
$constructor = $class->getConstructor([ ReflectionClass::forName("java.lang.String") ]); // Получаем конструктор класса
    // javax.swing.JFrame(java.lang.String title)
$instance = $constructor->newInstance([ "Reflection!" ]); // Создаем объект из конструктора
$method = $class->getMethod("setVisible", [ ReflectionTypes::typeBool() ]); // Получаем класс метода
    // javax.swing.JFrame.setVisible(bool visible)
$method->invoke($instance, [ true ]); // Выполняем метод
```

Результат: https://prnt.sc/nnlon2
