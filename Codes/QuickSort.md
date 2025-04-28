```java
import java.lang.*;
import java.util.*;

public class QuickSort {

    static int comp = 0;
    static int swaps = 0;
    public static void quicksort (int[] arr, int s, int e) {

        if (s < e) {

            int p = partition(arr, s, e);
            quicksort (arr, s, p - 1);
            quicksort (arr, p + 1, e);
        }
    }

    public static int partition (int[] arr, int s, int e) {

        int p = s;
        int c = arr[e];

        for (int i = s; i < e; i++) {

            comp++;
            if (arr[i] < c) {

                int temp = arr[i];
                arr[i] = arr[p];
                arr[p] = temp;
                p++;
                swaps++;
            }
        }
        int temp = arr[p];
        arr[p] = arr[e];
        arr[e] = temp;
        swaps++;
        return p;
    }

    public static void main (String[] args) {

        Scanner sc = new Scanner(System.in);
        System.out.println("Enter size of array : ");
        int size = sc.nextInt();
        int[] arr = new int[size];

        System.out.println("Enter array elements : ");
        for (int i = 0; i < size; i++) {

            arr[i] = sc.nextInt();
        }

        int s = 0;
        int e = size - 1;
        quicksort(arr, s, e);

        System.out.println("No. of comparisons : " +  comp);
        System.out.println("No. of swaps : " +  swaps);
        System.out.println("Sorted array : ");
        for (int i = 0; i < size; i++) {

            System.out.print(arr[i] + " ");
        }

    }
}
