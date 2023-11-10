# Notes
<br>
<h1>java with DSA </h1>
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

                       <h1>IMPORTANT QUESTIONS 😶😶</h1>


*******************************************************************************/
Prime Number

import java.util.*;
public class Main
{
	public static void main(String[] args) {
		Scanner sc=new Scanner(System.in);
		int t=sc.nextInt();
		for(int i=0;i<t;i++){
		    int n=sc.nextInt();
		    int count=0;
		for(int div=2;div*div<=n;div++){
		    if(n%div==0){
		        count++;
		        break;
		    }
		}
	if(count==0){
		    System.out.println("prime number");
		}else{
		    System.out.println("not a prime number");
		}
	}
  }
}
///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Range in Prime Number

import java.util.*;
public class Main
{
	public static void main(String[] args) {
		Scanner sc=new Scanner(System.in);
		int low=sc.nextInt();
		int high=sc.nextInt();
		
		for(int i=low;i<=high;i++){
		
		int count=0;
		for(int div=2;div*div<=i;div++){
		    if(i%div==0){
		        count++;
		        break;
		    }
		}
		
		if(count==0)
		System.out.println(i+" =  Prime Number");
		else
		System.out.println(i+" =  Not a Prime Number");
		}
	}
}
////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Sum of even and odd

import java.util.*;
public class Main
{
	public static void main(String[] args) {
		Scanner sc=new Scanner(System.in);
		int n=sc.nextInt();
		int sumeven=0;
		int sumodd=0;
	    for(int i=1;i<=n;i++){
	     if(i%2==0){
	         sumeven+=i;
	     }else{
	         sumodd+=i;
	     }
	    }
	    System.out.println(sumeven +"=sumevenn   "  + sumodd+ "  =sumodd");
	
	}
}

/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Leap Year

import java.util.*;
public class Main
{
	public static void main(String[] args) {
		Scanner sc=new Scanner(System.in);
		int year=sc.nextInt();
		
      if (((year % 4 == 0) && (year % 100!= 0)) || (year%400 == 0))
         System.out.println("Specified year is a leap year");
      else
         System.out.println("Specified year is not a leap year");

	    
	}
}

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Roots of a quadratic equation ax^2+bx+c


/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Palindrome Number

import java.util.*;
public class Main
{
	public static void main(String[] args) {
		Scanner sc=new Scanner(System.in);
		int n=sc.nextInt();
		Palindrome(n);
	}
	
	public static void Palindrome(int n){
	    int temp=n;
	    int rev=0;
	    while(n!=0){
	        int digit=n%10;
	        rev=rev*10+digit;
	        n=n/10;
	    }
	    if(temp==rev){
	        System.out.println("palindrome");
	    }else{
	        System.out.println("not a palindrome");
	    }
	}
}


////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

 Sum of a Number

import java.util.*;
public class Main
{
	public static void main(String[] args) {
		Scanner sc=new Scanner(System.in);
		int n=sc.nextInt();
		sum(n);
		
	}
	public static void sum(int n){
	    int s=0;
	    while(n>0){
	        int dig=n%10;
	        s=s+dig;
	        n=n/10;
	    }
	    System.out.println(s);
	}
}

/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
                                                              PATTERNS ♥️
1
2 3
4 5 6
7 8 9 10

import java.util.*;
public class Main
{
	public static void main(String[] args) {
		Scanner sc=new Scanner(System.in);
		int n=sc.nextInt();
		pattern(n);
	}
	public static void pattern(int n){
	    int count=1;
	   for(int i=1;i<=n;i++){
	       for(int j=1;j<=i;j++){
	           System.out.print(count+" ");
	           count++;
	       }
	       System.out.println();
	   }
	}
}


///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

******
*    *
*    *
*    *
******

import java.util.*;
public class Main
{
	public static void main(String[] args) {
		Scanner sc=new Scanner(System.in);
// 		int n=sc.nextInt();
		pattern(5);
	}
	public static void pattern(int n){
	   for(int i=1;i<=5;i++){
	       for(int j=1;j<=5;j++){
	           if(i==1||j==1||i==5||j==5){
	               System.out.print("* ");
	           }else{
	               System.out.print("  ");
	           }
	       }
	       System.out.println();
	   }
	}
}

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

*
**
***
****
*****

public class Main
{
	public static void main(String[] args) {
// 		Scanner sc=new Scanner(System.in);
		for(int i=1;i<=5;i++){
		    for(int j=1;j<=i;j++){
		        System.out.print("*");
		    }
		    System.out.println();
		}
	}
}

