# javaintern
codealpha intern




Here's a complete Java program to create a Student Grade Tracker. The program allows a teacher to enter students' grades and compute their average, highest, and lowest scores. We'll use an ArrayList to store the student data.

StudentGradeTracker.java
java

import java.util.ArrayList;
import java.util.Scanner;

public class StudentGradeTracker {
    public static void main(String[] args) {
        ArrayList<Double> grades = new ArrayList<>();
        Scanner scanner = new Scanner(System.in);
        int option;

        do {
            System.out.println("1. Add a grade");
            System.out.println("2. Display average grade");
            System.out.println("3. Display highest grade");
            System.out.println("4. Display lowest grade");
            System.out.println("5. Exit");
            System.out.print("Choose an option: ");
            option = scanner.nextInt();

            switch (option) {
                case 1:
                    addGrade(grades, scanner);
                    break;
                case 2:
                    displayAverage(grades);
                    break;
                case 3:
                    displayHighest(grades);
                    break;
                case 4:
                    displayLowest(grades);
                    break;
                case 5:
                    System.out.println("Exiting...");
                    break;
                default:
                    System.out.println("Invalid option. Please try again.");
            }
        } while (option != 5);

        scanner.close();
    }

    public static void addGrade(ArrayList<Double> grades, Scanner scanner) {
        System.out.print("Enter the grade: ");
        double grade = scanner.nextDouble();
        grades.add(grade);
        System.out.println("Grade added.");
    }

    public static void displayAverage(ArrayList<Double> grades) {
        if (grades.isEmpty()) {
            System.out.println("No grades available.");
            return;
        }

        double sum = 0;
        for (double grade : grades) {
            sum += grade;
        }
        double average = sum / grades.size();
        System.out.printf("Average grade: %.2f%n", average);
    }

    public static void displayHighest(ArrayList<Double> grades) {
        if (grades.isEmpty()) {
            System.out.println("No grades available.");
            return;
        }

        double highest = grades.get(0);
        for (double grade : grades) {
            if (grade > highest) {
                highest = grade;
            }
        }
        System.out.printf("Highest grade: %.2f%n", highest);
    }

    public static void displayLowest(ArrayList<Double> grades) {
        if (grades.isEmpty()) {
            System.out.println("No grades available.");
            return;
        }

        double lowest = grades.get(0);
        for (double grade : grades) {
            if (grade < lowest) {
                lowest = grade;
            }
        }
        System.out.printf("Lowest grade: %.2f%n", lowest);
    }
}
Explanation
Main Class and Menu: The StudentGradeTracker class contains the main method and a menu for the teacher to interact with. The menu has options to add a grade, display the average grade, display the highest grade, display the lowest grade, and exit the program.

Adding Grades: The addGrade method allows the teacher to enter a grade which is then added to the ArrayList of grades.

Displaying Average Grade: The displayAverage method calculates the average of the grades stored in the ArrayList and prints it.

Displaying Highest Grade: The displayHighest method finds the highest grade in the ArrayList and prints it.

Displaying Lowest Grade: The displayLowest method finds the lowest grade in the ArrayList and prints it.

How to Run
Save the code to a file named StudentGradeTracker.java.
Open a terminal or command prompt and navigate to the directory where the file is saved.
Compile the program using javac StudentGradeTracker.java.
Run the program using java StudentGradeTracker.
