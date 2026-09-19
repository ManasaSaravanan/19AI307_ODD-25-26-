


# Ex.No:4(D) DESIGN PATTERN  ---- BEHAVIOUR PATTERN

## QUESTION:
Create a program that sends different types of notifications: "email", "sms", and "push". Use the Factory Pattern to generate the appropriate notification sender and call its notifyUser() method.



## AIM:
To write a Java program that demonstrates a Behavioral Pattern using the Factory Method, allowing different notification types to send messages through a common interface.

## ALGORITHM :

1. Start the program.

2. Create a Notification interface with the notifyUser() method.

3. Create concrete notification classes:
   a) EmailNotification
   b) SMSNotification
   c) PushNotification

4. Implement the notifyUser() method in each notification class.

5. Create a NotificationContext class to store the selected notification strategy.

6. Read the notification type from the user.

7. Check the input notification type:
   a) If the input is "email", select EmailNotification.
   b) If the input is "sms", select SMSNotification.
   c) If the input is "push", select PushNotification.

8. Set the selected notification strategy in the NotificationContext.

9. Call the sendNotification() method to execute the selected notification.

10. If the input is invalid, display "Invalid notification type".

11. Repeat the process until the user enters "exit".

12. Stop the program.





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

// ===== Strategy Interface =====
interface Notification {
    void notifyUser();
}

// ===== Concrete Strategies =====
class EmailNotification implements Notification {
    public void notifyUser() {
        System.out.println("Sending Email Notification");
    }
}

class SMSNotification implements Notification {
    public void notifyUser() {
        System.out.println("Sending SMS Notification");
    }
}

class PushNotification implements Notification {
    public void notifyUser() {
        System.out.println("Sending Push Notification");
    }
}

// ===== Context =====
class NotificationContext {
    private Notification notification;

    public void setNotification(Notification notification) {
        this.notification = notification;
    }

    public void sendNotification() {
        if (notification != null) {
            notification.notifyUser();
        }
    }
}

// ===== Main =====
public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        NotificationContext context = new NotificationContext();

        while (true) {
            String input = sc.nextLine().trim();

            if (input.equalsIgnoreCase("exit")) {
                break;
            }

            switch (input.toLowerCase()) {
                case "email":
                    context.setNotification(new EmailNotification());
                    break;

                case "sms":
                    context.setNotification(new SMSNotification());
                    break;

                case "push":
                    context.setNotification(new PushNotification());
                    break;

                default:
                    System.out.println("Invalid notification type: " + input);
                    continue;
            }

            context.sendNotification();
        }

        sc.close();
    }
}
```






## OUTPUT:

![java45](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/c6316a5904f4a174dd995f6b7d7c47b65f677921/19AI307_JAVA(25-26)/Module-04/DAY-5/java45.png)

## RESULT:
Thus, the program demonstrating the Behavioral Pattern using Factory Method to generate different notification types was successfully implemented and executed.