/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

 *****
 ****
 ***
 **
 *

public class Main
{
	public static void main(String[] args) {
// 		Scanner sc=new Scanner(System.in);
		for(int i=5;i>=1;i--){
		    for(int j=1;j<=i;j++){   //for(int j=1;j<=(n-i+1);j++)
		        System.out.print("*");
		    }
		    System.out.println();
		}
	}
}
////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

1
1 2
1 2 3
1 2 3 4
1 2 3 4 5

public class Main
{
	public static void main(String[] args) {
	//Scanner sc=new Scanner(System.in);
	  
		for(int i=1;i<=5;i++){
		    for(int j=1;j<=i;j++){
		        System.out.print(j);
		    }
		    System.out.println();
		}
	}
}

/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

1
2 2
3 3 3 
4 4 4 4 
5 5 5 5 5

public class Main
{
	public static void main(String[] args) {
	//Scanner sc=new Scanner(System.in);
	  
		for(int i=1;i<=5;i++){
		    for(int j=1;j<=i;j++){
		        System.out.print(i);
		    }
		    System.out.println();
		}
	}
}

///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

A
B C
D E F
G H I J
K L M N O

public class Main
{
	public static void main(String[] args) {
	//Scanner sc=new Scanner(System.in);
	    char ch='A';
		for(int i=1;i<=5;i++){
		    for(int j=1;j<=i;j++){
		        System.out.print(ch);
		        ch++;
		    }
		    System.out.println();
		}
	}
}


////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

1
0 1
1 0 1
0 1 0 1
1 0 1 0 1

import java.util.*;
public class Main
{
	public static void main(String[] args) {
	//Scanner sc=new Scanner(System.in);
		for(int i=1;i<=5;i++){
		    for(int j=1;j<=i;j++){
		        if((i+j)%2==0)
		        System.out.print("1");
                else
                System.out.print("0");
		    }
		    System.out.println();
		}
	}
}

///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

      * 
    * * * 
  * * * * * 
* * * * * * *
* * * * * * *
  * * * * * 
    * * * 
      * 


import java.util.*;
public class Main
{
	public static void main(String[] args) {
	  Scanner sc=new Scanner(System.in);
	  int n=sc.nextInt();
	  int spaces=n-1;
	  int stars=1;
	  for(int i=1;i<=n;i++){
	      for(int j=1;j<=spaces;j++){
	          System.out.print("  ");
	      }
	      for(int j=1;j<=stars;j++){
	          System.out.print("* ");
	      }
	      for(int j=1;j<=spaces;j++){
	          System.out.print("  ");
	      }
	      System.out.println();
	      spaces--;
	      stars+=2;
	  }
	  spaces=0;
	  stars=2*n-1;

	  
	  for(int i=1;i<=n;i++){
	      for(int j=1;j<=spaces;j++){
	          System.out.print("  ");
	  }
	  for(int j=1;j<=stars;j++){
	      System.out.print("* ");
	  }
	  for(int j=1;j<=spaces;j++){
	      System.out.print("  ");
	  }
	  System.out.println();
	  spaces++;
	  stars-=2;
      }
	}
}

///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

*             *
* *         * *
* * *     * * *
* * * * * * * *
* * * * * * * *
* * *     * * *
* *         * *
*             *


  import java.util.*;
public class Main
{
	public static void main(String[] args) {
	  Scanner sc=new Scanner(System.in);
	  int n=sc.nextInt();
	  for(int i=1;i<=n;i++){
	      for(int j=1;j<=i;j++){
	          System.out.print("* ");
	      }
	      for(int j=1;j<=2*(n-i);j++){
	          System.out.print("  ");
	      }
	      for(int j=1;j<=i;j++){
	          System.out.print("* ");
	      }
	      System.out.println();
	  }
	  
	  for(int i=n;i>=1;i--){
	      for(int j=1;j<=i;j++){
	          System.out.print("* ");
	      }
	      for(int j=1;j<=2*(n-i);j++){
	          System.out.print("  ");
	      }
	      for(int j=1;j<=i;j++){
	          System.out.print("* ");
	      }
	      System.out.println();
	  }
	}
}

///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

          *
        * *
      * * *
    * * * *
  * * * * *

