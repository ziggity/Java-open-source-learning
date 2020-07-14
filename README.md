

 # Java open source 

*This is an open source knowledge share on all things Java CS related*

## Algorithms

## Time Complexity

## Arrays
*The following example is how to create an array and fill it with numbers using Java.

int[] myArray = new int[20];  //Creates an array of size 20 to store integers
String[] myArray = new String[20];  //Creates an array of size 20 to store String and type this out in your code 	System.out.println(myArray.length); which will result in 20


for(int i = 0; i < myArray.length; i++) { 

    myArray[i] = i;

}
//myArray.length = 20, i = 0, loop until i > 19
//On each iteration, myArray at index i will contain the current value of i
//When this loop finishes, myArray will contain 0,1,2,3,4,5,6,7,8,9... 19 in that order
Arrays are the simplest data structure you will be dealing with, but they are incredibly useful and have a huge amount of applications. Many complex data structures use arrays in some way. For example, you can represent a graph structure as a matrix, or two dimensional array, of connected edges. You can efficiently sort data without using any extra memory using a heap structure, which at its most basic form is just an array that can be sorted in place. Once you grasp arrays, you will be able to grasp the more complex structures much more easily.*

## Sorting
*There are many algorithms/ways to sort an array. Among them the most commonly used are

Bubble Sort(code is below)
Heap Sort
Merge Sort
Bucket Sort
Insertion Sort(code is below)
Selection Sort(code is below)
Before going into a discussion on these type of sorting, we must learn the basics of arranging elements in one order(ASC or DSC).

import java.util.Arrays;
import java.util.Collections;
import java.util.List;
public class Demon implements Cloneable {
	public static void main(String[] args) {
		//First way using sorting algorithm
		Integer a[]={11,2,2,33,33,4,5,6,0,9};
		for(int i=0;i<a.length;i++)
			for(int j=0;j<a.length;j++){
				if(a[i]<a[j]){
					a[i]=a[i]+a[j];
					a[j]=a[i]-a[j];
					a[i]=a[i]-a[j];
					
				}
			}
		System.out.println("First way using sorting algorithm");
		System.out.println("maximum element is "+a[a.length-1]);
		System.out.println("minimum element is "+a[0]);
		
		//Second way.....
		System.out.println("Second way using Arrays.sort()...");
		Integer b[]={11,2,2,33,33,4,5,6,0,9};
		Arrays.sort(b);
		System.out.println("maximum element is "+b[b.length-1]);
		System.out.println("minimum element is "+b[0]);
		
		//Third way.......
		System.out.println("Third way using Collections.sort()...");
		Integer c[]={11,2,2,33,33,4,5,6,0,9};
		List<Integer> list = Arrays.asList(c);
		Collections.sort(list);
		c = (Integer[]) list.toArray();
		System.out.println("maximum element is "+c[c.length-1]);
		System.out.println("minimum element is "+c[0]);
	
	}
} 
Selection Sort:


In the above example, it has an array [ 4,2,5,1,3] which need to be sorted in ascending order [1,2,3,4,5] using selection sort.

import java.util.Arrays;
public class Demo {
	public static void main(String[] args) {
		int a[] = { 4, 2, 5, 1, 3, 0 };
		System.out.println("Array before sorting " + Arrays.toString(a));
		a = selectionSortAlg(a, a.length);
		System.out.println("Array after sorting " + Arrays.toString(a));
	}
	private static int[] selectionSortAlg(int[] a, int n) {
		for (int i = 0; i < n - 1; i++) {
			int iMin = i;
			for (int j = i + 1; j < n; j++) {
				if (a[j] < a[iMin]) {
					iMin = j; // index of smallest element
				}
			}
			int temp = a[i];
			a[i] = a[iMin];
			a[iMin] = temp;
			System.out.println("Pass..." + i + "..." + Arrays.toString(a));
		}
		return a;
	}
}
ouput

Array before sorting [4, 2, 5, 1, 3, 0]
Pass...0...[0, 2, 5, 1, 3, 4]
Pass...1...[0, 1, 5, 2, 3, 4]
Pass...2...[0, 1, 2, 5, 3, 4]
Pass...3...[0, 1, 2, 3, 5, 4]
Pass...4...[0, 1, 2, 3, 4, 5]
Array after sorting [0, 1, 2, 3, 4, 5]
….

Bubble Sort


workflow

Before sorting...[7, 2, 4, 1, 5, 3]
[2, 4, 1, 5, 3, 7]
[2, 1, 4, 3, 5, 7]
[1, 2, 3, 4, 5, 7]
[1, 2, 3, 4, 5, 7]
[1, 2, 3, 4, 5, 7]
Before sorting...[1, 2, 3, 4, 5, 7]
code: This is a simplest and easiest algorithm, which I love very much

public int[] bubbleSort(int n, int... a) {
		for (int j = 0; j < n - 1; j++){
			for (int i = 0; i < n - 1; i++) {
				if (a[i] > a[i + 1]) {
					int temp = a[i];
					a[i] = a[i + 1];
					a[i + 1] = temp;
				}
			}
			System.out.println(Arrays.toString(a));
		}
		return a;
	}
Insertion Sort:


code

