#STUDENT_GRADE_TRACKER






import java.util.Scanner;
public class StudentGradeTracker {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter number of students: ");
        int n = scanner.nextInt();
        scanner.nextLine();  

        String[] names = new String[n];
        int[] grades = new int[n];

        for (int i = 0; i < n; i++) {
            System.out.print("Enter name of student " + (i + 1) + ": ");
            names[i] = scanner.nextLine();

            System.out.print("Enter grade for " + names[i] + ": ");
            grades[i] = scanner.nextInt();
            scanner.nextLine();  
        }

       
        int total = 0;
        int highest = grades[0];
        int lowest = grades[0];

        for (int i = 0; i < n; i++) {
            total += grades[i];
            if (grades[i] > highest) highest = grades[i];
            if (grades[i] < lowest) lowest = grades[i];
        }

        double average = (double) total / n;

        System.out.println("\n--- Student Grade Report ---");
        for (int i = 0; i < n; i++) {
            System.out.println(names[i] + " - Grade: " + grades[i]);
        }

        System.out.printf("\nAverage Grade: %.2f\n", average);
        System.out.println("Highest Grade: " + highest);
        System.out.println("Lowest Grade: " + lowest);
    }
}