import java.util.*;
public class Main
{
	public static void main(String[] args) {
	  Scanner sc=new Scanner(System.in);
	  int n=sc.nextInt();
	  for(int i=1;i<=n;i++){
	      for(int j=1;j<=n-i;j++){
	          System.out.print("  ");
	      }
	      for(int j=1;j<=i;j++){
	          System.out.print(" *");
	      }
	      System.out.println();
	  }
	}
}

////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////


1 2 3 4 5
1 2 3 4
1 2 3
1 2 
1 

import java.util.*;
public class Main
{
	public static void main(String[] args) {
	  Scanner sc=new Scanner(System.in);
	  int n=sc.nextInt();
	  for(int i=1;i<=n;i++){
	      for(int j=1;j<=n-i+1;j++){
	          System.out.print(j);
	      }
	      System.out.println();
	  }
	}
}

/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

 
     1
    2 2
   3 3 3
  4 4 4 4
 5 5 5 5 5

import java.util.*;
public class Main
{
	public static void main(String[] args) {
		Scanner sc=new Scanner(System.in);
		int n=sc.nextInt();
		for(int i=1;i<=n;i++){
		    for(int j=1;j<=5-i;j++){
		        System.out.print(" ");
		    }
		    for(int j=1;j<=i;j++){
		        System.out.print(i);
		        if(j!=i){
		            System.out.print(" ");
		        }
		    }
		   for(int j=1;j<=5-i;j++){
		       System.out.print(" ");
		   }
		   System.out.println();
		}
	}
}

////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

            1
          2 1 2
        3 2 1 2 3
      4 3 2 1 2 3 4
    5 4 3 2 1 2 3 4 5


  import java.util.*;
public class Main
{
	public static void main(String[] args) {
		Scanner sc=new Scanner(System.in);
		int n=sc.nextInt();

      for(int i=1;i<=n;i++){
          for(int j=1;j<=10-2*i;j++){
              System.out.print(" ");
          }
          for(int j=i;j>=2;j--){
              System.out.print(j);
              System.out.print(" ");
          }
          for(int j=1;j<=i;j++){
              System.out.print(j);
              if(j!=i)
             { System.out.print(" ");}
          }
             for(int j=1;j<=10-2*i;j++){
              System.out.print(" ");
          }
          System.out.println();
      }
	}
}

///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////


Linear Search

 int search(int arr[], int N, int X)
    {
        
        // Your code here
        for(int i=0;i<N;i++){
            if(arr[i]==X){
                return i;
            }
        }
        return -1;
        
    }


///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
 
Binary Search

class Solution {
  public:
    int binarysearch(int arr[], int n, int k) {
        int low=0;
        int high=n-1;
        while(low<=high){
            int mid=(low+high)/2;
            if(arr[mid]==k){
                return mid;
            }else if(arr[mid]>k){
                high=mid-1;
            }else{
                low=mid+1;
            }
        }
        return -1;
    }
};

/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Second largest in an array


class Solution {
    int print2largest(int arr[], int n) {
       int seclarg=Integer.MIN_VALUE;
	   int larg=Integer.MIN_VALUE;
	   for(int i=0;i<n;i++){
	       if(arr[i]>larg){
	           seclarg=larg;
	           larg=arr[i];
	       }else if(arr[i]>seclarg && arr[i]<larg){
	           seclarg=arr[i];
	       }
	   }
	   if(seclarg==Integer.MIN_VALUE){
	       seclarg=-1;
	   }
	   return seclarg;
    }
}

///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Largest element in an array

class Compute {
    
    public int largest(int arr[], int n)
    {
        int max=0;
        for(int i=0;i<n;i++){
            if(arr[i]>max){
                max=arr[i];
            }
        }
        return max;
    }
}

///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////


Reverse of an Array

import java.util.*;
public class Main
{
	public static void main(String[] args) {
	    int arr[]={2,3,4,5,6,};
	    reverse(arr);
	    for(int i=0;i<arr.length;i++){
	    System.out.print(arr[i]+" ");
	    }
	}
	public static void reverse(int arr[]){
	    int n=arr.length;
	    int low=0;
	    int high=n-1;
	    while(low<high){
	        int temp=arr[low];
	        arr[low]=arr[high];
	        arr[high]=temp;
	        low++;
	        high--;
	}
  }
}

/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////


Smallest number of an Array

import java.util.*;
public class Main
{
	public static void main(String[] args) {
	    int arr[]={2,3,4,5,6,1};
	    smallest(arr);
	}
	public static void smallest(int arr[]){
	    int n=arr.length;
	    int min=Integer.MAX_VALUE;
	    for(int i=0;i<n;i++){
	        if(arr[i]<min){
	            min=arr[i];
	        }
	    }
	    System.out.println(min);
  }
}

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

