# Week 1; Lecture 1; Introduction to Java

Java uses classes to create a program
```
public class HelloWorld
{
    public static void main(String[] args)
    {
        System.out.println("Hello World");
    }
}

```
In order to show something on the console, a static object System.out is used with functions like print() and println()
```
public class HelloWorld
{
    public static void main(String[] args)
    {
        System.out.print("Hello World");
        System.out.print("Ontario Tech");
    }
}
```

Word `static` means it is a class level function and not an object/instance level function. So you can access this function without creating an object of a class. You can create more than one static function in a class.
```
public class HelloWorld
{
    public static void main(String[] args)
    {
        System.out.println("Hello World");
        test();
    }

    public static void test()
    {
        System.out.println("This is another static function");
    }
}
```
Member functions can also be used in Java that would require you to create an object/instance of a class to access them. These functions cannot be accessed without an object. So the following code will produce an error.
```
public class Testing {


    public void test()
    {
        System.out.println("This is a member function");
    }
    public static void main(String[] args) {
        test();
    }
    
}
```
In order to fix the above code, an instance of the class is required. Below is the correct code.
```
public class Testing {


    public void test()
    {
        System.out.println("This is a member function");
    }
    public static void main(String[] args) {
        Testing testing = new Testing();
        testing.test();
    }
    
}
```
More than 1 member function can be created inside a class like C++
```
public class Testing {


    public void test()
    {
        System.out.println("This is a member function");
    }

    public void test_2()
    {
        System.out.println("This is another member function");
    }
    public static void main(String[] args) {
        Testing testing = new Testing();
        testing.test();
        testing.test_2();
    }
    
}
```

# Week 1, Lecture 2; Data Types and Type Casting in Java

Java uses various data types just like C and C++.
```
public class Student {
    
    public static void main(String[] args) {
        String name = "Steve Jobs";
        int age = 55;
        float cgpa = 2.95f;
        boolean active = true;
        double height = 5.11;

        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("CGPA: " + cgpa);
        System.out.println("Active: " + active);
        System.out.println("Height: " + height);
    }
}
```
`printf` is another way of printing in Java much like C and C++.
```
public class Student {
    
    public static void main(String[] args) {
        String name = "Steve Jobs";
        int age = 55;
        float cgpa = 2.95f;
        boolean active = true;
        double height = 5.11;

        System.out.printf("Name: %s \nAge: %d \nCGPA: %.2f \nActive: %s \nHeight: %.2f", name, age, cgpa, active, height);
    }
}
```
Instance members (variables) are used in Java much like member functions. More than 1 can be created. An instance of the class is required to access these variables inside a static method.
```
public class Student {
    String name = "Steve Jobs";
    int age = 55;
    float cgpa = 2.95f;
    boolean active = true;
    double height = 5.11;

    public static void main(String[] args) {

        Student student = new Student();
        System.out.printf("Name: %s \nAge: %d \nCGPA: %.2f \nActive: %s \nHeight: %.2f", student.name, student.age, student.cgpa, student.active, student.height);
    }
}
```
Member functions can access instance variables without creating an instance of a class. However, to call a member function in a static function, an instance is required for that class.

```
public class Student {
    String name = "Steve Jobs";
    int age = 55;
    float cgpa = 2.95f;
    boolean active = true;
    double height = 5.11;


    public void display()
    {
        System.out.printf("Name: %s \nAge: %d \nCGPA: %.2f \nActive: %s \nHeight: %.2f", name, age, cgpa, active, height);
    }

    public static void main(String[] args) {
        Student student = new Student();
        student.display();
        
    }
}
```
Conditional statements in Java are similar to C and C++.
```
public class Student {
    String name = "Steve Jobs";
    int age = 55;
    float cgpa = 3.95f;
    boolean active = true;
    double height = 5.11;

    void calculateGrade()
    {
        if (cgpa > 3.5f && cgpa <=4.0f)
        {
            System.out.println("A");
        }
        else if (cgpa > 3.0f && cgpa <=3.5f)
        {
            System.out.println("B");
        }
        else if (cgpa > 2.5f && cgpa <=3.0f)
        {
            System.out.println("C");
        }
        else if (cgpa > 2.0f && cgpa <=2.5f)
        {
            System.out.println("D");
        }
        else
        {
            System.out.println("F");
        }
    }

    public void display()
    {
        System.out.printf("Name: %s \nAge: %d \nCGPA: %.2f \nActive: %s \nHeight: %.2f \n", name, age, cgpa, active, height);
    }

    public static void main(String[] args) {
        Student student = new Student();
        student.display();
        student.calculateGrade();
        
    }
}
```
Java has loops similar to C and C++.
```
    void progress()
    {
        int i = 1;
        while (i<=8)
        {
            System.out.printf("Semester: %d , CGPA: %.2f ", i, cgpa );
            cgpa = cgpa - 0.25f;
            i++;
        }
    }
```
Java functions can return results based on various data types.
```
public class Numbers {

    public static double power(int base, int exponent)
    {
        double result = 1;

        for (int i=0; i<exponent; i++)
        {
            result *= base;
        }

        return result;
    }
    public static void main(String[] args) {
        
        double result = power(5, 2);
        System.out.println("Result: " + result);
    }
}
```
Java allows casting from one data type to another. Java allows implicit casting as well as explicit casting.
```
// Implicit Casting

    public static void casting(int number)
    {
        int i = 10;
        double d = i;
        float f = i;

        System.out.println("Integer : " + i);
        System.out.println("Double : " + d);
        System.out.println("Float : " + f);

    }
```
Narrow casting would result in an error as we need lose precision. Below will produce an error
```
    public static void casting(int number)
    {
        double d = 10.5;
        int i = d;

        System.out.println("Integer : " + i);
        System.out.println("Double : " + d);

    }
```
```
// Explicit Casting

public static void casting(int number)
{
        int i = 10;
        double d = (double) i;
        System.out.println("Integer : " + i);
        System.out.println("Double : " + d);

}
```
Narrow casting is allowed using explicit casting
```
public static void casting(int number)
    {
        double d = 10.5;
        int i = (int) d;
        System.out.println("Integer : " + i);
        System.out.println("Double : " + d);

    }
```

# Week 2; Lecture 4; Inner Classes, Inheritance and Polymorphism

Inner classes are allowed in Java as they can help in providing extra functionality in an organized manner.

`Student.java`
```
public class Student {
    String name;
    int age;

    Student(String name, int age)
    {
        this.name = name;
        this.age = age;
    }

    String getName()
    {
        return this.name;
    }

    int getAge()
    {
        return this.age;
    }

    void display()
    {
        System.out.println("Name: " + this.name + ", Age: " + this.age);
    }

    class StudentDetails
    {
        String getFirstName()
        {
            String firstName[];

            firstName = name.split(" ", 2);

            return firstName[0];
        }
    }
}
```
`Driver.java`
```
public class Driver {
    
    public static void main(String[] args) {
        Student student = new Student("Steve Jobs", 55);
        student.display();

        Student.StudentDetails details = student.new StudentDetails();
        System.out.println(details.getFirstName());
        
    }
}
```
Just like C++, Java offer Inheritance

`Vehicle.java`
```
package Inheritance;

public class Vehicle {
    String name;
    int kms;

    Vehicle()
    {
        this.name = "";
        this.kms = 0;
    }

    Vehicle(String name, int kms)
    {
        this.name = name;
        this.kms = kms;
    }

    void display()
    {
        System.out.println("Name: " + this.name + ", KMs: " + this.kms);
    }
}

```
`Car.java`
```
package Inheritance;

public class Car extends Vehicle {
    String type;

    Car()
    {
        this.type = "";
    }
    Car(String name, int kms, String type)
    {
        super(name, kms);
        this.type = type;
    }
    void display()
    {
        super.display();
        System.out.println("Type: " + type);
    }
}
```
`Driver.java`
```
package Inheritance;


public class Driver {
    
    public static void main(String[] args) {
        Car car  = new Car("Toyota Rav4", 1234, "SUV");
        car.display();
    }
}
```
Java does not offer multiple inheritance, however, it does offer multi-level-inheritance

`Phone.java`
```
package Multi_Level_Inheritance;

public class Phone {
    
    void makeCalls()
    {
        System.out.println("I can make calls");
    }
}
```

`SmartPhone.java`
```
package Multi_Level_Inheritance;

public class SmartPhone extends Phone {
    void browseInternet()
    {
        System.out.println("I can browse Internet");
    }

}
```
`Android.java`
```
package Multi_Level_Inheritance;

public class Android extends SmartPhone{
    
    void iAmAndroid()
    {
        System.out.println("I am Android");
    }
}
```

`Driver.java`
```
package Multi_Level_Inheritance;

public class Driver {
    
    public static void main(String[] args) {
        Android android = new Android();
        android.makeCalls();
        android.browseInternet();
        android.iAmAndroid();
    }
}
```