import java.util.Arrays;
public class Demo {
	public static void main(String[] args) {
		int a[] = {7,2,4,1,5,3}; //{ 4, 2, 5, 1, 3, 0 };
		System.out.println("Array before sorting " + Arrays.toString(a));
		a = insertionSortAlg(a, a.length);
		System.out.println("Array after sorting " + Arrays.toString(a));
	}
	private static int[] insertionSortAlg(int[] a, int n) {
		for (int i = 1; i < n ; i++) {
			for (int j = i; j > 0 && j <= i; j--) {
				if (a[j - 1] > a[j]) {
					int temp = a[j - 1];
					a[j - 1] = a[j];
					a[j] = temp;
				}
			}
			System.out.println("pass "+i+"..."+Arrays.toString(a));
		}
		return a;
	}
output:

Array before sorting [7, 2, 4, 1, 5, 3]
pass 1...[2, 7, 4, 1, 5, 3]
pass 2...[2, 4, 7, 1, 5, 3]
pass 3...[1, 2, 4, 7, 5, 3]
pass 4...[1, 2, 4, 5, 7, 3]
pass 5...[1, 2, 3, 4, 5, 7]
Array after sorting [1, 2, 3, 4, 5, 7]
Merge Sort:

Quick Sort

Sorting algorithms in java - Java2Blog
Sorting Algorithms - YouTube

Conclusion:
1)Insertion Sort(Next element is compared with previous element).

Array before sorting [7, 2, 4, 1, 5, 3]
pass 1...[2, 7, 4, 1, 5, 3]
pass 2...[2, 4, 7, 1, 5, 3]
pass 3...[1, 2, 4, 7, 5, 3]
pass 4...[1, 2, 4, 5, 7, 3]
pass 5...[1, 2, 3, 4, 5, 7]
Array after sorting [1, 2, 3, 4, 5, 7]
2)Selection Sort(the First element is replaced with the lowest element in an array).

Array before sorting [4, 2, 5, 1, 3, 0]
Pass...0...[0, 2, 5, 1, 3, 4]
Pass...1...[0, 1, 5, 2, 3, 4]
Pass...2...[0, 1, 2, 5, 3, 4]
Pass...3...[0, 1, 2, 3, 5, 4]
Pass...4...[0, 1, 2, 3, 4, 5]
Array after sorting [0, 1, 2, 3, 4, 5]
3)Bubble Sort(First element is compared with adjacent if not in order, then swap it)

Before sorting...[7, 2, 4, 1, 5, 3]
[2, 4, 1, 5, 3, 7]
[2, 1, 4, 3, 5, 7]
[1, 2, 3, 4, 5, 7]
[1, 2, 3, 4, 5, 7]
[1, 2, 3, 4, 5, 7]
Before sorting...[1, 2, 3, 4, 5, 7]

java.util.Arrays class has a overloaded static sort method. This can be used to sort an array of primitives or objects. There is also a parallelSort method.

Sorting an array of primitives

int [] intArr = {10, 4, 45, 6, -11, 9870, 99};
Arrays.sort(intArr);
System.out.println(Arrays.toString(intArr));
The output: [-11, 4, 6, 10, 45, 99, 9870]

Note the sorting order is ascending, by default.

All primitives (byte, int, float, char, etc.) and Java objects which implement java.lang.Comparable (String, Date, File, LocalDate, Integer, etc.) can use this version of the method. An example:


What are different ways to sort an array? (irrespective of platform)
What are different ways to ‘X’ sort in java? (Where X maybe insertion sort, selection, bubble sort…..)
The answer for Q.1

Insertion Sort
Quick Sort
Merge Sort
Heap Sort
Shell Sort
Bubble sort.
The answer for Q.2

I will take Bubble sort to explain this

1.

void swap(int *xp, int *yp)

{

 int temp = *xp;

 *xp = *yp;

 *yp = temp;

}

void bubbleSort(int arr[], int n)

{

 int i, j;

 for (i = 0; i < n-1; i++)  

 for (j = 0; j < n-i-1; j++) 

 if (arr[j] > arr[j+1])

 swap(&arr[j], &arr[j+1]);

}
*

## Searching

## String Techniques

## Two Pointer Technique

## Linked Lists

## Stacks and Queues

## Binary Trees

## Binary Search Trees

## Recursion

## Backtracking

## Dynamic Programming

## Greedy Algorithms

## Graphs

## 








### The README: Let us know which topics you'd like listed here in the issues tab



### List of helpful code websites to practice


1. *Hackerrank*  `www.hackerrank.com` 
   
2. *CodeSignal* -- 

3. *CodeBat* --

4. *Codewars* -- 

5. *Leetcode* 

6. *Pramp* 








## Bonus: websites that are helpful



- https://javadocs.com


## Bonus: The Java open source Checklist

A helpful checklist to gauge how your learning is coming along:

- [ ] OOP topics understood?
- [ ] Algorithms mastered? Brute-force and Optimized solutions understood?
- [ ] APIs built? SpringBoot framework?
- [ ] Read a few books on Java? Deittel Java objects, and Effective Java are good starting points.
- [ ] Built a CRUD app with Java? SQL database? 
- [ ] Java flashcards? 



## The authors

I'm [Zach Beecher](https://github.com/ziggity/). 


This little project began back in July 2020

## Further Reading





## Footnotes

1. <a name="footnote-1"></a>Thanks,


## Credits




   