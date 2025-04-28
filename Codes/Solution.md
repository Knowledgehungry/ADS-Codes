```java
import java.lang.*;
import java.util.*;

public class Solution {
    public static void main (String[] args) {

        Scanner sc = new Scanner (System.in);
        int[] nums;
        System.out.println("Enter size : ");
        int size = sc.nextInt();
        nums = new int[size];
        System.out.println("Enter elements : ");
        for (int i = 0; i < size; i++) {
            nums[i] = sc.nextInt();
        }
        System.out.println("Enter target : ");
        int target = sc.nextInt();

        int f = 0;
        for (int i = 0; i < size - 1; i++) {

            for (int j = i + 1; j < size; j++) {

                if ((nums[i] + nums[j]) == target) {

                    System.out.println("[" + i + "," + j + "]");
                    f++;
                }
            }
            if (f != 0) {
                break;
            }
        }
    }
}