Java supports Polymorphism, e.g., An object of parent class can hold the reference of a child class.

`Driver.java`
```
package Polymorphism;

public class Driver {
    public static void main(String[] args) {

        Car car = new Car("Honda Civic", 45454, "Sedan");

        Vehicle v = car;
        v.display();
    }
}
```

Using Polymorphism at run time, Java knows which exact function to call based on the reference it has.

`Shape.java`
```
package Polymorphism_2;

public class Shape {
    double height, width;
    String name;

    Shape()
    {
        this.height = this.width = 0.0;
        this.name = "";
    }
    Shape(double height, double width, String name)
    {
        this.height = height;
        this.width = width;
        this.name = name;
    }

    double calculateArea()
    {
        return 0.0;
    }
}
```
`Rectangle.java`
```
package Polymorphism_2;

public class Rectangle extends Shape {
    
    Rectangle()
    {
        super();
    }

    Rectangle(double height, double width, String name)
    {
        super(height, width, name);
    }

    double calculateArea()
    {
        return height * width;
    }
}
```

`Triangle.java`

```
package Polymorphism_2;

public class Triangle extends Shape{
    
    Triangle()
    {
        super();
    }

    Triangle(double height, double width, String name)
    {
        super(height, width, name);
    }

    double calculateArea()
    {
        return (height* width)/2;
    }
}

```
`Driver.java`
```
package Polymorphism_2;

public class Driver {
    public static void main(String[] args) {
        
        Shape shapes[] = new Shape[5];
        shapes[0] = new Triangle(10.0, 5.0, "Triangle 1");
        shapes[1] = new Triangle(15.0, 15.0, "Triangle 2");
        shapes[2] = new Rectangle(10.0, 10.0, "Rectangle 1");
        shapes[3] = new Rectangle(20.0, 1.0, "Rectangle 2");
        shapes[4] = new Shape(10.0, 1.0, "General Shape");

        for (int i = 0; i <5; i++)
        {
            System.out.println("Shape is " + shapes[i].name);
            System.out.println("Area is " + shapes[i].calculateArea());
        }
    }
}
```

# Week 2; Lecture 4; Abstraction, Exception Handling, Packages and Final
Java uses the concept of Abstract classes just like C++ except that it does not use virtual keyword and instead uses abstract keyword.

`Shape.java`
```
package Abstract_Methods;

public abstract class Shape {
    double height, width;
    String name;

    Shape()
    {
        this.height = this.width = 0.0;
        this.name = "";
    }
    Shape(double height, double width, String name)
    {
        this.height = height;
        this.width = width;
        this.name = name;
    }

    abstract double calculateArea();
}
```

`Rectangle.java`
```
package Abstract_Methods;

public class Rectangle extends Shape {
    
    Rectangle()
    {
        super();
    }

    Rectangle(double height, double width, String name)
    {
        super(height, width, name);
    }

    double calculateArea()
    {
        return height * width;
    }
}
```
`Triangle.java`
```
package Abstract_Methods;

public class Triangle extends Shape{
    
    Triangle()
    {
        super();
    }

    Triangle(double height, double width, String name)
    {
        super(height, width, name);
    }

    double calculateArea()
    {
        return (height* width)/2;
    }
}
```

`Driver.java`
```
package Abstract_Methods;

public class Driver {
    public static void main(String[] args) {
        
        Shape shapes[] = new Shape[4];
        shapes[0] = new Triangle(10.0, 5.0, "Triangle 1");
        shapes[1] = new Triangle(15.0, 15.0, "Triangle 2");
        shapes[2] = new Rectangle(10.0, 10.0, "Rectangle 1");
        shapes[3] = new Rectangle(20.0, 1.0, "Rectangle 2");

        for (int i = 0; i <4; i++)
        {
            System.out.println("Shape is " + shapes[i].name);
            System.out.println("Area is " + shapes[i].calculateArea());
        }
    }
}
```

In Java programming, it is sometimes helpful to define what a class must do but not how it will do it.

`Series.java`
```
package Interfaces;

public interface Series {
    int getNext();
    void reset();
    void setStart(int x);
}
```

`Ones.java`
```
package Interfaces;

public class Ones implements Series{
    int start;
    int value;

    Ones()
    {
        this.start = 0;
        this.value = 0;
    }
    public int getNext()
    {
        this.value += 1;
        return this.value;
    }
    public void reset()
    {
        this.value = 0;
    }
    public void setStart(int x)
    {
        this.start = x;
        this.value = x;

    }
}
```

`Twos.java`
```
package Interfaces;

public class Twos implements Series{
    int start;
    int value;

    Twos()
    {
        this.start = 0;
        this.value = 0;
    }
    public int getNext()
    {
        this.value += 2;
        return this.value;
    }
    public void reset()
    {
        this.value = 0;
    }
    public void setStart(int x)
    {
        this.start = x;
        this.value = x;

    }
}
```

`Driver.java`
```
package Interfaces;

public class Driver {
    public static void main(String[] args) {
        Ones ones = new Ones();
        
        for (int i =0; i<5; i++)
        {
            System.out.println("Next value: " + ones.getNext());
        }

        ones.setStart(100);
        for (int i =0; i<5; i++)
        {
            System.out.println("Next value: " + ones.getNext());
        }

        ones.reset();
        for (int i =0; i<5; i++)
        {
            System.out.println("Next value: " + ones.getNext());
        }

        Twos twos = new Twos();

        for (int i =0; i<5; i++)
        {
            System.out.println("Next value: " + twos.getNext());
        }
    }
}
```

In programming, it is often helpful to group related pieces of a program together. In Java, this can be accomplished by using a package.

`Book.java`
```
package Packages;

/**
 * Book
 */
public class Book {

    String name;
    String author;

    Book(String name, String author)
    {
        this.name = name;
        this.author = author;
    }

    public String toString()
    {
        return "Name: " + this.name + " Author: " + this.author;
    }
}
```
`Driver.java`
```
package Packages;

public class Driver {

    public static void main(String[] args) {
        Book book  = new Book("Data Structure", "Oreily");
        System.out.println(book.toString());
    }
    
}
```
Access modifiers work for packages as well. By default classes have package access which means they are visible to all classes within their package. However, this access can be change by changing access modifiers to private which would make that data member inaccessible outside the class.
```
package Packages;

/**
 * Book
 */
public class Book {

    private String name;
    String author;

    Book(String name, String author)
    {
        this.name = name;
        this.author = author;
    }

    public String toString()
    {
        return "Name: " + this.name + " Author: " + this.author;
    }
}
```
A final is pretty handy keyword in java. It helps in avoiding accidentle change of values for a variable just like const in C++. 

Below code will produce an error.

`Student.java`
```
package Final_Keyword;

public class Student {
    String name;
    int age;
    final String student_type = "Undergraduate";

    void setType()
    {
        this.student_type = "Graduate";
    }
}
```
`final` keyword can also be used to avoid inheritance of classes.

This code will produce an error.

`Student.java`
```
package Final_Keyword;

public final class Student {
    String name;
    int age;

    Student(String name)
    {
        this.name = name;
    }
    
    public String toString()
    {
        return "Name: " + this.name;
    }

}
```
`Undergraduate.java`
```
package Final_Keyword;

public class Undergraduate extends Student{

    Undergraduate(String name)
    {
        super(name);
    }
    
}
```

`Driver.java`
```
package Final_Keyword;

public class Driver {
    public static void main(String[] args) {
        Undergraduate ug = new Undergraduate("Steve Jobs");
        System.out.println(ug);
    }
}
```

`final` keyword can also be used to prevent overriding of methods display method in the code below cannot be overridden in child classes

`Student.java`

```
package Final_Keyword;

public class Student {
    String name;
    int age;

    Student(String name)
    {
        this.name = name;
    }
    
    public String toString()
    {
        return "Name: " + this.name;
    }

    final void display()
    {
        System.out.println("Name: " + this.name);
    }

}
```
There is an `Object` class in Java which is the parent class of all the classes. Even if no parent class is specified, that class would be extended from Object class. Parent of Student class below is Object class although it is not explicity mentioned.

`Student.java`
```
package Object_Class;

public class Student {
    String name;

    Student(String name)
    {
        this.name = name;
    }

    public String toString()
    {
        return this.name;
    }
}
```
The `toString()` method is basically a method in Object class which is overridden in child classes and hence requires public access.

Exception handling streamlines error handling by allowing your program to define a block of code, called an exception handler, that is executed automatically when an error occurs.

