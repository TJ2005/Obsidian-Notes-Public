---
Title: "Object Oriented Programming Lab 6"
Status: 
marker: 
tags: 
Date: "2025.03.06"
Time: "14:35"
---
# Object Oriented Programming Lab 6


## Question 1
Write a method that checks whether a string is a valid password. Suppose the password rule is as follows:
- **A password must have at least eight characters.**
- **A password consists of only letters and digits.**    
- **A password must contain at least two digits.**
Write a program that prompts the user to enter a password and displays:
- `"Valid Password"` if the rule is followed.
- `"Invalid Password"` otherwise.

```java
import java.util.Scanner;

  

public class Question1 {

    public static void main(String[] args) {

        // New scanner object

        Scanner input = new Scanner(System.in);

        // Use Outstream to print

        System.out.print("Enter a password: ");

        // Read the input from the user

        String password = input.nextLine();

        // Use method to check if the password is valid

        // Method returns true or false

        if (isValidPassword(password)) {

            System.out.println("Valid Password");

        } else {

            System.out.println("Invalid Password");

        }

    }

  

    public static boolean isValidPassword(String password) {

        if (password.length() < 8) {

            return false;

        }

  

        int digitCount = 0;

        for (int i = 0; i < password.length(); i++) {

            char ch = password.charAt(i);

            if (!Character.isLetterOrDigit(ch)) {

                return false;

            }

            if (Character.isDigit(ch)) {

                digitCount++;

            }

        }

  

        return digitCount >= 2;

    }

}
```

```bash
C:\Users\TJ\prog\temp\oop\lab6> cmd /C ""C:\Program Files\Eclipse Adoptium\jdk-17.0.13.11-hotspot\bin\java.exe" -XX:+ShowCodeDetailsInExceptionMessages -cp C:\Users\TJ\AppData\Roaming\Code\User\workspaceStorage\d2a52ffeb54559066c2ca7364c09ef79\redhat.java\jdt_ws\lab6_8ba73fe8\bin Question1 "
Enter a password: ILoveCats@2005
Invalid Password

C:\Users\TJ\prog\temp\oop\lab6> cmd /C ""C:\Program Files\Eclipse Adoptium\jdk-17.0.13.11-hotspot\bin\java.exe" -XX:+ShowCodeDetailsInExceptionMessages -cp C:\Users\TJ\AppData\Roaming\Code\User\workspaceStorage\d2a52ffeb54559066c2ca7364c09ef79\redhat.java\jdt_ws\lab6_8ba73fe8\bin Question1 "
Enter a password: ILoveCats2005
Valid Password
```

## Question 2
Create a class named Aircraft with data members being aircraft name and their respective speed. Implement member functions to display the aircraft object and also to find the aircraft with top speed. Demonstrate the working by creating array of objects for Aircraft class.

## Some Websites Impose Certain Rules for Passwords

Write a method that checks whether a string is a valid password. Suppose the password rule is as follows:

- **A password must have at least eight characters.**
    
- **A password consists of only letters and digits.**
    
- **A password must contain at least two digits.**
    

Write a program that prompts the user to enter a password and displays:

- `"Valid Password"` if the rule is followed.
    
- `"Invalid Password"` otherwise.
```java
public class Question2 {
    public static void main(String[] args) {
        Aircraft[] aircrafts = new Aircraft[6];

        aircrafts[0] = new Aircraft("Gulfstream Private Jet", 673);
        aircrafts[1] = new Aircraft("F-16 Fighter Jet", 1500);
        aircrafts[2] = new Aircraft("Cessna Sea Plane", 1100);
        aircrafts[3] = new Aircraft("Bell 407 Helicopter", 160);
        aircrafts[4] = new Aircraft("Boeing 777", 644);
        aircrafts[5] = new Aircraft("Glider", 150);

        System.out.println("         Aircrafts in Array");
        System.out.println("*********************************");
        System.out.printf("%-25s %-10s%n", "Aircraft", "Top Speed");
        System.out.println("---------------------------------");

        for (Aircraft aircraft : aircrafts) {
            System.out.printf("%-25s %-10d%n", aircraft.getName(), aircraft.getSpeed());
        }

        Aircraft topSpeedAircraft = findTopSpeedAircraft(aircrafts);

        System.out.println("\nAircraft with fastest top speed in the array of aircraft");
        System.out.println("-------------------------------------------");
        System.out.printf("Aircraft:  %-25s%n", topSpeedAircraft.getName());
        System.out.printf("Top Speed: %-10d%n", topSpeedAircraft.getSpeed());
    }

    public static Aircraft findTopSpeedAircraft(Aircraft[] aircrafts) {
        Aircraft topSpeedAircraft = aircrafts[0];
        for (Aircraft aircraft : aircrafts) {
            if (aircraft.getSpeed() > topSpeedAircraft.getSpeed()) {
                topSpeedAircraft = aircraft;
            }
        }
        return topSpeedAircraft;
    }
}

class Aircraft {
    private String name;
    private int speed;

    public Aircraft(String name, int speed) {
        this.name = name;
        this.speed = speed;
    }

    public String getName() {
        return name;
    }

    public int getSpeed() {
        return speed;
    }
}

```

