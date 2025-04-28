# Number of Digits in a Number Code

```java
import java.lang.*;
import java.util.*;

public class Digits {

    public static void main (String [] args) {

        Scanner sc = new Scanner(System.in);
        System.out.println("Enter a number : ");
        int num = sc.nextInt();
        int num1 = num;
        int f = 0;
        while (num > 0) {

            num = num / 10;
            f++;
        }
        System.out.println("The number of digits in " + num1 + " is " + f);
    }
}

```

# Sum of Digits in a Number Code

```java
import java.lang.*;
import java.util.*;

public class Digits {

    public static void main (String [] args) {

        Scanner sc = new Scanner(System.in);
        System.out.println("Enter a number : ");
        int num = sc.nextInt();
        int num1 = num;
        int sum = 0, rem = 0;
        while (num > 0) {

            rem = num % 10;
            num = num / 10;
            sum = sum + rem;
        }
        System.out.println("The sum of digits in " + num1 + " is " + sum);
    }
}

```

# Sum of Even and Odd Digits in a Number Code

```java
import java.lang.*;
import java.util.*;

public class Digits {

    public static void main (String [] args) {

        Scanner sc = new Scanner(System.in);
        System.out.println("Enter a number : ");
        int num = sc.nextInt();
        int num1 = num;
        int sum_ev = 0, sum_od = 0, rem = 0;
        while (num > 0) {

            rem = num % 10;
            num = num / 10;
            if(rem % 2 == 0) {

                sum_ev = sum_ev + rem;
            }
            else {

                sum_od = sum_od + rem;
            }
        }
        System.out.println("The sum of even digits in " + num1 + " is " + sum_ev + " and sum of odd digits is " + sum_od);
    }
}

```

# Sum of Digits at Even and Odd Places Code

```java
import java.lang.*;
import java.util.*;

public class Digits {

    public static void main (String [] args) {

        Scanner sc = new Scanner(System.in);
        System.out.println("Enter a number : ");
        int num = sc.nextInt();
        int num1 = num;
        int sum_ev = 0, sum_od = 0, rem = 0, f = 0;
        while (num > 0) {

            rem = num % 10;
            num = num / 10;
            f++;
            if(f % 2 == 0) {

                sum_ev = sum_ev + rem;
            }
            else {

                sum_od = sum_od + rem;
            }
        }
        System.out.println("The sum of digits at even place in " + num1 + " is " + sum_ev + " and sum of digits at odd place is " + sum_od);
    }
}

```

# Reverse of a Number Code

```java
import java.lang.*;
import java.util.*;

public class Digits {

    public static void main (String [] args) {

        Scanner sc = new Scanner(System.in);
        System.out.println("Enter a number : ");
        int num = sc.nextInt();
        int num1 = num;
        int rem = 0, rev_num = 0;
        while (num > 0) {

            rem = num % 10;
            num = num / 10;
            rev_num = (rev_num * 10) + rem;
        }
        System.out.println("The reverse of " + num1 + " is " + rev_num);
    }
}
