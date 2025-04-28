```java
/*
import java.lang.*;
import java.util.*;

public class PrefixSum {

    public static void main (String[] args) {

        Scanner sc = new Scanner(System.in);
        System.out.println("Enter size : ");
        int N = sc.nextInt();
        int[] A = new int[N];
        int[] PFS = new int[N];
        System.out.println("Enter elements : ");
        for (int i = 0; i < N; i++) {

            A[i] = sc.nextInt();
        }
        PFS[0] = A[0];
        for (int i = 1; i < N; i++) {

            PFS[i] = PFS[i - 1] + A[i];
        }
        System.out.println("Prefix Sum : ");
        for (int i = 0; i < N; i++) {

            System.out.print(PFS[i] + " ");
        }
    }
}
*/

import java.lang.*;
import java.util.*;

public class PrefixSum {

    public static void main (String[] args) {

        Scanner sc = new Scanner(System.in);
        System.out.println("Enter size : ");
        int N = sc.nextInt();
        int[] A = new int[N];
        System.out.println("Enter elements : ");
        for (int i = 0; i < N; i++) {

            A[i] = sc.nextInt();
        }
        for (int i = 1; i < N; i++) {

            A[i] = A[i - 1] + A[i];
        }
        System.out.println("Prefix Sum : ");
        for (int i = 0; i < N; i++) {

            System.out.print(A[i] + " ");
        }
    }
}
