1.import java.util.Scanner;

public class BonusChecker {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Input section
        System.out.print("Enter years of experience: ");
        double years = scanner.nextDouble();

        System.out.print("Enter attendance percentage: ");
        double attendance = scanner.nextDouble();

        System.out.print("Enter performance rating (1-5): ");
        int rating = scanner.nextInt();

        // Evaluation logic
        if (attendance < 60) {
            System.out.println("Not Eligible");
            System.out.println("Bonus Amount: ₹0 (Reason: Attendance below 60%)");
        } else if (years > 3 && attendance > 85) {
            int bonus = 0;

            switch (rating) {
                case 5:
                    bonus = 50000;
                    break;
                case 4:
                    bonus = 30000;
                    break;
                case 3:
                    bonus = 10000;
                    break;
                default:
                    bonus = 0;
                    break;
            }

            if (bonus > 0) {
                System.out.println("Eligible");
                System.out.println("Bonus Amount: ₹" + bonus);
            } else {
                System.out.println("Not Eligible");
                System.out.println("Bonus Amount: ₹0 (Reason: Performance rating too low)");
            }
        } else {
            System.out.println("Not Eligible");
            System.out.println("Bonus Amount: ₹0 (Reason: Did not meet experience or attendance criteria)");
        }

        scanner.close();
    }
2.import java.util.Scanner;

public class SmartLogin {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        String correctUsername = "admin";
        String correctPassword = "Java@123";
        int attempts = 0;

        while (attempts < 3) {
            System.out.print("Enter Username: ");
            String username = scanner.next();

            System.out.print("Enter Password: ");
            String password = scanner.next();

            if (username.equals(correctUsername) && password.equals(correctPassword)) {
                // Username and password correct, check OTP
                System.out.print("Enter 4-digit OTP: ");
                int otp = scanner.nextInt();

                if (otp >= 1000 && otp <= 9999) {
                    System.out.println("Login Successful!");
                } else {
                    System.out.println("Invalid OTP. Login Failed.");
                }
                break; // Break the while loop since credentials were correct
            } else {
                attempts++;
                System.out.println("Incorrect credentials.");

                // Extra twist hint checking
                if (username.equals(correctUsername) && password.startsWith("Java") && password.endsWith("123")) {
                    System.out.println("Almost correct password");
                }

                if (attempts == 3) {
                    System.out.println("Account Blocked");
                }
            }
        }

        scanner.close();
    }
3.import java.util.Scanner;

public class ElectricityBill {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("--- Electricity Bill Generator ---");
        System.out.println("1. Domestic");
        System.out.println("2. Commercial");
        System.out.println("3. Industrial");
        System.out.print("Select connection type (Enter 1, 2, or 3): ");
        int choice = scanner.nextInt();

        double bill = 0.0;

        if (choice == 1 || choice == 2 || choice == 3) {
            System.out.print("Enter units consumed: ");
            double units = scanner.nextDouble();

            if (choice == 1) { // Domestic
                if (units <= 100) {
                    bill = 0;
                } else if (units <= 300) {
                    bill = (units - 100) * 5;
                } else {
                    bill = (200 * 5) + ((units - 300) * 8);
                }
            } else if (choice == 2) { // Commercial
                if (units < 200) {
                    bill = units * 10;
                } else {
                    bill = units * 15;
                }
            } else { // Industrial
                System.out.print("Is power factor good? (yes/no): ");
                String pfInput = scanner.next().trim().toLowerCase();
                
                double baseCharge = units * 20;
                if (units > 500 && pfInput.equals("yes")) {
                    bill = baseCharge * 0.90; // 10% discount applied
                } else {
                    bill = baseCharge;
                }
            }

            System.out.printf("Total Electricity Bill: ₹%.2f\n", bill);
        } else {
            System.out.println("Invalid Connection Type");
        }

        scanner.close();
    }
4.import java.util.Scanner;

public class AdmissionPredictor {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Input section
        System.out.print("Enter Maths marks: ");
        double maths = scanner.nextDouble();

        System.out.print("Enter Physics marks: ");
        double physics = scanner.nextDouble();

