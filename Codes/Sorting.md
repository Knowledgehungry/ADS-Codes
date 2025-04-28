```java
import java.lang.*;
import java.util.*;

public class Sorting {

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

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        int c;
        do {
            System.out.println("1. Bubble Sort \n2. Insertion Sort \n3. Quick Sort \nEnter an option : ");
            int ch = sc.nextInt();
            switch (ch) {

                case 1: {
                    System.out.println("Enter size of array : ");
                    int size = sc.nextInt();
                    int[] arr = new int[size];
                    System.out.println("Enter array elements : ");
                    for (int i = 0; i < size; i++) {

                        arr[i] = sc.nextInt();
                    }

                    int count = 0;
                    int swaps = 0;
                    for (int i = 0; i < size - 1; i++) {

                        int f = 0;
                        for (int j = 0; j < size - i - 1; j++) {

                            count++;
                            if (arr[j] > arr[j + 1]) {

                                int temp = arr[j];
                                arr[j] = arr[j + 1];
                                arr[j + 1] = temp;
                                f++;
                                swaps++;
                            }
                        }
                        if (f == 0) {

                            break;
                        }
                    }
                    System.out.println("No. of comparisons : " + count);
                    System.out.println("No. of swaps : " + swaps);
                    System.out.println("Sorted array : ");
                    for (int i = 0; i < size; i++) {

                        System.out.print(arr[i] + " ");
                    }
                    break;
                }
                case 2: {
                    System.out.println("Enter size of array : ");
                    int size = sc.nextInt();
                    int [] arr = new int[size];
                    System.out.println("Enter array elements : ");
                    for (int i = 0; i < size; i++) {

                        arr[i] = sc.nextInt();
                    }

                    int comp = 0;
                    int swaps = 0;
                    for (int i = 1; i < size; i++) {

                        int temp = arr[i];
                        int j = i - 1;
                        while (j >= 0) {

                            comp++;
                            if (arr[j] > temp) {

                                arr[j + 1] = arr[j];
                                j--;
                                swaps++;
                            }
                        }
                        arr[j + 1] = temp;
                    }

                    System.out.println("No. of comparisons : " + comp);
                    System.out.println("No. of swaps : " + swaps);
                    System.out.println("Sorted array : ");
                    for (int i = 0; i < size; i++) {

                        System.out.print(arr[i] + " ");
                    }
                    break;
                }
                case 3: {
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
                    break;
                }
                default: {
                    System.out.println("Enter valid option!!");
                    break;
                }
            }
            System.out.println("\nDo you wish to continue? 0 - continue 1 - stop");
            c = sc.nextInt();
        } while(c == 0);
    }
}
