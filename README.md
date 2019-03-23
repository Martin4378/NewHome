# NewHome

import java.util.Scanner;

public class P37_NewHome {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        double rosesPrice = 5;
        double dahliasPrice = 3.80;
        double tulipsPrice = 2.80;
        double narcissusPrice = 3;
        double gladiolusPrice = 2.50;

        String flowerType = scanner.nextLine();
        int flowerCount = Integer.parseInt(scanner.nextLine());
        int budget = Integer.parseInt(scanner.nextLine());

        double orderPrice = 0;

        if (flowerType.equalsIgnoreCase("Roses")){
            orderPrice = flowerCount * rosesPrice;
            if (flowerCount > 80){
                orderPrice = orderPrice - 0.1 * orderPrice;
            }
        } else if (flowerType.equalsIgnoreCase("Dahlias")){
            orderPrice = flowerCount * dahliasPrice;
            if (flowerCount > 90){
                orderPrice = orderPrice - 0.15 * orderPrice;
            }
        } else if (flowerType.equalsIgnoreCase("Tulips")) {
            orderPrice = flowerCount * tulipsPrice;
            if (flowerCount > 80){
                orderPrice = orderPrice - 0.15 * orderPrice;
            }
        } else if (flowerType.equalsIgnoreCase("Narcissus")) {
            orderPrice = flowerCount * narcissusPrice;
            if (flowerCount < 120){
                orderPrice = orderPrice + 0.15 * orderPrice;
            }
        } else if (flowerType.equalsIgnoreCase("Gladiolus")) {
            orderPrice = flowerCount * gladiolusPrice;
            if (flowerCount < 80){
                orderPrice = orderPrice + 0.2 * orderPrice;
            }
        } else {
            System.out.println("Invalid input");
        }
        if (budget >= orderPrice){
            double moneyLeft = budget - orderPrice;
            System.out.printf("Hey, you have a great garden with %d %s and %.2f leva left.", flowerCount, flowerType, moneyLeft);
        } else {
            double neededMoney = orderPrice - budget;
            System.out.printf("Not enough money, you need %.2f leva more.", neededMoney);
        }
    }
    
}
