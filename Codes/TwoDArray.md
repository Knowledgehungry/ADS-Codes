```java
import java.lang.*;
import java.util.*;

public class TwoDArray {

    public static void main(String[] args) {

        Scanner sc =  new Scanner(System.in);
        System.out.println("Enter no. of rows : ");
        int N = sc.nextInt();
        System.out.println("Enter no. of columns : ");
        int M = sc.nextInt();

        int [][] A = new int[N][M];
        System.out.println("Enter array elements : ");
        for (int i = 0; i < N; i++) {

            for (int j = 0; j < M; j++) {

                A[i][j] = sc.nextInt();
            }
        }
        System.out.println("Array elements row wise : ");
        for (int i = 0; i < N; i++) {

            for (int j = 0; j < M; j++) {

                System.out.print(A[i][j] + " ");
            }
            System.out.println(" ");
        }

        System.out.println("Array elements column wise : ");
        for (int i = 0; i < N; i++) {

            for (int j = 0; j < M; j++) {

                System.out.print(A[j][i] + " ");
            }
            System.out.println(" ");
        }

        System.out.println("Array elements row wise wave form : ");
        for (int i = 0; i < N; i++) {

            if (i % 2 == 0) {

                for (int j = 0; j < M; j++) {

                    System.out.print(A[i][j] + " ");
                }
            }
            else {

                for (int j = N - 1; j >= 0; j--) {

                    System.out.print(A[i][j] + " ");
                }
            }
        }

        System.out.println("\nArray elements column wise wave form : ");
        for (int j = 0; j < M; j++) {

            if (j % 2 == 0) {

                for (int i = 0; i < N; i++) {

                    System.out.print(A[i][j] + " ");
                }
            }
            else {

                for (int i = N - 1; i >= 0; i--) {

                    System.out.print(A[i][j] + " ");
                }
            }
        }
    }
}
