# Codsoft-task2-student-grade-calculator-
import java.util.Scanner;

public class StudentGradeCalculator {
    private int numSubjects;
    private int[] marks;
    
    // Constructor to initialize variables
    public StudentGradeCalculator(int numSubjects) {
        this.numSubjects = numSubjects;
        marks = new int[numSubjects];
    }
    
    // Method to input marks for each subject
    public void inputMarks() {
        Scanner scanner = new Scanner(System.in);
        for (int i = 0; i < numSubjects; i++) {
            System.out.print("Enter marks for subject " + (i + 1) + ": ");
            marks[i] = scanner.nextInt();
        }
    }
    
    // Method to calculate total marks
    public int calculateTotal() {
        int total = 0;
        for (int mark : marks) {
            total += mark;
        }
        return total;
    }
    
    // Method to calculate average marks
    public double calculateAverage() {
        int total = calculateTotal();
        return (double) total / numSubjects;
    }
    
    // Method to calculate grade based on average marks
    public String calculateGrade() {
        double average = calculateAverage();
        
        if (average >= 90) {
            return "A";
        } else if (average >= 80) {
            return "B";
        } else if (average >= 70) {
            return "C";
        } else if (average >= 60) {
            return "D";
        } else {
            return "F";
        }
    }
    
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Enter the number of subjects: ");
        int numSubjects = scanner.nextInt();
        
        // Create an instance of StudentGradeCalculator
        StudentGradeCalculator calculator = new StudentGradeCalculator(numSubjects);
        
        // Input marks for each subject
        calculator.inputMarks();
        
        // Calculate total marks
        int total = calculator.calculateTotal();
        
        // Calculate average marks
        double average = calculator.calculateAverage();
        
        // Calculate grade
        String grade = calculator.calculateGrade();
        
        // Display results
        System.out.println("\nTotal marks: " + total);
        System.out.println("Average marks: " + average);
        System.out.println("Grade: " + grade);
        
        scanner.close();
    }
}
