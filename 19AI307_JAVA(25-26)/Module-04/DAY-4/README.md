

# Ex.No:4(D) DESIGN PATTERN -- ABSTRACT FACTORY

## QUESTION:
You are asked to simulate a simple Shape Drawing Tool using the abstract Factory Design Pattern in Java.

You will implement a Shape interface with concrete classes for different shapes (Circle, Square, Rectangle). Using a ShapeFactory, your program will take shape names from user input and draw them accordingly. If the shape is unknown, print an error message.



## AIM:
To write a Java program that implements the Factory Design Pattern to create and draw shapes dynamically based on user input.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a Shape interface containing a draw() method.
4. Create concrete classes Circle, Square, and Rectangle implementing Shape.
5. Create a ShapeFactory class with a method getShape(String shapeType).
6. In the main() method, accept user input for shape type.
7. Call factory method to get the appropriate object.
8. Draw the shape or print error if unknown.
9. Stop the program.


## PROGRAM:
 ```
/*
Program to implement variables and Operators using Java
Developed by:  MANASA S
RegisterNumber: 212224220059
*/
```

## SOURCE CODE:
```
import java.util.Scanner;

// ===== Abstract Product =====
interface Shape {
    void draw();
}

// ===== Concrete Products =====
class Circle implements Shape {
    public void draw() {
        System.out.println("Drawing Circle");
    }
}

class Square implements Shape {
    public void draw() {
        System.out.println("Drawing Square");
    }
}

class Rectangle implements Shape {
    public void draw() {
        System.out.println("Drawing Rectangle");
    }
}

// ===== Abstract Factory =====
interface ShapeFactory {
    Shape createShape();
}

// ===== Concrete Factories =====
class CircleFactory implements ShapeFactory {
    public Shape createShape() {
        return new Circle();
    }
}

class SquareFactory implements ShapeFactory {
    public Shape createShape() {
        return new Square();
    }
}

class RectangleFactory implements ShapeFactory {
    public Shape createShape() {
        return new Rectangle();
    }
}

// ===== Main =====
public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        while (true) {
            String input = sc.nextLine().trim();

            if (input.equalsIgnoreCase("exit")) {
                break;
            }

            ShapeFactory factory;

            switch (input.toLowerCase()) {
                case "circle":
                    factory = new CircleFactory();
                    break;

                case "square":
                    factory = new SquareFactory();
                    break;

                case "rectangle":
                    factory = new RectangleFactory();
                    break;

                default:
                    System.out.println("Invalid shape: " + input);
                    continue;
            }

            Shape shape = factory.createShape();
            shape.draw();
        }

        sc.close();
    }
}
```






## OUTPUT:

![java44](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/b628a27d8352a971924fad5b0adffc7f5f8644ba/19AI307_JAVA(25-26)/Module-04/DAY-4/java44.png)

## RESULT:
Thus, the Java program to simulate Shape Drawing using the Factory Design Pattern was successfully implemented and executed.
