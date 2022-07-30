package heapsort;

import java.util.Arrays;
import java.util.Scanner;

public class HeapSort {

    public static void main(String[] args) {
        int s;
        Scanner input = new Scanner(System.in);
        System.out.print("ENTER THE SIZE OF ARRAY >>");
        s = input.nextInt();

        Scanner input2 = new Scanner(System.in);
        int[] arr = new int[s];
        System.out.print("ENTER THE ELEMENTS >>");
        for (int i = 0; i < arr.length; i++) {
            arr[i] = input2.nextInt();

        }
        System.out.println("ENTERD ARRAY ELEMENTS ARE >>");
        for (int i = 0; i < arr.length; i++) {
            System.out.print("\t " + arr[i]);

        }

        //int[] arr = {16, 7, 22, 3, 19, 9, 33};
        HeapSort ob = new HeapSort();
        ob.sort(arr, arr.length);
        System.out.println("\nThe sorted array is >>>");
        System.out.println(Arrays.toString(arr));
    }

    public void sort(int arr[], int size) {

        for (int i = size / 2 - 1; i >= 0; i--) {

            heapify(arr, size, i);

        }
        for (int i = size - 1; i > 0; i--) {

            int temp = arr[0];
            arr[0] = arr[i];
            arr[i] = temp;
            heapify(arr, i, 0);

        }

    }

    public void heapify(int[] arr, int size, int i) {

        int largest = i;
        int left = 2 * i + 1;
        int right = 2 * i + 2;

        if (left < size && arr[left] > arr[largest]) {

            largest = left;

        }

        if (right < size && arr[right] > arr[largest]) {

            largest = right;
        }
        if (largest != i) {

            int temp = arr[i];
            arr[i] = arr[largest];
            arr[largest] = temp;
            heapify(arr, size, largest);

        }

    }

}
