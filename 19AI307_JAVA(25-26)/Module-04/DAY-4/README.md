# Ex.No:4(D) DESIGN PATTERN -- FACTORY

## QUESTION:

Create a program that sends different types of notifications: "email", "sms", and "push". Use the Factory Pattern to generate the appropriate notification sender and call its notifyUser() method.

## AIM:

To develop a Java program that uses the Factory Pattern to generate different types of notifications—Email, SMS, and Push—and call the appropriate notifyUser() method based on user input.

## ALGORITHM :

Define a Notification interface with a method notifyUser().

Implement three classes EmailNotification, SMSNotification, and PushNotification, each overriding notifyUser() with specific behavior.

Create a NotificationFactory class containing a method createNotification(String type) that:

Returns an EmailNotification object when type is "email".

Returns an SMSNotification object when type is "sms".

Returns a PushNotification object when type is "push".

Returns null for invalid types.

Create a NotificationFactory object.

Read user input in a loop until "exit" is entered.

Use the factory to create the correct notification object.

If the object is valid, call notifyUser(); otherwise print an error message.

Close the scanner after exiting the loop.



## PROGRAM:
 ```
/*
Program to implement a Abstract Factory Pattern using Java
Developed by: KUSHMA S
RegisterNumber: 212224040168 
*/
```

## SOURCE CODE:

    import java.util.Scanner;
    
    interface Notification {
        void notifyUser();
    }
    
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
    
    class NotificationFactory {
        public Notification createNotification(String type) {
            if (type == null) return null;
            if (type.equalsIgnoreCase("email")) return new EmailNotification();
            else if (type.equalsIgnoreCase("sms")) return new SMSNotification();
            else if (type.equalsIgnoreCase("push")) return new PushNotification();
            return null;
        }
    }
    
    public class Main {
        public static void main(String[] args) {
            Scanner sc = new Scanner(System.in);
            NotificationFactory factory = new NotificationFactory();
            while (true) {
                String input = sc.nextLine();
                if (input.equalsIgnoreCase("exit")) break;
                Notification n = factory.createNotification(input);
                if (n != null) n.notifyUser();
                else System.out.println("Invalid notification type: " + input);
            }
            sc.close();
        }
    }



## OUTPUT:

<img width="1007" height="417" alt="image" src="https://github.com/user-attachments/assets/a2f4fb47-6a7f-417d-a5a9-ffcee9e08641" />


## RESULT:
Therefore the program successfully creates and sends the appropriate notification type using the Factory Pattern.