`Driver.java`
```
package Exception_Handling;

public class Driver {
    public static void main(String[] args) {
        int nums[] = new int[4];

        try
        {
            nums[7] = 10;
        }
        catch(Exception e)
        {
            System.out.println("Array Index out of bound");
        }
        
    }
}

```
Exceptions can be generated in a separate method and can be caught in another method
```
package Exception_Handling;

public class Driver {

    void calculate()
    {
        int nums[] = new int[4];

        nums[7] = 10;

    }
    public static void main(String[] args) {
        Driver d = new Driver();
        try{
            d.calculate();
        }
        catch (ArrayIndexOutOfBoundsException e)
        {
            System.out.println("Array Index out of bound.");
        }
        
        
    }
}
```

# Week 3; Lecture 5; Induction

Induction can be used to calculate the Runtime time. Lets calculate for summation of i.
```
package Induction;

/**
 * induction
 */
public class induction {

    public static void summation()
    {
        int n = 1000;
        int sum = 0;
        for (int i =0; i<=n; i++)
        {
            sum+=i;
        }
        System.out.println("Sum: " + sum);
    }

    public static void simple_induction()
    {
        int n = 1000;
        int result = n*(n+1)/2;
        System.out.println("Sum: " + result);
    }
    public static void main(String[] args) {
        double starTime = (double)System.nanoTime();
        summation();
        double endTime = (double) System.nanoTime();

        double duration = endTime - starTime;
        double seconds = (double)duration/1000000000;

        System.out.printf("Duration: %.6f \n", seconds);

        // Induction
        double starTime_1 = (double)System.nanoTime();
        simple_induction();
        double endTime_1 = (double) System.nanoTime();

        double duration_1 = endTime_1 - starTime_1;
        double seconds_1 = (double)duration_1/1000000000;

        System.out.printf("Duration: %.6f", seconds_1);
    }
}
```
For summation of square of i
```
package Induction;

public class square_induction {

    public static void square_summation()
    {
        int n = 1000;
        int result = 0;

        for (int i = 0; i<=n; i++)
        {
            result+=(i*i);
        }

        System.out.println("Result: " + result);
    }

    public static void squared_induction()
    {
        int n = 1000;
        int result = 0;

        result = n*(n+1)*(2*n + 1)/6;

        System.out.println("Result: " + result);

    }
    public static void main(String[] args) {
        double starTime = (double)System.nanoTime();
        square_summation();
        double endTime = (double) System.nanoTime();

        double duration = endTime - starTime;
        double seconds = (double)duration/1000000000;

        System.out.printf("Duration: %.6f \n", seconds);


        double starTime_1 = (double)System.nanoTime();
        squared_induction();
        double endTime_1 = (double) System.nanoTime();

        double duration_1 = endTime_1 - starTime_1;
        double seconds_1 = (double)duration_1/1000000000;

        System.out.printf("Duration: %.6f \n", seconds_1);
    }
}
```

# Week 3; Lecture 6; Big O 

Constant time function is when the runtime does not increase with the increase in the size of the array
```
package Big_O;

public class Driver {

    public static int constant_function(int arr[])
    {
        int number = 0;  // O(1)
        return number;   // O(1)
	
	// total time = O(1) + O(1) = O(2) which is constant
    }
    public static void main(String[] args) {

        int arr[] = new int[5];
        constant_function(arr);
        
    }
    
}
```
Linear time function is when the runtime increases with the increase in the size of the array or size of the input
```
    public static int linear_function(int arr[])
    {
        int sum = 0;  // O(1)
        for (int i=0; i<arr.length; i++)   // this runs n times
        {
            sum+=i;   // O(1)
        }
        return sum;   // O(1)

    // total time = O(1) + n x O(1) + O(1) = O(n)
    }
```
Even will multiple loops, we still get linear time
```
    public static void sum_product(int arr[])
    {
        int sum = 0;  // O(1)
        for (int i=0; i<arr.length; i++)   // this runs n times
        {
            sum+=i;   // O(1)
        }
        System.out.println("Sum: " + sum);   // O(1)
        
        int product = 0;  // O(1)
        for (int i=0; i<arr.length; i++)   // this runs n times
        {
            product*=i;   // O(1)
        }
        System.out.println("Product: " + product);  // O(1)

        // total time = O(1) + n x O(1) + O(1) + O(1) + n x O(1) + O(1) = O(2n) = O(n)
    }
```
Quadratic Time is when nested loops come into play
```
    public static void pairs(int arr[])
    {
        for (int i=0; i<arr.length; i++)  // this runs n times
        {
            for (int j=0; j<arr.length; j++)  // this runs n times
            {
                System.out.printf("(%d,%d)", arr[i], arr[j]); // O(1)
            }
        }
         // total time = O(n) x O(n) x O(1) = O(n^2)
    }
    public static void main(String[] args) {

        int arr[] = new int[]{1, 2, 3, 4, 5};
        pairs(arr); 
    }
```
Calculating time with two arrays of different sizes
```
public static void two_arrays(int arr1[], int arr2[])
    {
        for (int i=0; i<arr1.length; i++)  // this runs n times
        {
            for (int j=0; j<arr2.length; j++) // this runs m times
            {
                System.out.printf("(%d,%d)", arr1[i], arr2[j]);  //O(1)
            }
        }
        // total time = O(n) x O(m) x O(1) = O(nxm)
    }
    public static void main(String[] args) {

        int arr1[] = new int[]{1, 2, 3, 4, 5};
        int arr2[] = new int[]{6, 7, 8};
        two_arrays(arr1, arr2); 
    }
```

# Week 4; Lecture 7; Arrays in Java

Just like C++, Java has collections and simplest of it is an array which is much like arrays in C++.
```
package Simple_Arrays;

/**
 * Driver
 */
public class Driver {

    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 5};

        for (int i = 0; i<numbers.length; i++)
        {
            System.out.println(numbers[i]);
        }
    }
}
```
Arrays can be passed to functions in Java
```
package Simple_Arrays;

/**
 * Driver
 */
public class Driver {

    public static void display(int[] numbers)
    {
        for (int i = 0; i<numbers.length; i++)
        {
            System.out.println(numbers[i]);
        }
    }

    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 5};

        display(numbers);
    }
}
```
Arrays are passed by reference under the hood but you dont have to worry about that. It is done for you automatically.
```
package Simple_Arrays;

/**
 * Driver
 */
public class Driver {

    public static void modify(int[] numbers)
    {
        numbers[0] = 100;
    }
    public static void display(int[] numbers)
    {
        for (int i = 0; i<numbers.length; i++)
        {
            System.out.println(numbers[i]);
        }
    }

    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 5};

        display(numbers);
        modify(numbers);
        display(numbers);
    }
}
```
If an array in a method is assigned to another location then it would not change the original array.
```
package Simple_Arrays;

/**
 * Driver
 */
public class Driver {

    public static void modify(int[] numbers)
    {
        numbers[0] = 100;
    }
    public static void changeReference(int[] numbers)
    {
        numbers = new int[5];
        numbers[0] = 200;
    }
    public static void display(int[] numbers)
    {
        for (int i = 0; i<numbers.length; i++)
        {
            System.out.println(numbers[i]);
        }
    }

    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 5};

        display(numbers);
        changeReference(numbers);
        display(numbers);
    }
}
```
BTW, a variation of for loop can be used as well
```
    public static void display(int[] numbers)
    {
        for(int item: numbers)
        {
            System.out.println(item);
        }
    }

    public static void main(String[] args) {
        int numbers[] = {1, 2, 3, 4, 5};

        display(numbers);
    }
```
Getting size and elements from the user
```
package Simple_Arrays;

import java.util.Scanner;

/**
 * Driver
 */
public class Driver {

    public static void display(int[] numbers)
    {
        for(int item: numbers)
        {
            System.out.println(item);
        }
    }

    public static void getElements(int[] numbers)
    {
        Scanner scanner = new Scanner(System.in);
        
        for (int i= 0; i<numbers.length; i++)
        {
            System.out.printf("Element [%d]: ", i);
            numbers[i] = scanner.nextInt();
        }
        
        scanner.close();
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("How many elements do you want to enter: ");
        int size = scanner.nextInt();

        int[] numbers = new int[size];
        getElements(numbers);

        scanner.close();

        display(numbers);
    }
}
```
Java offers other types of Arrays like String Arrays
```
package String_Arrays;

public class Driver {

    public static void display(String[] cities)
    {
        for(String city: cities)
        {
            System.out.println(city);
        }
    }
    public static void main(String[] args) {
        String[] cities = new String[]{"Toronto", "New York", "Tokyo", "London"};
        display(cities);

    }
}
```
Arrays in Java offer all the traditional features like search and sort.
```
package String_Arrays;

public class Driver {

    public static void search(String[] cities)
    {
        String city_name = "Ottawa";

        for (String city: cities)
        {
            if (city.equals(city_name))
            {
                System.out.printf("%s found in the array.", city_name);
            }
        }
    }

    public static void display(String[] cities)
    {
        for(String city: cities)
        {
            System.out.println(city);
        }
    }
    public static void main(String[] args) {
        String[] cities = new String[]{"Toronto", "New York", "Tokyo", "London"};
        search(cities);

    }
}
```
String has a function that allows comparison by ignoring the case
```
public static void search(String[] cities)
    {
        String city_name = "toronto";

        for (String city: cities)
        {
            if (city.equalsIgnoreCase(city_name))
            {
                System.out.printf("%s found in the array.", city_name);
            }
        }
    }

```
Just like C++, Java allows Arrays of Objects