```bash
C:\Users\TJ\prog\temp\oop\lab6> c: && cd c:\Users\TJ\prog\temp\oop\lab6 && cmd /C ""C:\Program Files\Eclipse Adoptium\jdk-17.0.13.11-hotspot\bin\java.exe" -XX:+ShowCodeDetailsInExceptionMessages -cp C:\Users\TJ\AppData\Roaming\Code\User\workspaceStorage\d2a52ffeb54559066c2ca7364c09ef79\redhat.java\jdt_ws\lab6_8ba73fe8\bin Question2 "
         Aircrafts in Array
*********************************
Aircraft                  Top Speed 
---------------------------------
Gulfstream Private Jet    673       
F-16 Fighter Jet          1500      
Cessna Sea Plane          1100      
Bell 407 Helicopter       160       
Boeing 777                644       
Glider                    150       

Aircraft with fastest top speed in the array of aircraft
-------------------------------------------
Aircraft:  F-16 Fighter Jet
Top Speed: 1500

```
## Question 3
In a sports shop, there are four types of rackets available, such as, voltric, nanoray, astrox, and carbonex. Each of these types has different country of origin, price, and colour. These fields are kept private to an inner class called Rackets. Create a class called Shopkeeper and there create an array of four instances (voltric, nanoray, astrox, and carbonex) of Rackets. From Shopkeeper class initialize each field of all the instances by invoking methods defined in Rackets and also show the details of the rackets. Find which one has the lowest cost

```java
public class Shopkeeper {

    // Inner class Rackets
    private class Rackets {
        private String name;
        private String countryOfOrigin;
        private double price;
        private String color;

        // Constructor to initialize fields
        public Rackets(String name, String countryOfOrigin, double price, String color) {
            this.name = name;
            this.countryOfOrigin = countryOfOrigin;
            this.price = price;
            this.color = color;
        }

        // Display method
        public void display() {
            System.out.printf("%-10s %-15s %-10.2f %-10s%n", name, countryOfOrigin, price, color);
        }

        public double getPrice() {
            return price;
        }

        public String getName() {
            return name;
        }
    }

    public static void main(String[] args) {
        Shopkeeper shopkeeper = new Shopkeeper();
        shopkeeper.displayRackets();
    }

    public void displayRackets() {
        Rackets[] rackets = {
            new Rackets("Voltric", "Japan", 120.50, "Red"),
            new Rackets("Nanoray", "China", 95.75, "Blue"),
            new Rackets("Astrox", "Taiwan", 150.00, "Black"),
            new Rackets("Carbonex", "India", 85.30, "Green")
        };

        System.out.println("          Rackets in Sports Shop");
        System.out.println("********************************************");
        System.out.printf("%-10s %-15s %-10s %-10s%n", "Name", "Country", "Price", "Color");
        System.out.println("--------------------------------------------");

        for (Rackets racket : rackets) {
            racket.display();
        }

        Rackets cheapestRacket = findCheapestRacket(rackets);
        
        System.out.println("\nRacket with the lowest price:");
        System.out.println("------------------------------");
        System.out.printf("Name:   %-10s%n", cheapestRacket.getName());
        System.out.printf("Price:  $%-10.2f%n", cheapestRacket.getPrice());
    }

    public Rackets findCheapestRacket(Rackets[] rackets) {
        Rackets cheapest = rackets[0];
        for (Rackets racket : rackets) {
            if (racket.getPrice() < cheapest.getPrice()) {
                cheapest = racket;
            }
        }
        return cheapest;
    }
}

```

```bash
C:\Users\TJ\prog\temp\oop\lab6> cmd /C ""C:\Program Files\Eclipse Adoptium\jdk-17.0.13.11-hotspot\bin\java.exe" -XX:+ShowCodeDetailsInExceptionMessages -cp C:\Users\TJ\AppData\Roaming\Code\User\workspaceStorage\d2a52ffeb54559066c2ca7364c09ef79\redhat.java\jdt_ws\lab6_8ba73fe8\bin Question3 "
          Rackets in Sports Shop
********************************************
Name       Country         Price      Color     
--------------------------------------------
Voltric    Japan           120.50     Red       
Nanoray    China           95.75      Blue      
Astrox     Taiwan          150.00     Black     
Carbonex   India           85.30      Green     

Racket with the lowest price:
------------------------------
Name:   Carbonex
Price:  $85.30
```
# References


###### Information
- date: 2025.03.06
- time: 14:35