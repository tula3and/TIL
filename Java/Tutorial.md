## Java tutorial

- Download [OpenJDK](https://jdk.java.net/15/) and set the environment variable
  - JDK: java development kit, 개발 환경
    - /bin/javac: a compiler
    - /bin/java: a launcher with JVM
    - /bin/javadoc: API documents (HTML)
      - API (application programming interface): the class library
      - Provided as packages
  - JRE (⊂ JDK): java runtime environment, 실행 환경 (JVM 포함)
  - Java SE (standard edition)
- `.java` → (Compile) → `.class` → `Java Virtual Machine` → `computer`
- Start codes with the comment below, package, and import sentences
  ```java
  /*
   * class name
   *
   * version information
   *
   * date
   *
   * copyright
   */
  package java.source; // Clarify the file location (folder)
  
  import java.util.Random; // Don't have to write a package
  ```
- Print "Hello World"
  ```java
  // HelloWorldApp.java
  // There must be just ONE PUBLIC CLASS each file
  public class HelloWorldApp{ // Public class name must be same with the file name
    public static void main(String[] args) { // There must be also one main method each file
      System.out.println("Hello world!!"); // Not i
    }
  }
  ```
- Identifier
  - Available: `$` `_` `한글`
  - Unavailable: keywords, most of special characters, numbers as the first letter
  - Class `UpperCamelCase`
  - Method `lowerCamelCase`
  - Constant `NUMBER`
  - Variable `lowerCamelCase`
- Input values: [Scanner methods](https://www.javatpoint.com/Scanner-class)
  ```java
  System.out.println("Input your name, age, and marital status: ");
  Scanner a = new Scanner(System.in);

  String name = a.next();
  System.out.print("Name: " + name + ", ");

  int age = a.nextInt();
  System.out.print("Age: " + age + ", ");

  boolean single = a.nextBoolean();
  System.out.print("Marital status: " + single);

  a.close();
  ```
- Array
  - Declare: `int arr[]` or `int[] arr`
  - Create: `arr = new int[10]`
  - Share an array (get same reference): `arr = newArr`
  - `enum`
    ```java
    enum Week { mon, tue, wed, thu, fri, sat, sun }
    
    public static void main(String[] args) {
        for (Week day : Week.values())
            System.out.println(day); // day.ordinal() // int
    }
    ```
- Class can have fields and methods.
  - Constructor: initialize field values and no `return`
  - Class can make an object (instance) which has states and behaviors.
  - Objects and arrays copy each reference using `=`
  - Each element in an array of objects must be initialized!
    ```
    Animal [] a = new Animal[5];
    
    for (int i = 0; i < a.length; i++) {
      a[i] = new Animal();
    }
    ```
- Inheritance using `extends`: `Class sub_class extends super_class`
- Overriding & Overloading
  - Overriding: in a child class: same parameters
    ```java
    class Plus {
        public int sum(int a, int b) {
            return a + b;
        }
    }
    
    // Overriding
    class NewPlus extends Plus {
        public int sum(int a, int b) {
            System.out.println("New!");
            return a + b;
        }
    }
    ```
  - Overloading: in a same class: different parameters (e.g. constructor overloading)
    ```java
    class Plus {
        public int sum(int a, int b) {
            return a + b;
        }
        
        // Overloading
        public int sum(int a, int b, int c) {
            return a + b + c;
        }
    }
    ```
- Access modifier: (literally) `default` `private` `public` `protected`
  - private < default < protected < public
  - private: only in a same class
  - default: in a same package