        System.out.print("Enter Chemistry marks: ");
        double chemistry = scanner.nextDouble();

        double totalAverage = (maths + physics + chemistry) / 3.0;

        // Logic evaluation
        if (maths < 35 || physics < 35 || chemistry < 35) {
            System.out.println("Admission Status: Automatically Rejected (Failed in one or more subjects)");
            System.out.println("Scholarship Status: Not Eligible");
        } else {
            // Check general admission criteria
            boolean criteria1 = (maths >= 70 && physics >= 60 && chemistry >= 60);
            boolean criteria2 = (totalAverage >= 80);

            if (criteria1 || criteria2) {
                System.out.println("Admission Status: Eligible");

                // Extra twist for scholarship
                if (maths > 90 && physics > 90 && chemistry > 90) {
                    System.out.println("Scholarship Status: Eligible for Scholarship");
                } else {
                    System.out.println("Scholarship Status: Not Eligible for Scholarship");
                }
            } else {
                System.out.println("Admission Status: Not Eligible (Criteria not met)");
                System.out.println("Scholarship Status: Not Eligible");
            }
        }

        scanner.close();
    }
5.import java.util.Scanner;

public class RestaurantSystem {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("--- Main Menu ---");
        System.out.println("1. Veg");
        System.out.println("2. Non-Veg");
        System.out.print("Select Category (1 or 2): ");
        int mainChoice = scanner.nextInt();

        String itemName = "";
        double itemPrice = 0.0;
        boolean validSelection = true;

        if (mainChoice == 1) { // Veg Menu
            System.out.println("\n--- Veg Menu ---");
            System.out.println("1. Fried Rice - ₹150");
            System.out.println("2. Noodles - ₹120");
            System.out.print("Select Item (1 or 2): ");
            int itemChoice = scanner.nextInt();

            if (itemChoice == 1) {
                itemName = "Fried Rice";
                itemPrice = 150;
            } else if (itemChoice == 2) {
                itemName = "Noodles";
                itemPrice = 120;
            } else {
                validSelection = false;
            }

        } else if (mainChoice == 2) { // Non-Veg Menu
            System.out.println("\n--- Non-Veg Menu ---");
            System.out.println("1. Chicken Biryani - ₹250");
            System.out.println("2. Grill Chicken - ₹300");
            System.out.print("Select Item (1 or 2): ");
            int itemChoice = scanner.nextInt();

            if (itemChoice == 1) {
                itemName = "Chicken Biryani";
                itemPrice = 250;
            } else if (itemChoice == 2) {
                itemName = "Grill Chicken";
                itemPrice = 300;
            } else {
                validSelection = false;
            }
        } else {
            validSelection = false;
        }

        // Process order details if the selection was valid
        if (validSelection) {
            System.out.print("Enter quantity: ");
            int quantity = scanner.nextInt();

            System.out.print("Enter Member status (Gold/Silver/Normal): ");
            String membership = scanner.next().trim();

            double baseBill = itemPrice * quantity;
            double discount = 0.0;

            // Handle membership case insensitively
            if (membership.equalsIgnoreCase("Gold")) {
                discount = 0.20;
            } else if (membership.equalsIgnoreCase("Silver")) {
                discount = 0.10;
            } else if (membership.equalsIgnoreCase("Normal")) {
                discount = 0.0;
            } else {
                System.out.println("Unknown membership type. Applied 'Normal' status processing.");
            }

            double finalBill = baseBill * (1 - discount);

            System.out.println("\n--- Receipt ---");
            System.out.println("Ordered: " + itemName + " x " + quantity);
            System.out.println("Subtotal: ₹" + baseBill);
            System.out.printf("Final Bill (After Discount): ₹%.2f\n", finalBill);

            // Twist: Free dessert check
            if (finalBill > 2000 && membership.equalsIgnoreCase("Gold")) {
                System.out.println("🎉 Congratulations! You win a free dessert! 🎉");
            }
        } else {
            System.out.println("Invalid Selection");
        }

        scanner.close();
    }
}