`Student.java`
```
package Object_Arrays;

public class Student {
    String name;
    int age;

    Student(String name, int age)
    {
        this.name = name;
        this.age = age;
    }

    public String toString()
    {
        return "Name: " + this.name + ", Age: " + this.age;
    }
}
```

`Driver.java`
```
package Object_Arrays;

public class Driver {
    
    public static void display(Student[] students)
    {
        for (Student student: students)
        {
            System.out.println(student.toString());
        }
    }
    public static void main(String[] args) {
        Student[] students = new Student[] {
            new Student("Steve Jobs", 55),
            new Student("Bill Gates", 65),
            new Student("Elon Musk", 45),
            new Student("Jeff Bezos", 55),
        };

        display(students);
    }
}
```
This student array can be searched for a name as well
```
public static void searchStudents(Student[] students)
    {
        for (Student student: students){
            if (student.name.equalsIgnoreCase("elon"))
            {
                System.out.printf("%s found", student.name);
            }
        }
    }
```
Arrays can be sorted by default in ascending order
```
package Sorting_Arrays;

import java.util.Arrays;

public class Driver {
    
    public static void display(int[] numbers)
    {
        for(int number: numbers)
        {
            System.out.println(number);
        }
    }
    public static void main(String[] args) {
        int[] numbers = new int[] {1, 50, 20, 24, 35, 16, 100, 75};
        display(numbers);

        Arrays.sort(numbers);

        display(numbers);
    }
}
```

# Week 4; Lecture 8; Collections and Array Optimizations
Java offers multi-dimensional arrays as well.
```
package MultiDim_Arrays;

public class Driver {
    
    public static void display(int[][] numbers)
    {
        for (int i =0; i<numbers.length; i++)
        {
            for (int j=0; j<numbers[i].length; j++)
            {
                System.out.println(numbers[i][j]);
            }
        }
    }
    public static void main(String[] args) {
        int[][] numbers = new int[][]{{1,2,3}, {4, 5, 6}};
        display(numbers);

    }
}
```
The `ArrayList` class is a resizable array, which can be found in the `java.util package`. The difference between a built-in array and an `ArrayList` in Java, is that the size of an array cannot be modified (if you want to add or remove elements to/from an array, you have to create a new one). While elements can be added and removed from an `ArrayList` whenever you want.
```
package Array_List;

import java.util.ArrayList;

public class Driver {

    public static void main(String[] args) {
        ArrayList<String> fruits = new ArrayList<String>();
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Orange");
        fruits.add("Grapes");  

        System.out.println(fruits);

    }
}
```
`ArrayList` has built-in methods like add and get to insert or get the elements.
```
package Array_List;

import java.util.ArrayList;

public class Driver {

    public static void display(ArrayList<String> fruits)
    {
        for(int i=0; i<fruits.size(); i++)
        {
            System.out.println(fruits.get(i));
        }
    }
    public static void main(String[] args) {
        ArrayList<String> fruits = new ArrayList<String>();
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Orange");
        fruits.add("Grapes");  

        display(fruits);

    }
}
```
`set` method cana be used to modify an element at a specific index in `ArrayList`
```
package Array_List;

import java.util.ArrayList;

public class Driver {

    public static void modify(ArrayList<String> fruits)
    {
        fruits.set(0, "Pine Apple");
    }

    public static void display(ArrayList<String> fruits)
    {
        for(int i=0; i<fruits.size(); i++)
        {
            System.out.println(fruits.get(i));
        }
    }
    public static void main(String[] args) {
        ArrayList<String> fruits = new ArrayList<String>();
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Orange");
        fruits.add("Grapes");  

        display(fruits);
        modify(fruits);
        display(fruits);

    }
}
```
Elements can be removed from `ArrayList` as well using remove method
```
package Array_List;

import java.util.ArrayList;

public class Driver {

    public static void removeByName(ArrayList<String> fruits)
    {
        fruits.remove("Apple");
        System.out.println(fruits.size());
    }
    
    public static void display(ArrayList<String> fruits)
    {
        for(int i=0; i<fruits.size(); i++)
        {
            System.out.println(fruits.get(i));
        }
    }
    public static void main(String[] args) {
        ArrayList<String> fruits = new ArrayList<String>();
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Orange");
        fruits.add("Grapes");  

        display(fruits);
        removeByName(fruits);
        display(fruits);

    }
}
```
`ArrayList` can be used with other data types
```
package Array_List_Integers;

import java.util.ArrayList;
import java.util.Collections;

public class Driver {
    public static void main(String[] args) {
        ArrayList<Integer> numbers = new ArrayList<Integer>();
        numbers.add(2);
        numbers.add(10);
        numbers.add(20);
        numbers.add(12);
        numbers.add(7);
        numbers.add(6);

        Collections.sort(numbers);

        System.out.println(numbers);
    }
}
```
Can be sorted in descending order by changing the above one line to
```
Collections.sort(numbers, Comparator.reverseOrder());
```
Comparing Strings can be done using ArrayList of Strings
```
public static boolean compareStringArrays(ArrayList<String> str1, ArrayList<String> str2)
    {
        boolean flag = true;

        for (int i =0; i <str1.size(); i++)
        {
            if (str1.get(i) != str2.get(i))
            {
                flag = false;
            }
        }
        return flag;
    }

    public static boolean compareStringArrays_better(ArrayList<String> str1, ArrayList<String> str2)
    {
        return String.join("",str1).equals(String.join("",str2));
    }
    public static void main(String[] args) {
        ArrayList<String> str1 = new ArrayList<>();
        str1.add("Toronto");
        str1.add("Ottawa");
        str1.add("Oshawa");

        ArrayList<String> str2 = new ArrayList<>();
        str2.add("Toronto");
        str2.add("Ottawa");
        str2.add("Oshawa");

        if (compareStringArrays_better(str1, str2))
        {
            System.out.println("String arrays are equal");
        }
        else{
            System.out.println("String arrays are not equal");
        }

    }
```

# Week 5; Lecture 9; Stacks and Queues

Java has a built-in class for Stack under java.util package.
```
package Stack_Class;

import java.util.Scanner;
import java.util.Stack;

public class Driver {
    
    public static void pushElements(Stack<Integer> stack)
    {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter the size of the stack: ");
        int size = scanner.nextInt();

        for (int i=0; i<size; i++)
        {
            System.out.print("Enter element: ");
            stack.push(scanner.nextInt());
        }

        scanner.close();    
    }

    public static void popElements(Stack<Integer> stack)
    {
        while(!stack.isEmpty())
        {
            System.out.println("Element " + stack.pop() + " popped");
        }
    }

    public static void searchElement(Stack<Integer> stack, int number)
    {
        int pos = stack.search(number);

        if (pos == -1)
        {
            System.out.println("Item not found!");
        }
        else
        {
            System.out.println("Item found at index " + pos);
        }
    }
    public static void main(String[] args) {
        Stack<Integer> stack = new Stack<>();
        pushElements(stack);
        searchElement(stack, 5);
        //popElements(stack);
        
    }
}
```

Stacks can help in validating an equation. Assume an equation in the form of a string which has characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.
```
package Valid_Parenthesis;

import java.util.Stack;

public class Driver {

    public static boolean isValid(String str) 
    {
        Stack<Character> stack = new Stack<>();

        for (char c: str.toCharArray())
        {
            if (c == '(' || c == '{'|| c == '[')
            {
                stack.push(c);
            }
            else if (stack.empty())
            {
                return false;
            }
            else if ((c == ')' && stack.pop() != '(' ) || (c == '}' && stack.pop() != '{') || (c == ']' && stack.pop() != '['))
            {
                return false;
            }

        }
        return stack.empty();
    }

    public static void main(String[] args) 
    {
        System.out.println(isValid("()"));  
    }
}
```

Remove all the consecutive duplicates from the string using stack.
```
package Remove_Duplicates;

import java.util.Stack;

public class Driver {
    
    public static String removeDuplicates(String str) 
    {
        Stack<Character> stack = new Stack<>();
        StringBuilder result = new StringBuilder();

        for (char c: str.toCharArray())
        {
            if (!(stack.isEmpty()) && stack.peek() == c )
            {
                stack.pop();
            }
            else
            {
                stack.push(c);
            }
        }

        while (!stack.isEmpty())
        {
            result.append(stack.pop());
        }

        return result.reverse().toString();
        
    }
    public static void main(String[] args) {

        System.out.println(removeDuplicates("abccbz"));
        
    }
}
```

