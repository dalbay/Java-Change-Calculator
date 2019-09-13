# Java-Change-Calculator

*Console Application that calculates the minimum number of quarters, dimes, nickels, and pennies needed for the specified number of cents.*

![console images](/images/consoleImg.png)


```java
/**
 * Change Calculator
 * @author Faruk Dalbay
 */
public class Main {
    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
         System.out.println("Welcome to the Change Calculator");
        
    // use Scanner object for user input
        Scanner sc = new Scanner(System.in);
        String choice = "y";
        while(choice.equalsIgnoreCase("y")){
            System.out.println();
            System.out.print("Enter number of cents (0-99): ");
            int money = sc.nextInt();
            System.out.println();
            CalculateChange(money);
            System.out.println("");
            System.out.print("Continue? (y/n)/: "); 
            choice = sc.next();
    }    
}
    public static void CalculateChange(int change) {
        int quaters;
        int quatersAmount = 0;
        int dimes;
        int dimesAmount = 0;
        int nickelsAmount = 0;
        int penniesAmount = 0;

        if (change % 25 >= 0) {
            quaters = change % 25;
            quatersAmount = (change - quaters) / 25;
            if (quaters % 10 >= 0) {
                dimes = quaters % 10;
                dimesAmount = (quaters - dimes) / 10;
                if (dimes % 5 >= 0) {
                    int nickels = dimes % 5;
                    nickelsAmount = (dimes - nickels) / 5;
                    penniesAmount = nickels;
                }
            }
        }
        System.out.println("Quaters:  " + Integer.toString(quatersAmount));
        System.out.println("Dimes:    " + Integer.toString(dimesAmount));
        System.out.println("Nickels:  " + Integer.toString(nickelsAmount));
        System.out.println("Pennies:  " + Integer.toString(penniesAmount));        
    }
}

```