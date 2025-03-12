# com.java.first-assigment
import java.util.*;
public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        System.out.print("Enter the number: ");
        long number = sc.nextLong();

        if (number < 1 || number >= 1000000000000L) {
            System.out.println("Invalid number (Enter between 1 - 999,999,999,999)");
        } else {
            System.out.println(convertToWords(number));
        }
    }

    public static String convertToWords(long num) {
        String[] sD = {"", "one", "two", "three", "four", "five", "six", "seven", "eight", "nine", "ten",
                "eleven", "twelve", "thirteen", "fourteen", "fifteen", "sixteen", "seventeen", "eighteen", "nineteen"};
        String[] ty = {"", "ten", "twenty", "thirty", "forty", "fifty", "sixty", "seventy", "eighty", "ninety"};

        if (num < 20) {
            return sD[(int) num];
        } else if (num < 100) {
            return ty[(int) (num / 10)] + " " + sD[(int) (num % 10)];
        } else if (num < 1000) {
            return sD[(int) (num / 100)] + " hundred " + convertToWords(num % 100);
        } else if (num < 1000000) {
            return convertToWords(num / 1000) + " thousand " + convertToWords(num % 1000);
        } else if (num < 1000000000) {
            return convertToWords(num / 1000000) + " million " + convertToWords(num % 1000000);
        } else if (num < 1000000000000L) {
            return convertToWords(num / 1000000000) + " billion " + convertToWords(num % 1000000000);
        } else {
            return "Out of range";
        }
    }
}