Java has some built-in classes and intefaces for queue as well. PriorityQueue is one of them.

`Driver.java`
```
package PriorityQueue_Class;

import java.util.PriorityQueue;
import java.util.Scanner;

public class Driver {

    public static void pushElements(PriorityQueue<Integer> queue)
    {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter the size of the queue: ");
        int size = scanner.nextInt();

        for (int i=0; i<size; i++)
        {
            System.out.print("Enter element to push: ");
            queue.add(scanner.nextInt());
        }
        scanner.close();
    }

    public static void print(PriorityQueue<Integer> queue)
    {
        System.out.println(queue);
        // while (!queue.isEmpty())
        // {
        //     System.out.println(queue.element());
        //     queue.poll();
        // }
    }
    public static void main(String[] args) {
        PriorityQueue<Integer> queue = new PriorityQueue<>();

        pushElements(queue);
        print(queue);
    }
}
```


A java program that returns the max. product of 2 elements from an array using PriorityQueue.
```
package Maximum_Product;

import java.util.Collections;
import java.util.PriorityQueue;

public class Driver {

    public static int max_product(int[] numbers)
    {
        PriorityQueue<Integer> queue = new PriorityQueue<>(Collections.reverseOrder());

        for (int number: numbers)
        {
            queue.add(number);
        }
        
        // while(!queue.isEmpty())
        // {
        //     System.out.println(queue.poll());
        // }
        int result = queue.poll() * queue.poll();
        return result;

    }
    
    public static void main(String[] args) {
        
        int[] numbers = new int[]{5, 2, 1, 8, 10};
        System.out.println("Max Product: " + max_product(numbers));
    }
}
```

# Week 7; Lecture 10; Linked Lists in Java

A Link List is a series of nodes connected together. We can implement LinkedList from scratch in Java.

`LinkedList.java`
```
package LinkedList_Implementation;

class Node
{
    public int data;
    public Node next;

    public Node(int data)
    {
        this.data = data;
    }
}


public class LinkedList {

    Node head;

    LinkedList()
    {
        this.head = null;
    }

    public void insertElement(int number)
    {
        Node node = new Node(number);

        if (this.head == null)
        {
            this.head = node;
        }
        else
        {
            Node currentNode = this.head;
            while (currentNode.next != null)
            {
                currentNode = currentNode.next;
            }
            currentNode.next = node;
        }
    }
    public void print()
    {
        Node currentNode = this.head;

        while (currentNode != null)
        {
            System.out.println(currentNode.data);
            currentNode = currentNode.next;
        }
    }
    
}
```
`Driver.java`
```
package LinkedList_Implementation;

public class Driver {
    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.insertElement(2);
        list.insertElement(4);
        list.insertElement(6);
        list.insertElement(8);
        list.insertElement(10);

        list.print();
    }
}
```
LinkedList can perform actions like search. Below function returns true if found else false

```
public Boolean search(int number)
    {
        Boolean found = false;

        Node currentNode = this.head;

        while (currentNode != null)
        {
            if (currentNode.data == number)
            {
                found = true;
                break;
            }
            currentNode = currentNode.next;
        }

        return found;
    }
```
We can delete elements from the linkedlist as well.

`LinkedList.java`
```
package LinkedList_Implementation;

class Node
{
    public int data;
    public Node next;

    public Node(int data)
    {
        this.data = data;
    }
}


public class LinkedList {

    Node head;

    LinkedList()
    {
        this.head = null;
    }

    public void insertElement(int number)
    {
        Node node = new Node(number);

        if (this.head == null)
        {
            this.head = node;
        }
        else
        {
            Node currentNode = this.head;
            while (currentNode.next != null)
            {
                currentNode = currentNode.next;
            }
            currentNode.next = node;
        }
    }
    public void print()
    {
        Node currentNode = this.head;

        if (this.head == null)
        {
            System.out.println("List is empty");
        }

        while (currentNode != null)
        {
            System.out.println(currentNode.data);
            currentNode = currentNode.next;
        }
    }

    public Boolean search(int number)
    {
        Boolean found = false;

        Node currentNode = this.head;

        while (currentNode != null)
        {
            if (currentNode.data == number)
            {
                found = true;
                break;
            }
            currentNode = currentNode.next;
        }

        return found;
    }

    public void delete(int number)
    {
        Node currentNode = this.head;
        Node previousNode = this.head;

        if (this.head == null)
        {
            System.out.println("List is empty");
        }

        if (head.data == number)
        {
            this.head = this.head.next;
        }

        while (currentNode != null)
        {
            if (currentNode.data != number)
            {
                previousNode = currentNode;
                currentNode = currentNode.next;
            }
            else
            {
                previousNode.next = currentNode.next;
                currentNode = null;
            }
        }

        
    }
    
}
```
`Driver.java`
```
package LinkedList_Implementation;

public class Driver {
    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.insertElement(2);
        list.insertElement(4);
        list.insertElement(6);
        list.insertElement(8);
        list.insertElement(10);

        System.out.println("Before deleting...");
        list.print();

        list.delete(2);
        list.delete(6);
        list.delete(8);
        list.delete(4);
        list.delete(10);
        System.out.println("After deleting...");
        list.print();
    }
}
```

# Week 7; Lecture 11; Circular and Doubly Linked Lists

Doubly Linkedlist is a type of linkedlist that keeps track of forward and backward nodes.

`LinkedList.java`

```
package Doubly_LinkedList;

class Node
{
    public int data;
    public Node next;
    public Node previous;

    public Node(int data)
    {
        this.data = data;
    }
}


public class LinkedList {

    Node head, tail;

    LinkedList()
    {
        this.head = null;
        this.tail = null;
    }

    public void insertElement(int number)
    {
        Node node = new Node(number);

        if (this.head == null)
        {
            this.head = node;
            this.tail = head;
            this.head.next = null;
            this.head.previous = null;
        }
        else
        {
            Node currentNode = this.head;
            while (currentNode.next != null)
            {
                currentNode = currentNode.next;
            }
            tail = node;
            currentNode.next = tail;
            tail.previous = currentNode;
            tail.next = null;       
        }
    }
    public void printForward()
    {
        Node currentNode = this.head;

        if (this.head == null)
        {
            System.out.println("List is empty");
        }

        while (currentNode != null)
        {
            System.out.println(currentNode.data);
            currentNode = currentNode.next;
        }
    }
```

`Driver.java`
```
package Doubly_LinkedList;

public class Driver {
    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.insertElement(2);
        list.insertElement(4);
        list.insertElement(6);
        list.insertElement(8);
        list.insertElement(10);

        list.printForward();
    }
}
```

One of the advantages of DoublyLinkedList is that you can traverse in the backward direction.
```
public void printBackward()
    {
        Node currentNode = this.tail;

        if (this.tail == null && this.head == null)
        {
            System.out.println("List is empty");
        }

        while (currentNode != null)
        {
            System.out.println(currentNode.data);
            currentNode = currentNode.previous;
        }
    }
```

Java has a built-in LinkedList class with some useful methods. Below is a simple LinkedList

`Driver.java`
```
package LinkedList_Class;

import java.util.LinkedList;

public class Driver {
    
    public static void main(String[] args) {
        LinkedList<Integer> list = new LinkedList<>();
        list.add(2);
        list.add(4);
        list.add(6);
        list.add(8);
        list.add(10);

        System.out.println(list);
    }
}
```
We can remove, add at specific index or modify elements of the linked list

Below will remove elements from a specific index in the list
`list.remove(2);`

Below will add element at a specific index in the list
`list.add(1, 5);`

Below will modify an element at a specific index
`list.set(1, 5);`

Below will help in iterating through the elements of LinkedList
```
for (int item : list)
{
        System.out.println(item);
}
```
LinkedList can be pretty handy in solving some mathematical problems like converting binary to decimal
```
public class Driver {

    public static int convert(LinkedList<Integer> list)
    {
        int result = list.getFirst();

        for (int i = 1; i< list.size(); i++)
        {
            result = result * 2 + list.get(i);
        }
        
        return result;
    }
    public static void main(String[] args) {
        LinkedList<Integer> list = new LinkedList<>();
        list.add(1);
        list.add(0);
        list.add(1);
        list.add(0);

        System.out.println(convert(list));
    }
}
```
To further practice, lets remove duplicates from the LinkedList but by implementing from scratch

