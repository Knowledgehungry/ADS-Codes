# Factorial Code

```java

import java.lang.*;
import java.util.*;

public class Factorial {

    public static int fact (int num) {

        if (num == 1) return 1;
        return fact(num - 1) * num;
    }

    public static void main (String[] args) {

        Scanner sc = new Scanner(System.in);
        System.out.println("Enter number to find factorial : ");
        int num = sc.nextInt();
        if (num == 0 || num == 1) {

            System.out.println("Factorial : 1");
        }
        else if (num < 0) {

            System.out.println("Not defined");
        }
        else {
            System.out.println("Factorial : " + fact(num));
        }
    }
}
