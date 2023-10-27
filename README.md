# Notes

<br>
import java.util.Scanner;

public class TwoDarray {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int matrix[][] = new int[3][3];
        for (int i = 0; i < matrix.length; i++) {
            for (int j = 0; j < matrix[0].length; j++) {
                matrix[i][j] = sc.nextInt();
            }
        }
        for (int i = 0; i < matrix.length; i++) {
            for (int j = 0; j < matrix[0].length; j++) {
                System.out.print(matrix[i][j] + " ");
            }
            System.out.println();
        }

        // searchmatrix(matrix, 5);
        // largest(matrix);
        // smallest(matrix);
        // sprialmatrix(matrix);
        System.out.println(diagonal(matrix));
    }

    public static boolean searchmatrix(int matrix[][], int key) {
        for (int i = 0; i < matrix.length; i++) {
            for (int j = 0; j < matrix[0].length; j++) {
                if (matrix[i][j] == key) {
                    System.out.print("found at index  (" + i + ", " + j + ")");
                    return true;
                }
            }
        }
        return false;
    }

    public static void largest(int matrix[][]) {
        int max = Integer.MIN_VALUE;
        for (int i = 0; i < matrix.length; i++) {
            for (int j = 0; j < matrix[0].length; j++) {
                if (matrix[i][j] > max) {
                    max = matrix[i][j];
                }
            }
        }
        System.out.println("Largest value is = " + max + " ");
    }

    public static void smallest(int matrix[][]) {
        int min = Integer.MAX_VALUE;
        for (int i = 0; i < matrix.length; i++) {
            for (int j = 0; j < matrix[0].length; j++) {
                if (matrix[i][j] < min) {
                    min = matrix[i][j];
                }
            }
        }
        System.out.println("Smallest value is = " + min + " ");
    }

    public static void sprialmatrix(int matrix[][]) {
        int startRow = 0;
        int startColumn = 0;
        int endRow = matrix.length - 1;
        int endColumn = matrix[0].length - 1;

        while (startRow <= endRow && startColumn <= endColumn) {
            // top
            for (int j = startColumn; j <= endColumn; j++) {
                System.out.print(matrix[startRow][j]+" ");
            }

            // right

            for (int i = startRow + 1; i <= endRow; i++) {
                System.out.print(matrix[i][endColumn]+" ");
            }

            // bottom

            for (int j = endColumn - 1; j >= startColumn; j--) {
                if(startRow==endRow){
                    break;
                }
                System.out.print(matrix[endRow][j]+" ");
            }

            // left

            for (int i = endRow - 1; i >= startRow+1; i--) {
                if(startColumn==endColumn){
                    break;
                }
                System.out.print(matrix[i][startColumn]+" ");
            }
            startRow++;
            endRow--;
            startColumn++;
            endColumn--;
        }
        System.out.println();
    }
    
    public static int diagonal(int matrix[][]){
        int sum=0;
        for(int i=0;i<matrix.length;i++){
            sum+=matrix[i][i];
            if(i!=matrix.length-1-i)
            sum+=matrix[i][matrix.length-1-i];
        }
        return sum;
    }
}