`Driver.java`
```
package Remove_Duplicates;

class Node
{
    int value;
    Node next;

    Node(int value)
    {
        this.value = value;
    }

}

public class Driver {

    public static Node deleteDuplicates(Node head)
    {
        Node currentNode = head;

        while (currentNode != null && currentNode.next != null)
        {

            if (currentNode.value == currentNode.next.value)
            {
                currentNode.next = currentNode.next.next;
            }
            else
            {
                currentNode = currentNode.next;
            }

        }
        return head;
    }

    public static void print(Node node)
    {
        Node currentNode = node;

        while(currentNode != null)
        {
            System.out.println(currentNode.value);
            currentNode = currentNode.next;
        }
    }

    public static void main(String[] args) {
        Node head = new Node(1);
        head.next = new Node(1);
        head.next.next = new Node(2);
        head.next.next.next = new Node(2);
        deleteDuplicates(head);
        print(head);
        
    }
    
}
```

# Week 8; Lecture 12; Recursion in Java
Java offers recursion just like C++. The program below uses recursion to find factorial of a number
```
public class Driver {

    public static int factorial(int n)
    {
        if (n <= 1)
        {
            return 1;
        }
        else
        {
            return n * factorial(n - 1);
        }
            // f(4) = 4 x f(3)
            // f(3) = 3 x f(2)
            // f(2) = 2 x f(1)
            // f(1) = 1 x f(0)
            // f(0) = 1
            // f(4) = O(4 + 1) and for f(n) = O(n + 1) = O(n)
    }

    public static void main(String[] args) {

        System.out.println("Factorial: " + factorial(3));
        
    }
}
```

Recursive functions can be expensive when it comes to time complexity
```
    public static int fibonacci(int n)
    {
        if (n <= 1)
        {
            return n;
        }
        else
        {
            return fibonacci(n - 1) + fibonacci(n - 2);
        }         
                //            f(4)           L1  = 1 node = 2^0
                //         /        \      
                //     f(3)        f(2)      L2  = 2 nodes = 2^1
                //    /    \       /   \     
                //  f(2)   f(1)   f(1) f(0)  L3  = 4 nodes = 2^2
               //  /   \   
               // f(1) f(0)                  L4  = 2 nodes because it reached base case so lets ignore this level
               //                            Time Complexity = O(2^n-1) = O(2^n)
    }
    public static void main(String[] args) {
        System.out.println("Fibonacci Number: " + fibonacci(4));
        
    }
```
Power function can also be solved using recursion.
```
    public static int power(int base, int exp)
    {
        if (exp < 0)
        {
            return 0;
        }
        else if (exp == 0)
        {
            return 1;
        }
        else
        {
            return base * power(base, exp-1);
        }
        // p(2^4) = 2 x p(2^3)
        // p(2^3) = 2 x p(2^2)
        // p(2^2) = 2 x p(2^1)
        // p(2^1) = 1
        // O(4) = if exp is 4 and hence if exp is n time complexity will be O(n)
    }
    public static void main(String[] args) {

        System.out.println("Result: " + power(2, 3));
        
    }
```
Power function can be solved without recursion with O(n)
```
    public static int power_simple(int base, int exp)
    {
        int result = 1;
        for (int i=0; i<exp; i++)
        {
            result = result*base;
        }
        return result;
        // Time complexity = O(n)
    }
```
Remove duplicates from LinkedList using Recursion
```
public static Node removeDuplicates(Node node, int value)
    {
        if (node == null)
        {
            return null;
        }

        if (node.value == value)
        {
            return removeDuplicates(node.next, value);
        }
        else
        {
            node.next =  removeDuplicates(node.next, value);
        }
        return node;
	// Time: O(n)
	// Space: O(n)
    }

    public static void print(Node node)
    {
        Node currentNode = node;

        while(currentNode != null)
        {
            System.out.print(currentNode.value + " ");
            currentNode = currentNode.next;
        }
    }

    public static void main(String[] args) {
        
        Node head = new Node(1);
        head.next = new Node(2);
        head.next.next = new Node(3);
        head.next.next.next = new Node(2);
        head.next.next.next.next = new Node(4);

        print(head);
        System.out.println("\nAfter remove duplicates");
        print(removeDuplicates(head, 2));
    }
```
Function can be simplified as:
```
public static Node removeDuplicates(Node node, int value)
    {
        if (node == null)
        {
            return null;
        }

        node.next = removeDuplicates(node.next, value);
        
        if (node.value == value)
        {
            return node.next;
        }
        else
        {
           return node;
        }

    }
```

# Week 8; Lecture 13; Divide and Conquer Algorithm

Divide and Conquer is a technique that is used to split a problem into smaller problems.

Merge Sort is one of such applications that uses Divide and Conquer
```
package MergeSort;

import java.util.Arrays;

public class Driver {

    public static void mergeSort(int[] numbers)
    {
        int size = numbers.length;

        if (size < 2)
        {
            return;
        }

        int mid = size / 2;

        int[] s1 = new int[mid];
        int[] s2 = new int[size - mid];

        // fill in left side array
        for (int i =0; i<mid; i++)
        {
            s1[i] = numbers[i];
        }

        // fill in right side array
        for (int i = mid; i<size; i++)
        {
            s2[i - mid] = numbers[i];
        }

        mergeSort(s1);
        mergeSort(s2);

        merge(numbers, s1, s2);

        // Time Complexity = O(nlogn)
    }

    public static void merge(int numbers[], int s1[], int s2[])
    {
        int s1_size = s1.length;
        int s2_size = s2.length;

        int i = 0, j = 0, k = 0;

        while (i < s1_size && j <s2_size)
        {
            if (s1[i]<=s2[j])
            {
                numbers[k] = s1[i];
                i++;
            }
            else
            {
                numbers[k] = s2[j];
                j++;
            }
            k++;
        }

        while (i < s1_size)
        {
            numbers[k] = s1[i];
            k++;
            i++;
        }
        while (j <s2_size)
        {
            numbers[k] = s2[j];
            k++;
            j++;
        }
    }
    public static void main(String[] args) {
        int[] numbers = new int[] {7, 10, 8, 1, 9, 2, 4, 3};
        System.out.println(Arrays.toString(numbers));
        mergeSort(numbers);
        System.out.println(Arrays.toString(numbers));
    }
}
```
Find Min and Max from array can also be solved using Divide and Conquer
```
package MinMax;

import java.util.Arrays;

public class Driver {

    public static int[] findMinMax(int A[], int start, int end)
    {
        int max;
        int min;
        if ( start == end )
        {
            max = A[start];
            min = A[start];
        }
        else if ( start + 1 == end )
        {
            if ( A[start] < A[end] )
            {
                max = A[end];
                min = A[start];
            }
            else
            {
                max = A[start];
                min = A[end];
            }
        }
        else
        {
            int mid = start + (end - start)/2;
            int left[] = findMinMax(A, start, mid);
            int right[] = findMinMax(A, mid+1, end);
            
            if ( left[0] > right[0] )
                max = left[0];
            else
                max = right[0];
            if ( left[1] < right[1] )
                min = left[1];
            else
                min = right[1];
        }
        int ans[] = {max, min};
        return ans;
    }
    
    public static void main(String[] args) {

        int numbers[] = new int[]{7, 10, 8, 1, 9, 2, 4, 3};

        System.out.println(Arrays.toString(findMinMax(numbers, 0, numbers.length-1)));
        
    }
}
```

# Week 9; Lecture 14; Sorting in Java I
After Bubble Sort, selection sort is one of the simplest sorting algorithms.
```
package Selection_Sort;

import java.util.Arrays;

public class Driver {
    public static void selectionSort(int[] numbers)
    {
        int size = numbers.length;

        for (int i=0; i<size-1; i++)
        {
            int smallest = i;

            for (int j=i+1; j<size; j++)
            {
                if (numbers[smallest] > numbers[j])
                {
                    smallest = j;
                }
            }

            int temp = numbers[smallest];
            numbers[smallest] = numbers[i];
            numbers[i] = temp;
        }
    }
    public static void main(String[] args) {
        int[] numbers = new int[]{7, 10, 8, 1, 9, 2, 4, 3};
        System.out.println(Arrays.toString(numbers));
        selectionSort(numbers);
        System.out.println(Arrays.toString(numbers));
    }
}
```
Another approach to sort is using insertion sort
```
package Insertion_Sort;

import java.util.Arrays;

public class Driver {
    public static void insertionSort(int[] numbers)
    {
        int size = numbers.length;

        for (int i=1; i<size; i++)
        {
            int current = numbers[i];
            int j = i - 1;

            while (j >=0 && current<numbers[j])
            {
                numbers[j+1] = numbers[j];
                j--;
            }
            numbers[j+1] = current;
        }
    }
    public static void main(String[] args) {
        int[] numbers = new int[]{7, 10, 8, 1, 9, 2, 4, 3};
        System.out.println(Arrays.toString(numbers));
        insertionSort(numbers);
        System.out.println(Arrays.toString(numbers));
    }
}
```

