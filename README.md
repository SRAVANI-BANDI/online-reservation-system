# online-reservation-system
Online reservation system for seamless booking and management of appointments or services. Features include user authentication, real-time availability, and admin dashboard for efficient scheduling."
import java.util.Scanner;

public class OnlineReservationSystem {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        boolean isLoggedIn = false;

        System.out.println("Welcome to the Online Reservation System");

        // Login
        while (!isLoggedIn) {
            System.out.println("Please login to continue.");
            System.out.print("Enter Username: ");
            String username = scanner.nextLine();
            System.out.print("Enter Password: ");
            String password = scanner.nextLine();

            if (login(username, password)) {
                isLoggedIn = true;
                System.out.println("Login successful!");
            } else {
                System.out.println("Invalid credentials. Please try again.");
            }
        }

        // Main Menu
        while (true) {
            System.out.println("\nSelect an option:");
            System.out.println("1. Make a Reservation");
            System.out.println("2. Cancel a Reservation");
            System.out.println("3. Exit");
            int choice = scanner.nextInt();

            switch (choice) {
                case 1:
                    makeReservation(scanner);
                    break;
                case 2:
                    cancelReservation(scanner);
                    break;
                case 3:
                    System.out.println("Exiting system. Goodbye!");
                    System.exit(0);
                default:
                    System.out.println("Invalid option. Please try again.");
            }
        }
    }

    // Dummy login function
    public static boolean login(String username, String password) {
        // In a real application, this would check credentials in a database
        return username.equals("admin") && password.equals("password");
    }

    // Dummy make reservation function
    public static void makeReservation(Scanner scanner) {
        System.out.println("Enter your basic details:");
        System.out.print("Name: ");
        String name = scanner.next();
        System.out.print("Train Number: ");
        String trainNumber = scanner.next();
        System.out.print("Class Type: ");
        String classType = scanner.next();
        System.out.print("Date of Journey (DD-MM-YYYY): ");
        String date = scanner.next();
        System.out.print("From: ");
        String from = scanner.next();
        System.out.print("To: ");
        String to = scanner.next();

        System.out.println("Reservation successful for " + name + " on " + date + " from " + from + " to " + to + ".");
        // In a real application, this data would be stored in a database
    }

    // Dummy cancel reservation function
    public static void cancelReservation(Scanner scanner) {
        System.out.print("Enter PNR Number: ");
        String pnrNumber = scanner.next();
        System.out.println("Reservation with PNR " + pnrNumber + " has been found.");
        System.out.print("Do you want to cancel the reservation? (yes/no): ");
        String confirmation = scanner.next();

        if (confirmation.equalsIgnoreCase("yes")) {
            System.out.println("Reservation canceled successfully.");
            // In a real application, this would update the database
        } else {
            System.out.println("Cancellation aborted.");
        }
    }
}
ss
