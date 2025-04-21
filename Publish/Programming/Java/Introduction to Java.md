```java
import java.util.Scanner;

  

public class Main {

  

public static void main(String[] args) {

Scanner scanner = new Scanner(System.in);

  

System.out.print("Enter the size of the array: ");

int size = scanner.nextInt();

  

int[] arr = new int[size];

System.out.println("Enter the elements of the array: ");

for (int i = 0; i < size; i++) {

arr[i] = scanner.nextInt();

}

  

System.out.print("The array elements are: ");

for (int i = 0; i < size; i++) {

System.out.print(arr[i] + " ");

}

  

int min = minimum(arr, size);

System.out.println("\nThe minimum element in the array is: " + min);

}

  

public static int minimum(int[] arr, int size) {

int min = arr[0];

  

for (int i = 1; i < size; i++) {

if (arr[i] < min) {

min = arr[i];

}

}

  

return min;

}

}
```