Sorting LinkedLists using Selection Sort
```
package LinkedList_Selection_Sort;

class Node
{
    int value;
    Node next;

    Node(int value)
    {
        this.value = value;
    }
}

public class Driver {

    public static void selectionSort(Node head)
    {
        Node pointer = head;
    
        while (pointer != null) 
        {
            Node smallest = pointer;
            Node currentNode = pointer.next;
  
            while (currentNode != null) 
            {
                if (smallest.value > currentNode.value)
                {
                    smallest = currentNode;
                }
                  
                currentNode = currentNode.next;
            }
  
            int temp = pointer.value;
            pointer.value = smallest.value;
            smallest.value = temp;
            pointer = pointer.next;
        }
}

    public static void printList(Node head)
    {
        Node currentNode = head;
        while (currentNode != null) 
        {
            System.out.print(currentNode.value + " ");
            currentNode = currentNode.next;
        }
    }

    public static void main(String[] args) {

        Node head = new Node(5);
        head.next = new Node(1);
        head.next.next = new Node(7);
        head.next.next.next = new Node(3);
        head.next.next.next.next = new Node(4);

        printList(head);
        System.out.println();
        selectionSort(head);
        printList(head);
        
    }
}
```

# Week 9; Lecture 15; Advanced Sorting in Java
One of quickest ways of sorting is Quick Sort that uses pivot for sorting. It is also an example of Divide and Conquer where collections are first partitioned into smaller collections and then they are recursively sorted.
```
package Quick_Sort;

import java.util.Arrays;

public class Driver {

    public static void swap(int[] numbers, int i, int j)
    {
        int temp = numbers[i];
        numbers[i] = numbers[j];
        numbers[j] = temp;
    }
    public static int partition(int[] numbers, int start, int end)
    {
        int pivot = numbers[end];
        int i = start - 1;

        for (int j=start; j<end; j++)
        {
            if (numbers[j] < pivot)
            {
                i++;
                // Swapping numbers smaller than pivot
                int temp = numbers[i];
                numbers[i] = numbers[j];
                numbers[j] = temp;
            }
        }
        i++;
        //Swapping pivot with the last number next to smaller numbers
        int temp = numbers[i];
        numbers[i] = pivot;
        numbers[end] = temp;
        return i;
    }

    public static void quickSort(int[] numbers, int start, int end)
    {
        if (start < end)
        {
            int pivotIndex = partition(numbers, start, end);
            quickSort(numbers, start, pivotIndex - 1);
            quickSort(numbers, pivotIndex + 1, end);
        }
    }
    public static void main(String[] args) {
        int[] numbers = new int[]{8, 2, 7, 3, 10, 15, 6};
        System.out.println(Arrays.toString(numbers));
        quickSort(numbers, 0, numbers.length-1);
        System.out.println(Arrays.toString(numbers));
    }
}
```
Sorting String using Quick Sort
```
import java.util.Arrays;

public class Driver {

    public static int partition(String[] strings, int start, int end)
    {
        String pivot = strings[end];
        int i = start - 1;

        for (int j=start; j<end; j++)
        {
            if (strings[j].compareTo(pivot) < 0)
            {
                i++;
                // Swapping numbers smaller than pivot
                String temp = strings[i];
                strings[i] = strings[j];
                strings[j] = temp;
            }
        }
        i++;
        //Swapping pivot with the last number next to smaller numbers
        String temp = strings[i];
        strings[i] = pivot;
        strings[end] = temp;
        return i;
    }

    public static void quickSort(String[] strings, int start, int end)
    {
        if (start < end)
        {
            int pivotIndex = partition(strings, start, end);
            quickSort(strings, start, pivotIndex - 1);
            quickSort(strings, pivotIndex + 1, end);
        }
    }
    public static void main(String[] args) {

        String[] strings = new String[]{"Toronto", "Ottawa", "Oshawa", "Whitby", "Ajax"};
        System.out.println(Arrays.toString(strings));
        quickSort(strings, 0, strings.length-1);
        System.out.println(Arrays.toString(strings));
        
    }
}
```
Sorting string by length using Quick Sort
```
public class Driver {

    public static int partition(String[] strings, int start, int end)
    {
        String pivot = strings[end];
        int i = start - 1;

        for (int j=start; j<end; j++)
        {
            if (strings[j].length() < pivot.length())
            {
                i++;
                // Swapping numbers smaller than pivot
                String temp = strings[i];
                strings[i] = strings[j];
                strings[j] = temp;
            }
        }
        i++;
        //Swapping pivot with the last number next to smaller numbers
        String temp = strings[i];
        strings[i] = pivot;
        strings[end] = temp;
        return i;
    }

    public static void quickSort(String[] strings, int start, int end)
    {
        if (start < end)
        {
            int pivotIndex = partition(strings, start, end);
            quickSort(strings, start, pivotIndex - 1);
            quickSort(strings, pivotIndex + 1, end);
        }
    }
    public static void main(String[] args) {

        String[] strings = new String[]{"abcd", "ab", "abc", "abcde", "a"};
        System.out.println(Arrays.toString(strings));
        quickSort(strings, 0, strings.length-1);
        System.out.println(Arrays.toString(strings));
        
    }
}
```
Sort a String Sentence
```
package Sort_Sentence;

public class Driver {

    public static String sortSentence(String sentence)
    {
        String[] words = sentence.split(" ");
        String[] answer = new String[words.length];

        for (String word: words)
        {
            int i = word.length() - 1;
            int index = word.charAt(i) - '0';
            answer[index-1] = word.substring(0, i);
        }
        return String.join(" ", answer);
    }
    public static void main(String[] args) {
        System.out.println(sortSentence("is2 sentence4 This1 a3"));
    }
}
```

# Week 10; Lecture 16; Trees and Binary Search Trees
Binary Search Trees can be implemented using recursive and iterative approach. Below is the iterative approach

`BinarySearchTree.java`
```
class Node
{
    int value;
    Node left;
    Node right;

    Node(int value)
    {
        this.value = value;
    }
}

public class BinarySearchTree 
{
    Node root;

    public void insertNode(int value)
    {
        Node node = new Node(value);

        if (root == null)
        {
            root = node;
        }
        else
        {
            Node currentNode = root;
            Node parent;
            while (true)
            {
                parent = currentNode;
                if (value < currentNode.value)
                {
                    currentNode = currentNode.left;
                    if (currentNode == null)
                    {
                        parent.left = node;
                        return;
                    }
                }
                else
                {
                    currentNode = currentNode.right;
                    if (currentNode == null)
                    {
                        parent.right = node;
                        return;
                    }
                }
            }
        }

        // Time Complexity if O(n)
        // Space Complexity is O(n)
    }

    public void printNodes()
    {
        Stack<Node> stack = new Stack<>();
        Node currentNode = root;

        while (currentNode!=null || !stack.empty())
        {
            if (currentNode!=null)
            {
                stack.push(currentNode);
                currentNode = currentNode.left;
            }
            else
            {
                currentNode = stack.pop();
                System.out.println(currentNode.value);
                currentNode = currentNode.right;
            }
        }

        // Time Complexity if O(n)
        // Space Complexity is O(n)
    }

}
```
`Driver.java`
```
package BST;


public class Driver {


    public static void main(String[] args) {
        BinarySearchTree tree = new BinarySearchTree();
        tree.insertNode(5);
        tree.insertNode(10);
        tree.insertNode(2);
        tree.insertNode(11);
        tree.insertNode(1);
        tree.insertNode(3);
        tree.insertNode(20);
        tree.insertNode(15);
        tree.insertNode(90);

        tree.printNodes();
    }
}
```
Binary Search Trees are very efficient when it comes to searching
```
public Node search(int value)
    {
        Node currentNode = root;

        while (currentNode.value != value)
        {
            if (value < currentNode.value)
            {
                currentNode = currentNode.left;
            }
            else
            {
                currentNode = currentNode.right;
            }

            if (currentNode == null)
            {
                return null;
            }
        }
        return currentNode;

        // Time Complexity: O(logn)
        // Space Complexity: O(n)
    }
```
Recursion can be used to simplify the code for insertion as below:
```
public void insertion(int value)
    {
        root = insertNode_recursion(root, value);
    }

    public Node insertNode_recursion(Node root, int value)
    {
        if (root == null)
        {
            root = new Node(value);
            return root;
        }
        else if (value < root.value)
        {
            root.left = insertNode_recursion(root.left, value);
        }
        else
        {
            root.right = insertNode_recursion(root.right, value);
        }
        return root;
    }
```
Recursion can be used for Search as well
```
public Node search_recursion(Node root, int value)
    {
        if (root == null || root.value == value)
        {
            return root;
        }
        if (value < root.value)
        {
            return search_recursion(root.left, value);
        }
        else
        {
            return search_recursion(root.right, value);
        }
    }

    public void search_it(int value)
    {
        if (search_recursion(root, value) == null)
        {
            System.out.println("\nElement not found");
        }
        else
        {
            System.out.println("\nElement found");
        }
    }
```

