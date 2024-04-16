# Task-2
import java.util.Scanner;

public class Ticket{

    public class MuseumTicketCalculator {
   public static void main(String[] args) {
Scanner scanner = new Scanner(System.in);


System.out.println("Client's name; ");
String clientName = scanner.nextLine();
System.out.print("Clients age:");
int age = scanner.nextInt();
            System.out.print("Enter number of tickets: ");
            int numberOfTickets = scanner.nextInt();

            // Calculating ticket price
            double ticketPrice = calculateTicketPrice(age, numberOfTickets);

            // Displaying result
            System.out.println("\nClient's data:");
            System.out.println("Name: " + clientName);
            System.out.println("Age: " + age);
            System.out.println("Number of tickets: " + numberOfTickets);
            System.out.println("Ticket price after discount: " + ticketPrice + " PLN");
        }
        public static double calculateTicketPrice(int age, int numberOfTickets) {
            double basePrice = 40; // Base ticket price in PLN

            // Applying discounts based on age
            if (age < 18) {
                basePrice -= 10; // Discount of 10 PLN for clients under 18
            } else if (age >= 65) {
                basePrice -= 15; // Discount of 15 PLN for clients 65 or older
            }

            // Applying discounts based on number of tickets
            if (numberOfTickets >= 5) {
                basePrice -= 5; // Discount of 5 PLN for purchasing 5 or more tickets
            }

            return basePrice * numberOfTickets;
        }
    }
}