SubArray of an Array

import java.util.*;
public class Main
{
	public static void main(String[] args) {
	    int arr[]={1,2,3};
	    subarray(arr);
	}
	public static void subarray(int arr[]){
	    int n=arr.length;
	    for(int i=0;i<n;i++){
	        for(int j=i;j<n;j++){
	            for(int k=i;k<=j;k++){
	                System.out.print(arr[k]+ " ");
	            }
	             System.out.println();
	        }
	        System.out.println();
	    }
  }
}

////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Binary coeficient

public class Main
{
	public static void main(String[] args) {
	 System.out.println(bin_coefficient(5,2));
	}
	
	public static int factorial(int n){
	    int fact=1;
	    for(int i=1;i<=n;i++){
	        fact=fact*i;
	    }
	   return fact;
	}
	
	public static int bin_coefficient(int n,int r){
	  int fact_n=factorial(5);
	  int fact_r=factorial(2);
	  int factnmr=factorial(5-2);
	  int bincoff=fact_n/(fact_r*factnmr);
	  return bincoff;
	}

}


////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Binary to decimal

import java.util.*;
public class Main
{
	public static void main(String[] args) {
		int n=111;
		System.out.print(binarytodecimal(n));
	}
	public static int binarytodecimal(int n){
	    int pow=0;
	    int decnum=0;
	    while(n!=0){
	        int lastdigit=n%10;
	        decnum=decnum+(lastdigit*(int)Math.pow(2,pow));
	        n=n/10;
	        pow++;
	    }
	    return decnum;
	}
}

/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Decimal to binary

import java.util.*;
public class Main
{
	public static void main(String[] args) {
		int n=7;
		System.out.print(decimaltobinary(n));
	}
	public static int decimaltobinary(int n){
	    int pow=0;
	    int decnum=0;
	    while(n!=0){
	        int rem=n%2;
	        decnum=decnum+(rem*(int)Math.pow(10,pow));
	        n=n/2;
	        pow++;
	    }
	    return decnum;
	}
}


//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Trapped rainwater


import java.util.*;
public class Main
{
	public static void main(String[] args) {
		int arr[]={4,2,0,6,3,2,5};
		System.out.print(trappedrainwater(arr));
	}
	public static int trappedrainwater(int[] arr){
	    int left[]=new int[arr.length];
	     left[0]=arr[0];
	     for(int i=1;i<arr.length;i++){
	         left[i]=Math.max(left[i-1],arr[i]);
	     }
	     
	     int right[]=new int[arr.length];
	     right[arr.length-1]=arr[arr.length-1];
	     for(int i=arr.length-2;i>=0;i--){
	         right[i]=Math.max(right[i+1],arr[i]);
	     }
	     int trappedwater=0;
	     for(int i=0;i<arr.length;i++){
	        int waterlevel=Math.min(left[i],right[i]);
	        trappedwater+=waterlevel-arr[i];
	     }
	     return trappedwater;
	  
	    
	}
}
//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Buy and sell prices

public class Main
{
	public static void main(String[] args) {
	  int []prices={7,1,5,3,6,4};
	  System.out.print(buyandsell(prices));
	}
	public static int buyandsell(int []prices){
	    int maxprofit=0;
	    int buyprice=Integer.MAX_VALUE;
	    for(int i=0;i<prices.length;i++){
	        if(buyprice<prices[i]){
	            int profit=prices[i]-buyprice;
	            maxprofit=Math.max(maxprofit,profit);
	        }else{
	            buyprice=prices[i];
	        }
	    }
	    return maxprofit;
	    
	}
}
//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Bubble sort

public class Main
{
	public static void main(String[] args) {
		int arr[]={5,1,3,4,2};
		bubblesort(arr);
		printarray(arr);
	}
	public static void bubblesort(int []arr){
	    for(int i=0;i<arr.length-1;i++){
	        for(int j=0;j<arr.length-1-i;j++){
	            if(arr[j]>arr[j+1]){
	                int temp=arr[j];
	                arr[j]=arr[j+1];
	                arr[j+1]=temp;
	            }
	        }
	    }
	}
	public static void printarray(int []arr){
	    for(int i=0;i<arr.length;i++){
	        System.out.print(arr[i]+" ");
	    }
	}
}

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