# Week 10; Lecture 17; Binary Tree Traversals

Tree traversals can be level wise which is also called Breadth First Traversals
```
public static void levelOrder(Node root)
    {
        LinkedList<Node> list = new LinkedList<>();
        list.add(root);

        while (!list.isEmpty())
        {
            Node currentNode = list.poll();
            System.out.print(currentNode.value + " ");

            if (currentNode.left != null)
            {
                list.add(currentNode.left);
            }
            if (currentNode.right != null)
            {
                list.add(currentNode.right);
            }
        }
    }
```
Traversals can be Depth First as well which are pre-order, in-order and post-order
```
public static void preOrder(Node root)
    {
        if (root == null)
        {
            return;
        }
        System.out.print(root.value + " ");
        preOrder(root.left);
        preOrder(root.right);
    }

    public static void inOrder(Node root)
    {
        if (root == null)
        {
            return;
        }
        inOrder(root.left);
        System.out.print(root.value + " ");
        inOrder(root.right);
    }

    public static void postOrder(Node root)
    {
        if (root == null)
        {
            return;
        }
        postOrder(root.left);
        postOrder(root.right);
        System.out.print(root.value + " ");

    }
```
Above functions can be used with the following main method
```
public static void main(String[] args) {

        Node root = new Node(5);
        root.left = new Node(3);
        root.right = new Node(15);
        root.left.left = new Node(2);
        root.left.right = new Node(4);
        root.right.left = new Node(12);
        root.right.right = new Node(25);

        System.out.println("Level Order Traversal");
        levelOrder(root);

        System.out.println("\nPre Order traversal:");
        preOrder(root);
        
        System.out.println("\nIn Order traversal:");
        inOrder(root);

        System.out.println("\nIn Post traversal:");
        postOrder(root);

    }
}
```
Deleting a node from the tree is pretty complicated. Deleting a node with no children is the easiest.
```
public static boolean delete(Node root, int value)
    {
        Node currentNode = root;
        Node parent = root;
        boolean isLeft = false;

        while (currentNode.value != value)
        {
            parent = currentNode;
            if (value < currentNode.value)
            {
                isLeft = true;
                currentNode = currentNode.left;
            }
            else
            {
                isLeft = false;
                currentNode = currentNode.right;
            }
            if (currentNode == null)
            {
                return false;
            }
        }

        if (currentNode.left == null && currentNode.right == null)
        {
            if (currentNode == root)
            {
                root = null;
            }
            else 
            {
                if (isLeft)
                {
                    parent.left = null;
                }
                else
                {
                    parent.right = null;
                }
            }
        }
        return true;
    }
```
All above examples use following Node class
```
class Node
{
    int value;
    Node left;
    Node right;

    Node(int value)
    {
        this.value = value;
    }
}
```

# Week 11; Lecture 18; AVL Trees (Balanced Trees)
AVL trees help solving worst case scenario of Binary Search Trees

`AVL_Tree.java`
```
package AVL_Tree;

class Node
{
    int value;
    int height;
    Node left;
    Node right;

    Node(int value)
    {
        this.value = value;
        height = 1;
    }
}

public class AVL {
    
    Node root;

    void insertion(int value)
    {
        root = insertNode(root, value);
    }

    Node insertNode(Node node, int value)
    {
        if (node == null)
        {
            return new Node(value);
        }
        if (value < node.value)
        {
            node.left = insertNode(node.left, value);
        }
        else if (value > node.value)
        {
            node.right = insertNode(node.right, value);
        }
        else
        {
            return node;
        }
        node.height = getMax(getHeight(node.left), getHeight(node.right)) + 1;
        int balanceFactor = getBalanceFactor(node);

        if (balanceFactor > 1)
        {
            if (value < node.left.value)
            {
                return rightRotate(node);
            }
            else
            {
                node.left = leftRotate(node.left);
                return rightRotate(node);
            }
        }
        if (balanceFactor < -1)
        {
            if (value > node.right.value)
            {
                return leftRotate(node);
            }
            else
            {
                node.right = rightRotate(node.right);
                return leftRotate(node);
            }
        }
        return node;
    }
    Node rightRotate(Node node)
    {
        Node newRoot = node.left;
        node.left = newRoot.right;
        newRoot.right = node;
        node.height = getMax(getHeight(node.left), getHeight(node.right)) + 1;
        newRoot.height = getMax(getHeight(newRoot.left), getHeight(newRoot.right)) + 1;
        return newRoot;
    }
    Node leftRotate(Node node)
    {
        Node newRoot = node.right;
        node.right = newRoot.left;
        newRoot.left = node;
        node.height = getMax(getHeight(node.left), getHeight(node.right)) + 1;
        newRoot.height = getMax(getHeight(newRoot.left), getHeight(newRoot.right)) + 1;
        return newRoot;
    }
    int getHeight(Node node)
    {
        if (node == null)
        {
            return 0;
        }
        return node.height;
    }
    int getMax(int a, int b)
    {
        return (a > b) ? a : b;
    }
    int getBalanceFactor(Node node)
    {
        if (node == null)
        {
            return 0;
        }
        return getHeight(node.left) - getHeight(node.right);
    }
    void preOrder(Node node)
    {
        if (node == null)
        {
            return;
        }
        else
        {
            System.out.println(node.value + " ");
            preOrder(node.left);
            preOrder(node.right);
        }
    }
    
}
```
`Driver.java`
```
package AVL_Tree;

public class Driver {
    public static void main(String[] args) {
        AVL tree = new AVL();
        tree.insertion(10);
        tree.insertion(20);
        tree.insertion(30);
        tree.insertion(40);
        tree.insertion(50);
        tree.insertion(25);
        tree.preOrder(tree.root);
    }
}
```

# Week 12; Lecture 19; Hashing - HashMap

Hashmaps are used to improve efficiency while searching

`HashMap.java`
```
package HashMaps;

class Node
{
    int key;
    int value;
    Node next;

    Node(int key, int value)
    {
        this.key = key;
        this.value = value;
    }
    int getValue()
    {
        return this.value;
    }
    int getKey()
    {
        return this.key;
    }
    void setValue(int value)
    {
        this.value = value;
    }
}

public class HashMap {

    Node table[];
    int size;

    HashMap(int size)
    {
        this.size = size;
        table = new Node[size];
    }

    void put(int key, int value)
    {
        int hash = key % size;

        Node node = table[hash];

        if (node == null)
        {
            table[hash] = new Node(key, value);
        }
        else
        {
            while (node.next != null)
            {
                // update the value of the key
                if (node.getKey() == key)
                {
                    node.setValue(value);
                    return;
                }
                node = node.next;
            }

            if (node.getKey() == key)
            {
                node.setValue(value);
                return;
            }
            node.next = new Node(key, value);
        }
    }
    
    int get(int key)
    {
        int hash = key % size;
        Node node = table[hash];

        if (node == null)
        {
            return -1;
        }

        while (node != null)
        {
            if (node.getKey() == key)
            {
                return node.getValue();
            }
            node = node.next;
        }
        return -1;
    }
    
}
```

`Driver.java`
```
package HashMaps;

public class Driver {
    public static void main(String[] args) {
        HashMap map = new HashMap(10);
        map.put(1, 25);
        map.put(2, 38);
        map.put(3, 46);
        map.put(4, 59);
        map.put(5, 94);
        map.put(1, 98);
        int value = 381;
        int key = 6;

        
        if ((value = map.get(key)) == -1)
        {
            System.out.println("No value found at that key");
        }
        else
        {
            System.out.printf("Value at %d: %d", key, value);
        }
    }
}
```
Java has a built in HashMap as well.
```
package HashMaps_Java;

import java.util.HashMap;

public class Driver {
    public static void main(String[] args) {
        HashMap<Integer, String> map = new HashMap<>();
        map.put(1, "Steve Jobs");
        map.put(2, "Bill Gates");
        map.put(3, "Elon Musk");
        map.put(4, "Jeff Bezos");
        
        System.out.println(map);

        System.out.println(map.get(2));

        System.out.println(map.containsValue("Bill Gates"));
        

    }
}
```

Find occurrences of characters in a string
```
package Good_String;

import java.util.HashMap;

public class Driver {

    public static boolean areOccurrencesEqual(String s) 
    {
        HashMap<Character, Integer> map = new HashMap<>();

        for (char ch: s.toCharArray())
        {
            map.put(ch, map.getOrDefault(ch, 0) + 1);
        }

        for (char key: map.keySet())
        {
            if (map.get(key) != map.get(s.charAt(0)))
            {
                return false;
            }
        }
        return true;
    }
    public static void main(String[] args) {
        String string = new String("abbaccd");

        if (areOccurrencesEqual(string))
        {
            System.out.println("Good String");
        }
        else
        {
            System.out.println("Bad String");
        }
    }
}
```