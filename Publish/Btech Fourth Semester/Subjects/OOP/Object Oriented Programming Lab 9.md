---
Title: "Object Oriented Programming Lab 7"
Status: 
marker: 
tags: 
Date: "2025.03.27"
Time: "15:04"
---
# Object Oriented Programming Lab 7
## Question 1
$$\LaTeX \text{ is being generated... } \vphantom{10}$$
![](https://i.imgur.com/CkZW6AL.png)
Test run the program with employee record **being [89, ”Steve”,”Jackson”,3000]** , the resultant annual employee record with a percent hike of 10% in salary should be **[89, ”Steve”,”Jackson”,396000].**
```java
public class Question1 {

    public class Employee {

        int id;

        String firstname;

        String lastname;

        int salary;

  

        Employee(int id, String firstname, String lastname, int salary) {

            this.id = id;

            this.firstname = firstname;

            this.lastname = lastname;

            this.salary = salary;

        }

  

        public int getID() {

            return id;

        }

  

        public String getFirstName() {

            return firstname;

        }

  

        public String getLastName() {

            return lastname;

        }

  

        public String getName() {

            return firstname + " " + lastname;

        }

  

        public int getSalary() {

            return salary;

        }

  

        public int getAnnualSalary() {

            return salary * 12;

        }

  

        public void raiseSalary(int percent) {

            salary = salary + (salary * percent / 100);

        }

  

        public String toString() {

            return "Employee[id=" + id + ", name=" + getName() + ", salary=" + salary + "]";

        }

    }

  

    public static void main(String[] args) {

        Question1 outer = new Question1();

        Employee emp = outer.new Employee(89, "Steve", "Jackson", 3000);

  

        System.out.println("Before raise: " + emp);

        emp.raiseSalary(10);

        System.out.println("After raise: " + emp);

        System.out.println("Annual Salary: " + emp.getAnnualSalary());

    }

}
```

```bash

C:\Users\TJ\prog\temp\oop\lab7> cmd /C ""C:\Program Files\Eclipse Adoptium\jdk-17.0.13.11-hotspot\bin\java.exe" -XX:+ShowCodeDetailsInExceptionMessages -cp C:\Users\TJ\AppData\Roaming\Code\User\workspaceStorage\095ef1e73c8fb7098a9f0aa9a9e9b786\redhat.java\jdt_ws\lab7_8ba73fe9\bin Question1 "
Before raise: Employee[id=89, name=Steve Jackson, salary=3000]
After raise: Employee[id=89, name=Steve Jackson, salary=3300]
Annual Salary: 39600
```

## Question 2
Design and implement classes as shown in the Class diagram below. Write a test program to test the classes created.
![](https://i.imgur.com/XI00cgN.png)

```java
// Base class: Person

public class Question2 {

  

    // Inner Person class

    public static class Person {

        private String name;

        private String address;

  

        // Constructor

        public Person(String name, String address) {

            this.name = name;

            this.address = address;

        }

  

        // Getters and Setters

        public String getName() {

            return name;

        }

  

        public String getAddress() {

            return address;

        }

  

        public void setAddress(String address) {

            this.address = address;

        }

  

        // toString method

        @Override

        public String toString() {

            return "Person[name=" + name + ", address=" + address + "]";

        }

    }

  

    // Subclass: Student

    public static class Student extends Person {

        private String program;

        private int year;

        private double fee;

  

        // Constructor

        public Student(String name, String address, String program, int year, double fee) {

            super(name, address);

            this.program = program;

            this.year = year;

            this.fee = fee;

        }

  

        // Getters and Setters

        public String getProgram() {

            return program;

        }

  

        public void setProgram(String program) {

            this.program = program;

        }

  

        public int getYear() {

            return year;

        }

  

        public void setYear(int year) {

            this.year = year;

        }

  

        public double getFee() {

            return fee;

        }

  

        public void setFee(double fee) {

            this.fee = fee;

        }

  

        // toString method

        @Override

        public String toString() {

            return "Student[" + super.toString() +

                   ", program=" + program +

                   ", year=" + year +

                   ", fee=" + fee + "]";

        }

    }

  

    // Subclass: Staff

    public static class Staff extends Person {

        private String school;

        private double pay;

  

        // Constructor

        public Staff(String name, String address, String school, double pay) {

            super(name, address);

            this.school = school;

            this.pay = pay;

        }

  

        // Getters and Setters

        public String getSchool() {

            return school;

        }

  

        public void setSchool(String school) {

            this.school = school;

        }

  

        public double getPay() {

            return pay;

        }

  

        public void setPay(double pay) {

            this.pay = pay;

        }

  

        // toString method

        @Override

        public String toString() {

            return "Staff[" + super.toString() +

                   ", school=" + school +

                   ", pay=" + pay + "]";

        }

    }

  

    // Main method to test the program

    public static void main(String[] args) {

        // Testing the classes

        Person person = new Person("Alice", "123 Main St");

        System.out.println(person);

  

        Student student = new Student("Bob", "456 Elm St", "Computer Science", 2025, 15000.0);

        System.out.println(student);

  

        Staff staff = new Staff("Charlie", "789 Oak St", "Engineering", 70000.0);

        System.out.println(staff);

    }

}

```

```bash

C:\Users\TJ\prog\temp\oop\lab7> cmd /C ""C:\Program Files\Eclipse Adoptium\jdk-17.0.13.11-hotspot\bin\java.exe" -XX:+ShowCodeDetailsInExceptionMessages -cp C:\Users\TJ\AppData\Roaming\Code\User\workspaceStorage\095ef1e73c8fb7098a9f0aa9a9e9b786\redhat.java\jdt_ws\lab7_8ba73fe9\bin Question2 "
Person[name=Alice, address=123 Main St]
Student[Person[name=Bob, address=456 Elm St], program=Computer Science, year=2025, fee=15000.0]
Staff[Person[name=Charlie, address=789 Oak St], school=Engineering, pay=70000.0]

```

# References


###### Information
- date: 2025.03.27
- time: 15:04