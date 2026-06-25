1)import java.util.Scanner;

public class ShoppingBillGenerator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Taking inputs
        System.out.print("Enter Customer Name: ");
        String customerName = scanner.nextLine();

        System.out.print("Enter Product Name: ");
        String productName = scanner.nextLine();

        System.out.print("Enter Product Price: ");
        double price = scanner.nextDouble();

        System.out.print("Enter Quantity: ");
        int quantity = scanner.nextInt();

        // Calculation
        double totalBill = price * quantity;

        // Output Display
        System.out.println("\n--- Invoice ---");
        System.out.println("Customer Name: " + customerName);
        System.out.println("Product: " + productName);
        System.out.println("Price: " + price);
        System.out.println("Quantity: " + quantity);
        System.out.println("Total Bill: " + totalBill);

        scanner.close();
    }
}
2. import java.util.Scanner;

public class StudentResultAnalyzer {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Taking inputs
        System.out.print("Enter Student Name: ");
        String studentName = scanner.nextLine();

        System.out.print("Enter Marks for Subject 1: ");
        double sub1 = scanner.nextDouble();

        System.out.print("Enter Marks for Subject 2: ");
        double sub2 = scanner.nextDouble();

        System.out.print("Enter Marks for Subject 3: ");
        double sub3 = scanner.nextDouble();

        // Calculations
        double totalMarks = sub1 + sub2 + sub3;
        double averageMarks = totalMarks / 3.0;

        // Output Display
        System.out.println("\n--- Result Analysis ---");
        System.out.println("Student Name: " + studentName);
        System.out.println("Total Marks: " + totalMarks);
        System.out.println("Average Marks: " + averageMarks);

        // Bonus: Comparison check
        boolean isPass = averageMarks > 50;
        System.out.println("Is Average greater than 50?: " + isPass);

        scanner.close();
    }
}
3.import java.util.Scanner;

public class TravelExpenseEstimator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Taking inputs
        System.out.print("Enter travel distance (in KM): ");
        double distance = scanner.nextDouble();

        System.out.print("Enter petrol price per liter: ");
        double petrolPrice = scanner.nextDouble();

        System.out.print("Enter vehicle mileage (KM per liter): ");
        double mileage = scanner.nextDouble();

        // Calculations
        double petrolNeeded = distance / mileage;
        double totalTravelCost = petrolNeeded * petrolPrice;

        // Output Display
        System.out.println("\n--- Travel Estimate ---");
        System.out.printf("Petrol Needed: %.2f Liters\n", petrolNeeded);
        System.out.printf("Total Travel Cost: ₹%.2f\n", totalTravelCost);

        scanner.close();
    }
}
4.import java.util.Scanner;

public class AtmSystem {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Taking inputs
        System.out.print("Enter Account Holder Name: ");
        String accountHolder = scanner.nextLine();

        System.out.print("Enter Account Balance: ");
        double balance = scanner.nextDouble();

        System.out.print("Enter Withdrawal Amount: ");
        double withdrawalAmount = scanner.nextDouble();

        // Bonus Check: Check if balance is sufficient using comparison operator
        boolean hasSufficientFunds = balance >= withdrawalAmount;

        System.out.println("\n--- ATM Transaction Summary ---");
        System.out.println("Account Holder: " + accountHolder);
        System.out.println("Is balance sufficient for withdrawal?: " + hasSufficientFunds);

        // Calculation & Output based on fund availability
        if (hasSufficientFunds) {
            double remainingBalance = balance - withdrawalAmount;
            System.out.println("Withdrawal Successful!");
            System.out.println("Remaining Balance: " + remainingBalance);
        } else {
            System.out.println("Transaction Denied: Insufficient Funds.");
            System.out.println("Current Balance remains: " + balance);
        }

        scanner.close();
    }
}


