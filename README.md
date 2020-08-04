

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
*Linear Search
Binary Search
Knuth Morris Pratt Pattern Search
Jump Search
Interpolation Search
Exponential Search
Fibonacci Search
Java Collections API
Linear Search
Linear or Sequential Search is the simplest of search algorithms. While it most certainly is the simplest, it's most definitely not the most common, due to its inefficiency. It's a brute-force algorithm. Very rarely is it used in production, and in most cases, it's outperformed by other algorithms.

Linear Search has no pre-requisites for the state of the underlying data structure.

Explanation
Linear Search involves sequential searching for an element in the given data structure until either the element is found or the end of the structure is reached.

If the element is found, we usually just return its position in the data structure. If not, we usually return -1.

Implementation
Now let's see how to implement Linear Search in Java:

public static int linearSearch(int arr[], int elementToSearch) {

    for (int index = 0; index < arr.length; index++) {
        if (arr[index] == elementToSearch)
            return index;
    }
    return -1;
}
To test it, we'll use a simple Array of integers:

int index = linearSearch(new int[]{89, 57, 91, 47, 95, 3, 27, 22, 67, 99}, 67);
print(67, index);
With a simple helper method to print the result:

public static void print(int elementToSearch, int index) {
    if (index == -1){
        System.out.println(elementToSearch + " not found.");
    }
    else {
        System.out.println(elementToSearch + " found at index: " + index);
    }
}
Output:

67 found at index: 8
Time Complexity
Here we are iterating through the entire set of N elements sequentially to get the location of the element being searched. The worst case for this algorithm will be if the element we are searching for is the last element in the array.

In this case, we will iterate N times before we find the element.

Hence, the Time Complexity of Linear search is O(N).

Space Complexity
This type of search requires only a single unit of memory to store the element being searched. This is not relevant to the size of the input Array.

Hence, the Space Complexity of Linear Search is O(1).

Applications
Linear Search can be used for searching in a small and unsorted set of data which is guaranteed not to increase in size by much.

It is a very basic search algorithm but due to its linear increase in time complexity, it does not find application in many production systems.

Binary Search
Binary or Logarithmic Search is one of the most commonly used search algorithms primarily due to its quick search time.

Explanation
This kind of search uses the Divide and Conquer methodology and requires the data set to be sorted beforehand.

It divides the input collection into equal halves, and with each iteration compares the goal element with the element in the middle.

If the element is found, the search ends. Else, we continue looking for the element by dividing and selecting the appropriate partition of the array, based on if the goal element is smaller or bigger than the middle element.

This is why it's important to have a sorted collection for Binary Search.

The search terminates when the firstIndex (our pointer) goes past lastIndex (last element), which implies we have searched the whole array and the element is not present.

There are two ways to implement this algorithm - iterative and recursive.

There shouldn't be a difference regarding time and space complexity between these two implementations, though this doesn't hold true to all languages.

Implementation
Iterative
Let's first take a look at the iterative approach:

public static int binarySearch(int arr[], int elementToSearch) {

    int firstIndex = 0;
    int lastIndex = arr.length - 1;

    // termination condition (element isn't present)
    while(firstIndex <= lastIndex) {
        int middleIndex = (firstIndex + lastIndex) / 2;
        // if the middle element is our goal element, return its index
        if (arr[middleIndex] == elementToSearch) {
            return middleIndex;
        }

        // if the middle element is smaller
        // point our index to the middle+1, taking the first half out of consideration
        else if (arr[middleIndex] < elementToSearch)
            firstIndex = middleIndex + 1;

        // if the middle element is bigger
        // point our index to the middle-1, taking the second half out of consideration
        else if (arr[middleIndex] > elementToSearch)
            lastIndex = middleIndex - 1;

    }
    return -1;
}
We can use the algorithm like this:

int index = binarySearch(new int[]{89, 57, 91, 47, 95, 3, 27, 22, 67, 99}, 67);
print(67, index);
Output:

67 found at index: 5
Recursive
And now let's take a look at the recursive implementation:

public static int recursiveBinarySearch(int arr[], int firstElement, int lastElement, int elementToSearch) {

    // termination condition
    if (lastElement >= firstElement) {
        int mid = firstElement + (lastElement - firstElement) / 2;

        // if the middle element is our goal element, return its index
        if (arr[mid] == elementToSearch)
            return mid;

        // if the middle element is bigger than the goal element
        // recursively call the method with narrowed data
        if (arr[mid] > elementToSearch)
            return recursiveBinarySearch(arr, firstElement, mid - 1, elementToSearch);

        // else, recursively call the method with narrowed data
        return recursiveBinarySearch(arr, mid + 1, lastElement, elementToSearch);
    }

    return -1;
}
The difference in the recursive approach is that we invoke the method itself once we get the new partition. In the iterative approach, whenever we determined the new partition we modified the first and last elements and repeated the process in the same loop.

Another difference here is that recursive calls are pushed on the method call-stack and they occupy one unit of space per recursive call.

We can use this algorithm like this:

int index = binarySearch(new int[]{3, 22, 27, 47, 57, 67, 89, 91, 95, 99}, 0, 10, 67);
print(67, index);
Output:

67 found at index: 5
Time Complexity
Since Binary Search divides the array into half each time its time complexity is O(log(N)). This time complexity is a marked improvement on the O(N) time complexity of Linear Search.

Space Complexity
This search requires only one unit of space to store the element to be searched. Hence, its space complexity is O(1).

If Binary Search is implemented recursively, it needs to store the call to the method on a stack. This may require O(log(N)) space in the worst case scenario.

Applications
It is the most commonly used search algorithm in most of the libraries for searching. The Binary Search tree is used by many data structures as well which store sorted data.

Binary Search is also implemented in Java APIs in the Arrays.binarySearch method.

Knuth Morris Pratt Pattern Search
As the name indicates, it is an algorithm for finding a pattern in the given text. This algorithm was developed by Donald Knuth, Vaughan Pratt, and James Morris, hence the name.

Explanation
In this search, the given pattern is first compiled. By compiling it, we try to find the prefix and suffix of the pattern string. This helps us when a mismatch happens - we will not start looking for the next match from the beginning of the index.

Instead, we skip the part of text string which we have already compared and start comparing beyond that part. We determine this part by knowing the prefix and suffix so we are sure what part is already compared and can be safely skipped.

As a result of this skip, we can save a lot of comparisons and KMP performs faster than a naive brute-force algorithm.

Implementation
Let's create the compilePatternArray() method, which will be used later by the KMP search algorithm:

public static int[] compilePatternArray(String pattern) {
    int patternLength = pattern.length();
    int len = 0;
    int i = 1;
    int[] compliedPatternArray = new int[patternLength];
    compliedPatternArray[0] = 0;

    while (i < patternLength) {
        if (pattern.charAt(i) == pattern.charAt(len)) {
            len++;
            compliedPatternArray[i] = len;
            i++;
        } else {
            if (len != 0) {
                len = compliedPatternArray[len - 1];
            } else {
                compliedPatternArray[i] = len;
                i++;
            }
        }
    }
    System.out.println("Compiled Pattern Array " + Arrays.toString(compliedPatternArray));
    return compliedPatternArray;
}
The compiled pattern array can be thought of as an array storing the pattern of characters in the pattern array. The main aim behind creating this array is to find the prefix and suffix in the pattern. If we know these elements in the pattern, we can avoid comparing from the start of the text and just compare next character after the mismatch has occurred.

The compiled array stores the index position of previous occurrence of the current character in the pattern array.

Let's implement the algorithm itself:

public static List<Integer> performKMPSearch(String text, String pattern) {
    int[] compliedPatternArray = compilePatternArray(pattern);

    int textIndex = 0;
    int patternIndex = 0;

    List<Integer> foundIndexes = new ArrayList<>();

    while (textIndex < text.length()) {
        if (pattern.charAt(patternIndex) == text.charAt(textIndex)) {
            patternIndex++;
            textIndex++;
        }
        if (patternIndex == pattern.length()) {
            foundIndexes.add(textIndex - patternIndex);
            patternIndex = compliedPatternArray[patternIndex - 1];
        }

        else if (textIndex < text.length() && pattern.charAt(patternIndex) != text.charAt(textIndex)) {
            if (patternIndex != 0)
                patternIndex = compliedPatternArray[patternIndex - 1];
            else
                textIndex = textIndex + 1;
        }
    }
    return foundIndexes;
}
Here we start by comparing the characters in the pattern and text array sequentially. We keep moving forward until we keep getting a match of pattern and text arrays. This way, if we reach the end of the pattern array while matching it means we have found an occurrence of the pattern in the text.

However, if we find a mismatch when comparing the two arrays, we move the pattern character array index to the value in the compiledPatternArray() and also move to the next character in the text array. This is where the KMP search beats the brute-force approach, as it doesn't compare the text characters more than once if there is a mismatch.

Let's try running the algorithm:

String pattern = "AAABAAA";
String text = "ASBNSAAAAAABAAAAABAAAAAGAHUHDJKDDKSHAAJF";

List<Integer> foundIndexes = KnuthMorrisPrathPatternSearch.performKMPSearch(text, pattern);

if (foundIndexes.isEmpty()) {
    System.out.println("Pattern not found in the given text String");
} else {
    System.out.println("Pattern found in the given text String at positions: " + .stream().map(Object::toString).collect(Collectors.joining(", ")));
}
In the pattern text AAABAAA, the following pattern is observed and encoded in the pattern array:

The pattern A (Single A) is repeating in index 1 and again at 4.
The pattern AA (Double A) is repeating in index 2 and again at index 5.
The pattern AAA (3 A's) is repeating at index 6.
Let's see the output to validate our discussion so far:

Compiled Pattern Array [0, 1, 2, 0, 1, 2, 3]
Pattern found in the given text String at positions: 8, 14
The pattern we described is clearly shown to us in the complied pattern array in the output.

With the help of this compiled array, the KMP search algorithm can search for the given pattern in the text without moving back in the text array.

Time Complexity
This algorithm needs to compare all the elements in the given text to find the pattern. The time required for that is O(N) . For compiling the pattern string we need to visit each of the character in the pattern and that is another O(M) iterations.

So the total time this algorithm takes will be O(M+N).

Space Complexity
We need O(M) space to store the compiled pattern for a given pattern of size M

Applications
This algorithm is particularly employed in text tools for finding patterns in text files.

Jump Search
Explanation
This search is similar to Binary Search but instead of jumping both forward and backward - we will only jump forward. Keep in mind that Jump Search also requires for the collection to be sorted.

In Jump Search, we jump in the interval sqrt(arraylength) ahead until we reach an element greater than current element or end of the array. On every jump, the previous step is recorded.

If we encounter an element greater than the element we are searching for, we stop jumping. Then, we run a Linear Search between the previous step and the current step.

This makes the search space a lot smaller for Linear Search, and thus it becomes a viable option.

Implementation
public static int jumpSearch(int[] integers, int elementToSearch) {

    int arrayLength = integers.length;
    int jumpStep = (int) Math.sqrt(integers.length);
    int previousStep = 0;

    while (integers[Math.min(jumpStep, arrayLength) - 1] < elementToSearch) {
        previousStep = jumpStep;
        jumpStep += (int)(Math.sqrt(arrayLength));
        if (previousStep >= arrayLength)
            return -1;
    }
    while (integers[previousStep] < elementToSearch) {
        previousStep++;
        if (previousStep == Math.min(jumpStep, arrayLength))
            return -1;
    }

    if (integers[previousStep] == elementToSearch)
        return previousStep;
    return -1;
}
We start with the jumpstep of size square-root of the length of array and keep jumping forward with this same size until we find an element which is same or greater than the element we are searching for.

So we first visit element at integers[jumpStep], then integers[2jumpStep], integers[3jumpStep] and so on. We also store the previous element visited in the previousStep variable.

Once we find a value such that integers[previousStep] < elementToSearch < integers[jumpStep], we perform a linear search between integers[previousStep] and integers[jumpStep] or an element greater than elementToSearch.

We can use the algorithm like this:

int index = jumpSearch(new int[]{3, 22, 27, 47, 57, 67, 89, 91, 95, 99}, 67);
print(67, index);
Output:

67 found at Index 5
Time Complexity
Since we jump sqrt(arraylength) steps in each iteration, the time complexity for this search is O(sqrt(N)).

Space Complexity
The space complexity for this search is O(1) as it requires only one unit of space to store the element to be searched.

Application
This search is used over Binary Search when jumping back is costly. This constraint is faced when we use spinning medium like drives when seeking forward is easy but jumping in changed direction multiple times is costly.

Interpolation Search
Explanation
Interpolation Search is used to search elements in a sorted array. This search is particularly useful if we know the data in the underlying structure is uniformly distributed.

If the data is uniformly spread out, taking a guess about the location of an element can be more precise, opposed to Binary Search where we always try to find the element in the middle of the array.

Interpolation Search uses interpolation formulae to find the best probable place where the element can be found in the array. However, for this formulae to be effective the search array should be large otherwise it performs like Linear Search:

Implementation
public static int interpolationSearch(int[] integers, int elementToSearch) {

    int startIndex = 0;
    int lastIndex = (integers.length - 1);

    while ((startIndex <= lastIndex) && (elementToSearch >= integers[startIndex]) &&
           (elementToSearch <= integers[lastIndex])) {
        // using interpolation formulae to find the best probable position for this element to exist
        int pos = startIndex + (((lastIndex-startIndex) /
          (integers[lastIndex]-integers[startIndex]))*
                        (elementToSearch - integers[startIndex]));

        if (integers[pos] == elementToSearch)
            return pos;

        if (integers[pos] < elementToSearch)
            startIndex = pos + 1;

        else
            lastIndex = pos - 1;
    }
    return -1;
}
We can use this algorithm like this:

int index = interpolationSearch(new int[]{1,2,3,4,5,6,7,8}, 6);
print(67, index);
Output:

6 found at Index 5
Let's take a look at how the interpolation formulae works its magic to look for 6:

startIndex = 0
lastIndex = 7
integers[lastIndex] = 8
integers[startIndex] = 1
elementToSearch = 6
Now let's apply this values to the formulae to estimate the index of search Element:

i
n
d
e
x
=
0
+
(
7
−
0
)
/
(
8
−
1
)
∗
(
6
−
1
)
=
5
The element at integers[5] is 6 which is the element we were looking for. As we can see here, the index for the element is calculated in just one step since the data is uniformly spread.

Time Complexity
The best case time complexity for this algorithm is O(log log N) but in the worst case, i.e. when the elements are not uniformly distributed, it is comparable to linear search time complexity which is O(N).

Space Complexity
This algorithm also requires only one unit of space to store the element to be searched. Hence its space complexity is O(1).

Application
This search is useful when the data is uniformly distributed like Phone Numbers in a directory.

Exponential Search
Explanation
Exponential Search is used to search elements by jumping in exponential positions i.e. in powers of 2.

In this search we are basically trying to find a comparatively smaller range in which we can search the element using other bounded searches algorithms like Binary Search.

Needless to say, the collection should be sorted for this to work.

Implementation
public static int exponentialSearch(int[] integers, int elementToSearch) {

    if (integers[0] == elementToSearch)
        return 0;
    if (integers[integers.length - 1] == elementToSearch)
        return integers.length;

    int range = 1;

    while (range < integers.length && integers[range] <= elementToSearch) {
        range = range * 2;
    }

    return Arrays.binarySearch(integers, range / 2, Math.min(range, integers.length), elementToSearch);
}
We can use this algorithm like this:

int index = exponentialSearch(new int[]{3, 22, 27, 47, 57, 67, 89, 91, 95, 99}, 67);
print(67, index);
This is how the algorithm works:

We try to find an element which is greater than the element we are searching. We do this to minimise the range of elements we are looking for. We increase the range by multiplying it with 2 and check again if we reached an element greater than element we are searching or the end of array. Once either of this is achieved, we break out of the loop. Then we perform binary search with startIndex as range/2 and lastIndex as range.

In our case, this range value is achieved at 8 and the element at integers[8] is 95. So, the range where we perform binary search is:

startIndex = range/2 = 4

lastIndex = range = 8
With this the binary search call becomes:

Arrays.binarySearch(integers, 4, 8, 6);
Output:

67 found at Index 5
A important thing to note here we can speedup the multiplication by 2 by using the left shift operator range << 1instead of * operator.

Time Complexity
The worst-case time complexity for this type of search is O(log(N)).

Space Complexity
This algorithm requires O(1) space to store the element being searched if the underlying Binary Search algorithm is iterative.

If the underlying Binary Search algorithm is recursive, the space complexity becomes O(log(N)).

Applications
Exponential search is used when we have a huge or unbounded array. Applying Binary Search on the entire dataset may prove to be costly. Exponential Search can reduce this data into smaller, easily searchable partitions.

Fibonacci Search
Explanation
Fibonacci search employs divide and conquer approach wherein we unequally split element as per the Fibonacci series. This search requires the array to be sorted.

Unlike in Binary Search where we divide the elements into equal halves to reduce the array range - In Fibonacci search we try to use addition or subtraction to get a smaller range.

Remember the formula for Fibonacci series is:

F
i
b
o
(
N
)
=
F
i
b
o
(
N
−
1
)
+
F
i
b
o
(
N
−
2
)
The first two numbers in this series are Fibo(0) = 0 and Fibo(1) = 1. So as per this formula, the series looks like this 0, 1, 1, 2, 3, 5, 8, 13, 21... Interesting observations to note here is that:

Fibo(N-2) is approximately 1/3rd of Fibo(N)

Fibo(N-1) is approximately 2/3rd of Fibo(N)

So when we use fibonacci series numbers to partition the range it gets split in the same ratio as above.

Implementation
Let's take a look at the implementation to get a clearer idea:

public static int fibonacciSearch(int[] integers, int elementToSearch) {

    int fibonacciMinus2 = 0;
    int fibonacciMinus1 = 1;
    int fibonacciNumber = fibonacciMinus2 + fibonacciMinus1;
    int arrayLength = integers.length;

    while (fibonacciNumber < arrayLength) {
        fibonacciMinus2 = fibonacciMinus1;
        fibonacciMinus1 = fibonacciNumber;
        fibonacciNumber = fibonacciMinus2 + fibonacciMinus1;
    }

    int offset = -1;

    while (fibonacciNumber > 1) {
        int i = Math.min(offset+fibonacciMinus2, arrayLength-1);

        if (integers[i] < elementToSearch) {
            fibonacciNumber = fibonacciMinus1;
            fibonacciMinus1 = fibonacciMinus2;
            fibonacciMinus2 = fibonacciNumber - fibonacciMinus1;
            offset = i;
        }

        else if (integers[i] > elementToSearch) {
            fibonacciNumber = fibonacciMinus2;
            fibonacciMinus1 = fibonacciMinus1 - fibonacciMinus2;
            fibonacciMinus2 = fibonacciNumber - fibonacciMinus1;
        }

        else return i;
    }

    if (fibonacciMinus1 == 1 && integers[offset+1] == elementToSearch)
        return offset+1;

    return -1;
}
We can run this algorithm like this:

int index = fibonacciSearch(new int[]{3, 22, 27, 47, 57, 67, 89, 91, 95, 99}, 67);
print(67, index);
This is how the algorithm works:

It starts by first finding the number in the Fibonacci series closest to but more than the length of array. This happens when fibonacciNumber is at 13 which is just more than array length - 10.

Next, we compare the elements of the array and on the basis of that comparison , we take one of the below actions:

Compare the element to be searched with the element at fibonacciMinus2 and return the index if the value matches.
If the elementToSearch is greater than the current element, we move one step back in the fibonacci series and change the values of fibonacciNumber, fibonacciMinus1 & fibonacciMinus2 accordingly. The offset is reset to the current Index.
If the elementToSearch is smaller than the current element, we move two steps back in the fibonacci series and change the values of fibonacciNumber, fibonacciMinus1 & fibonacciMinus2 accordingly.
Output:

67 found at Index 5
Time Complexity
The worst-case time complexity for this search is O(log(N)).

Space Complexity
While we need to save the three numbers in Fibonacci series and the element to be searched we need four extra units of space.

This requirement of space does not increase with the size of the input array. Hence, we can say that the space complexity for Fibonacci search is O(1).

Applications
This search is used when the division is a costly operation for the CPU to perform. Algorithms like Binary Search tend to fare poorly as they use division to divide the array.

Another benefit of this search is when elements of the input array cannot fit into the RAM. In such situations, a localized scope of operation that this algorithm performs helps it to run much faster.

Java Collections API
Now that we have seen the implementation of multiple algorithms in Java, let's also take a brief look at the way searching is performed in different Java Collections.

Arrays
Arrays in Java can be searched using one of the java.util.BinarySearch methods. The binary Search in the Open JDK version uses the iterative form of the search.

Let's take a quick look at how we can use this method:

int[] integers = {3, 22, 27, 47, 57, 67, 89, 91, 95, 99};

int elementToSearch = 67;

int index = java.util.Arrays.binarySearch(integers, elementToSearch);
Output:

67 found at Index 5
The List Interface
The List Interface has primarily two methods which can be used for searching: indexOf() and contains().

The indexOf() method returns the index of the element if it exists in the list or -1 if it doesn't exist.

The contains() method returns true or false depending upon the existence of the element. It internally calls the indexOf() method.

The List interface uses Sequential Search to perform the index lookup and hence its time complexity is O(N).

Let's try out a search operation on a List:

java.util.List<Integer> integers = new java.util.ArrayList<>();
integers.add(3);
integers.add(22);
integers.add(27);
integers.add(47);
integers.add(57);
integers.add(67);
integers.add(89);
integers.add(91);
integers.add(95);
integers.add(99);

int elementToSearch = 67;

int index = integers.indexOf(elementToSearch);
Output:

67 found at Index 5
Similarly, if we are not interested in the index but only want to know if the element exists in the List or not we can use the contains() method:

integers.contains(67)
Output:

true
The Map Interface
The Map is a key-value pair data structure. The Map interface in Java uses HashBased searching as well as the Binary Search Tree.

The java.util.HashMap class uses a hash-value of the key to store the elements in the Map. Retrieving the element from the Map using right keys to hash and a good Hashing algorithm (such that no collisions occur) is O(1).

Another implementation of the Map interface is the java.util.TreeMap, which internally uses Red-Black Tree which is a type of self-balancing binary search tree. The elements added to this tree are automatically stored in the sorted fashion by the tree.

The time complexity of searching a Binary Tree is O(log(N)).

Let's see how we can search an element in a Map:

java.util.Map<Integer, String> integers = new java.util.HashMap<>();
integers.put(3,"three");
integers.put(22,"twentytwo");
integers.put(27,"twentyseven");
integers.put(47,"fortyseven");
integers.put(57,"fiftyseven");
integers.put(67,"sixtyseven");
integers.put(89,"eightynine");
integers.put(91,"ninetyone");
integers.put(95,"ninetyfive");
integers.put(99,"ninetynine");

String value = integers.get(67);

System.out.println("the value at key 67 is: " + value);
We have created a map with a key as an Integer and the value as that Integer in words. We then search for a key and get the Integer as words in the output.

An important thing to note here is that the map will not store duplicate keys. If we try to insert a duplicate value it will overwrite the existing key and value with the new one.

Output:

the value at key 67 is: sixtyseven
Map interface also contains the containsKey() method which can be used to determine if a given key exists or not:

integers.containsKey(67);
The Set Interface
The Set data-structure is used to store unique elements. The Set interface is essentially a wrapper over the Map interface described above storing elements in the Key of the Map.

As with the Map interface it uses the Binary and Hash-based search.

java.util.Set<Integer> integers = new java.util.HashSet<>();
integers.add(3);
integers.add(22);
integers.add(27);
integers.add(47);
integers.add(57);
integers.add(67);
integers.add(89);
integers.add(91);
integers.add(95);
integers.add(99);

int elementToSearch = 67;

boolean isNumberExists = integers.contains(elementToSearch);

if (isNumberExists)
    System.out.println(elementToSearch + " exists in the set");
else
    System.out.println(elementToSearch + " does not exist in the set");
There is no index in the Set interface and as such the search operation contains() returns true or false depending upon the existence of the element being searched.

In this case, since the element exists in the set we get the below output:

67 exists in the set
Search Algorithm Time Comparison
That being said, it's often useful to run all of these algorithms a few times to get an idea of how they perform.

Let's search for the element 573400 in a sorted array that's populated with a million integers.

Here are the results of the algorithms:

time(ns)	Linear	Binary (Iterative)	Binary (Recursive)	Jump	Interpolation	Exponential	Fibonacci
First Run	5 229 901	23 014	14 928	125 647	18 661	49 762	13 373
Second Run	8 436 389	24 570	14 306	329 046	18 349	206 820	21 770
Third Run	7 207 909	24 569	23 326	585 005	19 593	106 054	23 325
Fourth Run	5 888 615	33 589	27 057	218 327	23 015	111 341	25 813
Fifth Run	3 002 466	20 216	46 962	132 800	15 861	65 311	20 216
Sixth Run	6 896 901	12 440	26 124	212 107	7 465	106 054	38 254
Seventh Run	6 916 495	59 714	13 373	210 241	15 240	126 891	13 684
Eight Run	6 781 828	22 393	46 962	159 235	10 575	83 972	26 436
Ninth Run	6 917 116	11 507	18 660	265 911	28 302	130 002	12 751
Tenth Run	3 811 085	41 053	89 259	302 922	26 436	183 184	25 192
It's easy to see that Linear Search takes significantly longer than any other algorithm to search for this element, since it evaluated each and every element before the one we're searching for. If we were searching for the first element, Linear Search would be the most efficient one here.

It's also easy to see the Binary, Interpolation and Fibonacci Search show the best results for this particular array.

Conclusion
Every system has its own unique set of constraints and requirements. A correctly used search algorithm, based on those constraints, can go a long way in determining the performance of the system.
*

## String Techniques
*String is a sequence of characters, for e.g. “Hello” is a string of 5 characters. In java, string is an immutable object which means it is constant and can cannot be changed once it has been created. In this tutorial we will learn about String class and String methods in detail along with many other Java String tutorials.

Creating a String
There are two ways to create a String in Java

String literal
Using new keyword
String literal
In java, Strings can be created like this: Assigning a String literal to a String instance:

String str1 = "Welcome";
String str2 = "Welcome";
The problem with this approach: As I stated in the beginning that String is an object in Java. However we have not created any string object using new keyword above. The compiler does that task for us it creates a string object having the string literal (that we have provided , in this case it is “Welcome”) and assigns it to the provided string instances.

But if the object already exist in the memory it does not create a new Object rather it assigns the same old object to the new instance, that means even though we have two string instances above(str1 and str2) compiler only created on string object (having the value “Welcome”) and assigned the same to both the instances. For example there are 10 string instances that have same value, it means that in memory there is only one object having the value and all the 10 string instances would be pointing to the same object.

What if we want to have two different object with the same string? For that we would need to create strings using new keyword.

Using New Keyword
As we saw above that when we tried to assign the same string object to two different literals, compiler only created one object and made both of the literals to point the same object. To overcome that approach we can create strings like this:

String str1 = new String("Welcome");
String str2 = new String("Welcome");
In this case compiler would create two different object in memory having the same string.

A Simple Java String Example
public class Example{  
   public static void main(String args[]){  
	//creating a string by java string literal 
	String str = "Beginnersbook"; 
	char arrch[]={'h','e','l','l','o'}; 
	//converting char array arrch[] to string str2
	String str2 = new String(arrch); 
		
	//creating another java string str3 by using new keyword 
	String str3 = new String("Java String Example"); 
		
	//Displaying all the three strings
	System.out.println(str);  
	System.out.println(str2);  
	System.out.println(str3);  
   }
}
Output:

Here are the list of the methods available in the Java String class. These methods are explained in the separate tutorials with the help of examples. Links to the tutorials are provided below:

char charAt(int index): It returns the character at the specified index. Specified index value should be between 0 to length() -1 both inclusive. It throws IndexOutOfBoundsException if index<0||>= length of String.
boolean equals(Object obj): Compares the string with the specified string and returns true if both matches else false.
boolean equalsIgnoreCase(String string): It works same as equals method but it doesn’t consider the case while comparing strings. It does a case insensitive comparison.
int compareTo(String string): This method compares the two strings based on the Unicode value of each character in the strings.
int compareToIgnoreCase(String string): Same as CompareTo method however it ignores the case during comparison.
boolean startsWith(String prefix, int offset): It checks whether the substring (starting from the specified offset index) is having the specified prefix or not.
boolean startsWith(String prefix): It tests whether the string is having specified prefix, if yes then it returns true else false.
boolean endsWith(String suffix): Checks whether the string ends with the specified suffix.
int hashCode(): It returns the hash code of the string.
int indexOf(int ch): Returns the index of first occurrence of the specified character ch in the string.
int indexOf(int ch, int fromIndex): Same as indexOf method however it starts searching in the string from the specified fromIndex.
int lastIndexOf(int ch): It returns the last occurrence of the character ch in the string.
int lastIndexOf(int ch, int fromIndex): Same as lastIndexOf(int ch) method, it starts search from fromIndex.
int indexOf(String str): This method returns the index of first occurrence of specified substring str.
int lastindexOf(String str): Returns the index of last occurrence of string str.
String substring(int beginIndex): It returns the substring of the string. The substring starts with the character at the specified index.
String substring(int beginIndex, int endIndex): Returns the substring. The substring starts with character at beginIndex and ends with the character at endIndex.
String concat(String str): Concatenates the specified string “str” at the end of the string.
String replace(char oldChar, char newChar): It returns the new updated string after changing all the occurrences of oldChar with the newChar.
boolean contains(CharSequence s): It checks whether the string contains the specified sequence of char values. If yes then it returns true else false. It throws NullPointerException of ‘s’ is null.
String toUpperCase(Locale locale): Converts the string to upper case string using the rules defined by specified locale.
String toUpperCase(): Equivalent to toUpperCase(Locale.getDefault()).
public String intern(): This method searches the specified string in the memory pool and if it is found then it returns the reference of it, else it allocates the memory space to the specified string and assign the reference to it.
public boolean isEmpty(): This method returns true if the given string has 0 length. If the length of the specified Java String is non-zero then it returns false.
public static String join(): This method joins the given strings using the specified delimiter and returns the concatenated Java String
String replaceFirst(String regex, String replacement): It replaces the first occurrence of substring that fits the given regular expression “regex” with the specified replacement string.
String replaceAll(String regex, String replacement): It replaces all the occurrences of substrings that fits the regular expression regex with the replacement string.
String[] split(String regex, int limit): It splits the string and returns the array of substrings that matches the given regular expression. limit is a result threshold here.
String[] split(String regex): Same as split(String regex, int limit) method however it does not have any threshold limit.
String toLowerCase(Locale locale): It converts the string to lower case string using the rules defined by given locale.
public static String format(): This method returns a formatted java String
String toLowerCase(): Equivalent to toLowerCase(Locale. getDefault()).
String trim(): Returns the substring after omitting leading and trailing white spaces from the original string.
char[] toCharArray(): Converts the string to a character array.
static String copyValueOf(char[] data): It returns a string that contains the characters of the specified character array.
static String copyValueOf(char[] data, int offset, int count): Same as above method with two extra arguments – initial offset of subarray and length of subarray.
void getChars(int srcBegin, int srcEnd, char[] dest, int destBegin): It copies the characters of src array to the dest array. Only the specified range is being copied(srcBegin to srcEnd) to the dest subarray(starting fromdestBegin).
static String valueOf(): This method returns a string representation of passed arguments such as int, long, float, double, char and char array.
boolean contentEquals(StringBuffer sb): It compares the string to the specified string buffer.
boolean regionMatches(int srcoffset, String dest, int destoffset, int len): It compares the substring of input to the substring of specified string.
boolean regionMatches(boolean ignoreCase, int srcoffset, String dest, int destoffset, int len): Another variation of regionMatches method with the extra boolean argument to specify whether the comparison is case sensitive or case insensitive.
byte[] getBytes(String charsetName): It converts the String into sequence of bytes using the specified charset encoding and returns the array of resulted bytes.
byte[] getBytes(): This method is similar to the above method it just uses the default charset encoding for converting the string into sequence of bytes.
int length(): It returns the length of a String.
boolean matches(String regex): It checks whether the String is matching with the specified regular expression regex.
int codePointAt(int index):It is similar to the charAt method however it returns the Unicode code point value of specified index rather than the character itself.*

## Two Pointer Technique

## Linked Lists
*LinkedList in Java
Linked List is a part of the Collection framework present in java.util package. This class is an implementation of the LinkedList data structure which is a linear data structure where the elements are not stored in contiguous locations and every element is a separate object with a data part and address part. The elements are linked using pointers and addresses. Each element is known as a node. Due to the dynamicity and ease of insertions and deletions, they are preferred over the arrays. It also has few disadvantages like the nodes cannot be accessed directly instead we need to start from the head and follow through the link to reach to a node we wish to access.

Example: The following implementation demonstrates how to create and use a linked list.

filter_none
edit
play_arrow

brightness_4
import java.util.*; 
  
public class Test { 
  
    public static void main(String args[]) 
    { 
        // Creating object of the 
        // class linked list 
        LinkedList<String> ll 
            = new LinkedList<String>(); 
  
        // Adding elements to the linked list 
        ll.add("A"); 
        ll.add("B"); 
        ll.addLast("C"); 
        ll.addFirst("D"); 
        ll.add(2, "E"); 
  
        System.out.println(ll); 
  
        ll.remove("B"); 
        ll.remove(3); 
        ll.removeFirst(); 
        ll.removeLast(); 
  
        System.out.println(ll); 
    } 
} 
Output:
[D, A, E, B, C]
[A]
Performing Various Operations on ArrayList
Let’s see how to perform some basics operations on the LinkedList.

1. Adding Elements: In order to add an element to an ArrayList, we can use the add() method. This method is overloaded to perform multiple operations based on different parameters. They are:



add(Object): This method is used to add an element at the end of the LinkedList.
add(int index, Object): This method is used to add an element at a specific index in the LinkedList.
filter_none
edit
play_arrow

brightness_4
// Java program to add elements  
// to a LinkedList 
    
import java.util.*;  
    
public class GFG {  
    
    public static void main(String args[])  
    {  
        LinkedList<String> ll = new LinkedList<>();  
    
        ll.add("Geeks");  
        ll.add("Geeks");  
        ll.add(1, "For");  
    
        System.out.println(ll);  
    }  
}  
Output:
[Geeks, For, Geeks]
2. Changing Elements: After adding the elements, if we wish to change the element, it can be done using the set() method. Since a LinkedList is indexed, the element which we wish to change is referenced by the index of the element. Therefore, this method takes an index and the updated element which needs to be inserted at that index.

filter_none
edit
play_arrow

brightness_4
// Java program to change elements  
// in a LinkedList  
    
import java.util.*;  
    
public class GFG {  
    
    public static void main(String args[])  
    {  
        LinkedList<String> ll = new LinkedList<>();  
    
        ll.add("Geeks");  
        ll.add("Geeks");  
        ll.add(1, "Geeks");  
    
        System.out.println("Initial LinkedList " + ll);  
    
        ll.set(1, "For");  
    
        System.out.println("Updated LinkedList " + ll);  
    }  
}  
Output:
Initial LinkedList [Geeks, Geeks, Geeks]
Updated LinkedList [Geeks, For, Geeks]
3. Removing Elements: In order to remove an element from a LinkedList, we can use the remove() method. This method is overloaded to perform multiple operations based on different parameters. They are:

remove(Object): This method is used to simply remove an object from the LinkedList. If there are multiple such objects, then the first occurrence of the object is removed.
remove(int index): Since a LinkedList is indexed, this method takes an integer value which simply removes the element present at that specific index in the LinkedList. After removing the element, all the elements are moved to the left to fill the space and the indices of the objects are updated.
filter_none
edit
play_arrow

brightness_4
// Java program to remove elements  
// in a LinkedList 
    
import java.util.*;  
    
public class GFG {  
    
    public static void main(String args[])  
    {  
        LinkedList<String> ll = new LinkedList<>();  
    
        ll.add("Geeks");  
        ll.add("Geeks");  
        ll.add(1, "For");  
    
        System.out.println(  
            "Initial LinkedList " + ll);  
    
        ll.remove(1);  
    
        System.out.println(  
            "After the Index Removal " + ll);  
    
        ll.remove("Geeks");  
    
        System.out.println(  
            "After the Object Removal " + ll);  
    }  
}  
Output:
Initial LinkedList [Geeks, For, Geeks]
After the Index Removal [Geeks, Geeks]
After the Object Removal [Geeks]
4. Iterating the LinkedList: There are multiple ways to iterate through the LinkedList. The most famous ways are by using the basic for loop in combination with a get() method to get the element at a specific index and the advanced for loop.

filter_none
edit
play_arrow

brightness_4
// Java program to iterate the elements  
// in an LinkedList 
    
import java.util.*;  
    
public class GFG {  
    
    public static void main(String args[])  
    {  
        LinkedList<String> ll  
            = new LinkedList<>();  
    
        ll.add("Geeks");  
        ll.add("Geeks");  
        ll.add(1, "For");  
    
        // Using the Get method and the  
        // for loop  
        for (int i = 0; i < ll.size(); i++) {  
    
            System.out.print(ll.get(i) + " ");  
        }  
    
        System.out.println();  
    
        // Using the for each loop  
        for (String str : ll)  
            System.out.print(str + " ");  
    }  
}  
Output:
Geeks For Geeks 
Geeks For Geeks 
List-ArrayList-in-Java-In-Depth-Study

In the above illustration, AbstractList, CopyOnWriteArrayList and the AbstractSequentialList are the classes which implement the list interface. A separate functionality is implemented in each of the mentioned classes. They are:

AbstractList: This class is used to implement an unmodifiable list, for which one needs to only extend this AbstractList Class and implement only the get() and the size() methods.
CopyOnWriteArrayList: This class implements the list interface. It is an enhanced version of ArrayList in which all the modifications(add, set, remove, etc.) are implemented by making a fresh copy of the list.
AbstractSequentialList: This class implements the Collection interface and the AbstractCollection class. This class is used to implement an unmodifiable list, for which one needs to only extend this AbstractList Class and implement only the get() and the size() methods.
How LinkedList work Internally?
Since a LinkedList acts as a dynamic array and we do not have to specify the size while creating it, the size of the list automatically increases when we dynamically add and remove items. And also, the elements are not stored in a continuous fashion. Therefore, there is no need to increase the size. Internally, the LinkedList is implemented using the doubly linked list data structure. The main difference between a normal linked list and a doubly LinkedList is that a doubly linked list contains an extra pointer, typically called the previous pointer, together with the next pointer and data which are there in the singly linked list.

Constructors in the LinkedList
In order to create a LinkedList, we need to create an object of the LinkedList class. The LinkedList class consists of various constructors that allow the possible creation of the list. The following are the constructors available in this class:

LinkedList(): This constructor is used to create an empty linked list. If we wish to create an empty LinkedList with the name ll, then, it can be created as:
LinkedList ll = new LinkedList();

LinkedList(Collection C): This constructor is used to create an ordered list which contains all the elements of a specified collection, as returned by the collection’s iterator. If we wish to create a linkedlist with the name ll, then, it can be created as:
LinkedList ll = new LinkedList(C);

Methods for Java LinkedList
METHOD	DESCRIPTION
add(int index, E element)	This method Inserts the specified element at the specified position in this list.
add(E e)	This method Appends the specified element to the end of this list.
addAll(int index, Collection<E> c)	This method Inserts all of the elements in the specified collection into this list, starting at the specified position.
addAll(Collection<E> c)	This method Appends all of the elements in the specified collection to the end of this list, in the order that they are returned by the specified collection’s iterator.
addFirst(E e)	This method Inserts the specified element at the beginning of this list.
addLast(E e)	This method Appends the specified element to the end of this list.
clear()	This method removes all of the elements from this list.
clone()	This method returns a shallow copy of this LinkedList.
contains(Object o)	This method returns true if this list contains the specified element.
descendingIterator()	This method returns an iterator over the elements in this deque in reverse sequential order.
element()	This method retrieves, but does not remove, the head (first element) of this list.
get(int index)	This method returns the element at the specified position in this list.
getFirst()	This method returns the first element in this list.
getLast()	This method returns the last element in this list.
indexOf(Object o)	This method returns the index of the first occurrence of the specified element in this list, or -1 if this list does not contain the element.
lastIndexOf(Object o)	This method returns the index of the last occurrence of the specified element in this list, or -1 if this list does not contain the element.
listIterator(int index)	This method returns a list-iterator of the elements in this list (in proper sequence), starting at the specified position in the list.
offer(E e)	This method Adds the specified element as the tail (last element) of this list.
offerFirst(E e)	This method Inserts the specified element at the front of this list.
offerLast(E e)	This method Inserts the specified element at the end of this list.
peek()	This method retrieves, but does not remove, the head (first element) of this list.
peekFirst()	This method retrieves, but does not remove, the first element of this list, or returns null if this list is empty.
peekLast()	This method retrieves, but does not remove, the last element of this list, or returns null if this list is empty.
poll()	This method retrieves and removes the head (first element) of this list.
pollFirst()	This method retrieves and removes the first element of this list, or returns null if this list is empty.
pollLast()	This method retrieves and removes the last element of this list, or returns null if this list is empty.
pop()	This method Pops an element from the stack represented by this list.
push(E e)	This method Pushes an element onto the stack represented by this list.
remove()	This method retrieves and removes the head (first element) of this list.
remove(int index)	This method removes the element at the specified position in this list.
remove(Object o)	This method removes the first occurrence of the specified element from this list, if it is present.
removeFirst()	This method removes and returns the first element from this list.
removeFirstOccurrence(Object o)	This method removes the first occurrence of the specified element in this list (when traversing the list from head to tail).
removeLast()	This method removes and returns the last element from this list.
removeLastOccurrence(Object o)	This method removes the last occurrence of the specified element in this list (when traversing the list from head to tail).
set(int index, E element)	This method replaces the element at the specified position in this list with the specified element.
size()	This method returns the number of elements in this list.
spliterator()	This method Creates a late-binding and fail-fast Spliterator over the elements in this list.
toArray()	This method returns an array containing all of the elements in this list in proper sequence (from first to last element).
toArray(T[] a)	This method returns an array containing all of the elements in this list in proper sequence (from first to last element); the runtime type of the returned array is that of the specified array.
toString()	This method returns a String containing all of the elements in this list in proper sequence (from first to last element), each element is separated by commas and the String is enclosed in square brackets.*
## Stacks and Queues

## Binary Trees

## Binary Search Trees
*Binary Search Tree (BST) Complete Implementation.
Binary Tree : A data structure in which we have nodes containing data and two references to other nodes, one on the left and one on the right.

Binary Tree consist of Nodes

Nodes are nothing but objects of a class and each node has data and a link to the left node and right node.
Usually we call the starting node of a tree as root.
class Node{
	int data;
	Node left;
	Node right;	
	public Node(int data){
		this.data = data;
		left = null;
		right = null;
	}
}

 Left and right node of a Leaf node points to NULL so you will know that you have reached to the end of the tree.


Binary Search Tree:

Often we call it as BST, is a type of Binary tree which has a special property.

Nodes smaller than root goes to the left of the root and Nodes greater than root goes to the right of the root.



Operations:

Insert(int n) : Add a node the tree with value n. Its O(lgn)

Find(int n) : Find a node the tree with value n. Its O(lgn)

Delete (int n) : Delete a node the tree with value n. Its O(lgn)

Display(): Prints the entire tree in increasing order. O(n).

Detail Explanations for the Operations:

Find(int n):

Its very simple operation to perform.
start from the root and compare root.data with n
if root.data is greater than n that means we need to go to the left of the root.
if root.data is smaller than n that means we need to go to the right of the root.
if any point of time root.data is equal to the n then we have found the node, return true.
if we reach to the leaves (end of the tree) return false, we didn’t find the element
Insert(int n):

Very much similar to find() operation.
To insert a node our first task is to find the place to insert the node.
Take current = root .
start from the current and compare root.data with n
if current.data is greater than n that means we need to go to the left of the root.
if current.data is smaller than n that means we need to go to the right of the root.
if any point of time current is null that means we have reached to the leaf node, insert your node here with the help of parent node. (See code)


Delete(int n):

Complicated than Find() and Insert() operations. Here we have to deal with 3 cases.

Node to be deleted is a leaf node ( No Children).
Node to be deleted has only one child.
Node to be deleted has two childrens.
Node to be deleted is a leaf node ( No Children).

its a very simple case, if a node to be deleted has no children then just traverse to that node, keep track of parent node and the side in which the node exist(left or right) and set parent.left = null or parent.right = null;

 



Node to be deleted has only one child.

its a slightly complex case. if a node to be deleted(deleteNode) has only one child then just traverse to that node, keep track of parent node and the side in which the node exist(left or right).
check which side child is null (since it has only one child).
Say node to be deleted has child on its left side . Then take the entire sub tree from the left side and add it to the parent and the side on which deleteNode exist, see step 1 and example.


Node to be deleted has two children.

Now this is quite exciting 🙂

You just cannot replace the deleteNode with any of its child, Why? Lets try out a example.



What to do now?????

Dont worry we have solution for this 🙂

Find The Successor:

Successor is the node which will replace the deleted node. Now the question is to how to find it and where to find it.

Successor is the smaller node in the right sub tree of the node to be deleted.



Display() : To know about how we are displaying nodes in increasing order, Click Here

Complete Example :

 



Complete Example Code:Run This Code

public class BinarySearchTree {
	public static  Node root;
	public BinarySearchTree(){
		this.root = null;
	}
	
	public boolean find(int id){
		Node current = root;
		while(current!=null){
			if(current.data==id){
				return true;
			}else if(current.data>id){
				current = current.left;
			}else{
				current = current.right;
			}
		}
		return false;
	}
	public boolean delete(int id){
		Node parent = root;
		Node current = root;
		boolean isLeftChild = false;
		while(current.data!=id){
			parent = current;
			if(current.data>id){
				isLeftChild = true;
				current = current.left;
			}else{
				isLeftChild = false;
				current = current.right;
			}
			if(current ==null){
				return false;
			}
		}
		//if i am here that means we have found the node
		//Case 1: if node to be deleted has no children
		if(current.left==null && current.right==null){
			if(current==root){
				root = null;
			}
			if(isLeftChild ==true){
				parent.left = null;
			}else{
				parent.right = null;
			}
		}
		//Case 2 : if node to be deleted has only one child
		else if(current.right==null){
			if(current==root){
				root = current.left;
			}else if(isLeftChild){
				parent.left = current.left;
			}else{
				parent.right = current.left;
			}
		}
		else if(current.left==null){
			if(current==root){
				root = current.right;
			}else if(isLeftChild){
				parent.left = current.right;
			}else{
				parent.right = current.right;
			}
		}else if(current.left!=null && current.right!=null){
			
			//now we have found the minimum element in the right sub tree
			Node successor	 = getSuccessor(current);
			if(current==root){
				root = successor;
			}else if(isLeftChild){
				parent.left = successor;
			}else{
				parent.right = successor;
			}			
			successor.left = current.left;
		}		
		return true;		
	}
	
	public Node getSuccessor(Node deleleNode){
		Node successsor =null;
		Node successsorParent =null;
		Node current = deleleNode.right;
		while(current!=null){
			successsorParent = successsor;
			successsor = current;
			current = current.left;
		}
		//check if successor has the right child, it cannot have left child for sure
		// if it does have the right child, add it to the left of successorParent.
//		successsorParent
		if(successsor!=deleleNode.right){
			successsorParent.left = successsor.right;
			successsor.right = deleleNode.right;
		}
		return successsor;
	}
	public void insert(int id){
		Node newNode = new Node(id);
		if(root==null){
			root = newNode;
			return;
		}
		Node current = root;
		Node parent = null;
		while(true){
			parent = current;
			if(id<current.data){				
				current = current.left;
				if(current==null){
					parent.left = newNode;
					return;
				}
			}else{
				current = current.right;
				if(current==null){
					parent.right = newNode;
					return;
				}
			}
		}
	}
	public void display(Node root){
		if(root!=null){
			display(root.left);
			System.out.print(" " + root.data);
			display(root.right);
		}
	}
	public static void main(String arg[]){
		BinarySearchTree b = new BinarySearchTree();
		b.insert(3);b.insert(8);
		b.insert(1);b.insert(4);b.insert(6);b.insert(2);b.insert(10);b.insert(9);
		b.insert(20);b.insert(25);b.insert(15);b.insert(16);
		System.out.println("Original Tree : ");
		b.display(b.root);		
		System.out.println("");
		System.out.println("Check whether Node with value 4 exists : " + b.find(4));
		System.out.println("Delete Node with no children (2) : " + b.delete(2));		
		b.display(root);
		System.out.println("\n Delete Node with one child (4) : " + b.delete(4));		
		b.display(root);
		System.out.println("\n Delete Node with Two children (10) : " + b.delete(10));		
		b.display(root);
	}
}

class Node{
	int data;
	Node left;
	Node right;	
	public Node(int data){
		this.data = data;
		left = null;
		right = null;
	}
}
view rawBinarySearchTree.java hosted with ❤ by GitHub
Output:
Original Tree :
1 2 3 4 6 8 9 10 15 16 20 25
Check whether Node with value 4 exists : true
Delete Node with no children (2) : true
1 3 4 6 8 9 10 15 16 20 25
Delete Node with one child (4) : true
1 3 6 8 9 10 15 16 20 25
Delete Node with Two children (10) : true
1 3 6 8 9 15 16 20 25*

## Recursion
*A physical world example would be to place two parallel mirrors facing each other. Any object in between them would be reflected recursively.

How Recursion works?
A function is calling itself
Working of Java Recursion
In the above example, we have called the recurse() method from inside the main method. (normal method call). And, inside the recurse() method, we are again calling the same recurse method. This is a recursive call.

In order to stop the recursive call, we need to provide some conditions inside the method. Otherwise, the method will be called infinitely.

Hence, we use the if...else statement (or similar approach) to terminate the recursive call inside the method.

Example: Factorial of a Number Using Recursion
class Factorial {

    static int factorial( int n ) {
        if (n != 0)  // termination condition
            return n * factorial(n-1); // recursive call
        else
            return 1;
    }

    public static void main(String[] args) {
        int number = 4, result;
        result = factorial(number);
        System.out.println(number + " factorial = " + result);
    }
}
Output:

4 factorial = 24
In the above example, we have a method named factorial(). The factorial() is called from the main() method. with the number variable passed as an argument.

Here, notice the statement,

return n * factorial(n-1);
The factorial() method is calling itself. Initially, the value of n is 4 inside factorial(). During the next recursive call, 3 is passed to the factorial() method. This process continues until n is equal to 0.

When n is equal to 0, the if statement returns false hence 1 is returned. Finally, the accumulated result is passed to the main() method.

Working of Factorial Program
The image below will give you a better idea of how the factorial program is executed using recursion.

Finding the factorial of a number using recursion
Factorial Program using Recursion
Advantages and Disadvantages of Recursion
When a recursive call is made, new storage locations for variables are allocated on the stack. As, each recursive call returns, the old variables and parameters are removed from the stack. Hence, recursion generally uses more memory and is generally slow.

On the other hand, a recursive solution is much simpler and takes less time to write, debug and maintain.*

## Backtracking
*
Backtracking Algorithms
Backtracking is an algorithmic-technique for solving problems recursively by trying to build a solution incrementally, one piece at a time, removing those solutions that fail to satisfy the constraints of the problem at any point of time (by time, here, is referred to the time elapsed till reaching any level of the search tree).

For example, consider the SudoKo solving Problem, we try filling digits one by one. Whenever we find that current digit cannot lead to a solution, we remove it (backtrack) and try next digit. This is better than naive approach (generating all possible combinations of digits and then trying every combination one by one) as it drops a set of permutations whenever it backtracks.
The Knight’s tour problem | Backtracking-1
Backtracking is an algorithmic paradigm that tries different solutions until finds a solution that “works”. Problems which are typically solved using backtracking technique have following property in common. These problems can only be solved by trying every possible configuration and each configuration is tried only once. A Naive solution for these problems is to try all configurations and output a configuration that follows given problem constraints. Backtracking works in incremental way and is an optimization over the Naive solution where all possible configurations are generated and tried.

For example, consider the following Knight’s Tour problem.
The knight is placed on the first block of an empty board and, moving according to the rules of chess, must visit each square exactly once.

Path followed by Knight to cover all the cells

Following is chessboard with 8 x 8 cells. Numbers in cells indicate move number of Knight.
knight-tour-problem
Let us first discuss the Naive algorithm for this problem and then the Backtracking algorithm.

Naive Algorithm for Knight’s tour
The Naive Algorithm is to generate all tours one by one and check if the generated tour satisfies the constraints.



while there are untried tours
{ 
   generate the next tour 
   if this tour covers all squares 
   { 
      print this path;
   }
}
Backtracking works in an incremental way to attack problems. Typically, we start from an empty solution vector and one by one add items (Meaning of item varies from problem to problem. In context of Knight’s tour problem, an item is a Knight’s move). When we add an item, we check if adding the current item violates the problem constraint, if it does then we remove the item and try other alternatives. If none of the alternatives work out then we go to previous stage and remove the item added in the previous stage. If we reach the initial stage back then we say that no solution exists. If adding an item doesn’t violate constraints then we recursively add items one by one. If the solution vector becomes complete then we print the solution.

Backtracking Algorithm for Knight’s tour
Following is the Backtracking algorithm for Knight’s tour problem.

If all squares are visited 
    print the solution
Else
   a) Add one of the next moves to solution vector and recursively 
   check if this move leads to a solution. (A Knight can make maximum 
   eight moves. We choose one of the 8 moves in this step).
   b) If the move chosen in the above step doesn't lead to a solution
   then remove this move from the solution vector and try other 
   alternative moves.
   c) If none of the alternatives work then return false (Returning false 
   will remove the previously added item in recursion and if false is 
   returned by the initial call of recursion then "no solution exists" )
Following are implementations for Knight’s tour problem. It prints one of the possible solutions in 2D matrix form. Basically, the output is a 2D 8*8 matrix with numbers from 0 to 63 and these numbers show steps made by Knight.
filter_none
edit
play_arrow

brightness_4
// Java program for Knight Tour problem 
class KnightTour { 
    static int N = 8; 
  
    /* A utility function to check if i,j are 
       valid indexes for N*N chessboard */
    static boolean isSafe(int x, int y, int sol[][]) { 
        return (x >= 0 && x < N && y >= 0 && 
                y < N && sol[x][y] == -1); 
    } 
  
    /* A utility function to print solution 
       matrix sol[N][N] */
    static void printSolution(int sol[][]) { 
        for (int x = 0; x < N; x++) { 
            for (int y = 0; y < N; y++) 
                System.out.print(sol[x][y] + " "); 
            System.out.println(); 
        } 
    } 
  
    /* This function solves the Knight Tour problem 
       using Backtracking.  This  function mainly 
       uses solveKTUtil() to solve the problem. It 
       returns false if no complete tour is possible, 
       otherwise return true and prints the tour. 
       Please note that there may be more than one 
       solutions, this function prints one of the 
       feasible solutions.  */
    static boolean solveKT() { 
        int sol[][] = new int[8][8]; 
  
        /* Initialization of solution matrix */
        for (int x = 0; x < N; x++) 
            for (int y = 0; y < N; y++) 
                sol[x][y] = -1; 
  
       /* xMove[] and yMove[] define next move of Knight. 
          xMove[] is for next value of x coordinate 
          yMove[] is for next value of y coordinate */
        int xMove[] = {2, 1, -1, -2, -2, -1, 1, 2}; 
        int yMove[] = {1, 2, 2, 1, -1, -2, -2, -1}; 
  
        // Since the Knight is initially at the first block 
        sol[0][0] = 0; 
  
        /* Start from 0,0 and explore all tours using 
           solveKTUtil() */
        if (!solveKTUtil(0, 0, 1, sol, xMove, yMove)) { 
            System.out.println("Solution does not exist"); 
            return false; 
        } else
            printSolution(sol); 
  
        return true; 
    } 
  
    /* A recursive utility function to solve Knight 
       Tour problem */
    static boolean solveKTUtil(int x, int y, int movei, 
                               int sol[][], int xMove[], 
                               int yMove[]) { 
        int k, next_x, next_y; 
        if (movei == N * N) 
            return true; 
  
        /* Try all next moves from the current coordinate 
            x, y */
        for (k = 0; k < 8; k++) { 
            next_x = x + xMove[k]; 
            next_y = y + yMove[k]; 
            if (isSafe(next_x, next_y, sol)) { 
                sol[next_x][next_y] = movei; 
                if (solveKTUtil(next_x, next_y, movei + 1, 
                                sol, xMove, yMove)) 
                    return true; 
                else
                    sol[next_x][next_y] = -1;// backtracking 
            } 
        } 
  
        return false; 
    } 
  
    /* Driver program to test above functions */
    public static void main(String args[]) { 
        solveKT(); 
    } 
} 
// This code is contributed by Abhishek Shankhadhar 

Output:
  0  59  38  33  30  17   8  63
 37  34  31  60   9  62  29  16
 58   1  36  39  32  27  18   7
 35  48  41  26  61  10  15  28
 42  57   2  49  40  23   6  19
 47  50  45  54  25  20  11  14
 56  43  52   3  22  13  24   5
 51  46  55  44  53   4  21  12
*

## Dynamic Programming
*
What is Dynamic Programming?
Dynamic programming is a programming principle where a very complex problem can be solved by dividing it into smaller subproblems. This principle is very similar to recursion, but with a key difference, every distinct subproblem has to be solved only once.

To understand what this means, we first have to understand the problem of solving recurrence relations. Every single complex problem can be divided into very similar subproblems, this means we can construct a recurrence relation between them.

Let's take a look at an example we all are familiar with, the Fibonacci sequence! The Fibonacci sequence is defined with the following recurrence relation:

f
i
b
o
n
a
c
c
i
(
n
)
=
f
i
b
o
n
a
c
c
i
(
n
−
1
)
+
f
i
b
o
n
a
c
c
i
(
n
−
2
)
Note: A recurrence relation is an equation that recursively defines a sequence where the next term is a function of the previous terms. The Fibonacci sequence is a great example of this.

So, if we want to find the n-th number in the Fibonacci sequence, we have to know the two numbers preceding the n-th in the sequence.

However, every single time we want to calculate a different element of the Fibonacci sequence, we have have certain duplicate calls in our recursive calls, as can be seen in following image, where we calculate Fibonacci(5):

fibonacci_sequence

For example, if we want to calculate F(5), we obviously need to calculate F(4) and F(3) as a prerequisite. However, to calculate F(4), we need to calculate F(3) and F(2), which in turn requires us to calculate F(2) and F(1) in order to get F(3) – and so on.

This leads to many repeated calculations, which are essentially redundant and slow down the algorithm significantly. To solve this issue, we're introducing ourselves to Dynamic Programming.

In this approach, we model a solution as if we were to solve it recursively, but we solve it from the ground up, memoizing the solutions to the subproblems (steps) we take to reach the top.

Therefore, for the Fibonacci sequence, we first solve and memoize F(1) and F(2), then calculate F(3) using the two memoized steps, and so on. This means that the calculation of every individual element of the sequence is O(1), because we already know the former two.

When solving a problem using dynamic programming, we have to follow three steps:

Determine the recurrence relation that applies to said problem
Initialize the memory/array/matrix's starting values
Make sure that when we make a "recursive call" (access the memoized solution of a subproblem) it's always solved in advance
Following these rules, let's take a look at some examples of algorithms that use dynamic programming.

Rod Cutting Algorithm
Let's start with something simple:

Given a rod of length n and an array that contains prices of all pieces of size smaller than n. Determine the maximum value obtainable by cutting up the rod and selling the pieces.

Naive Solution
This problem is practically tailor-made for dynamic programming, but because this is our first real example, let's see how many fires we can start by letting this code run:

public class naiveSolution {
    static int getValue(int[] values, int length) {
        if (length <= 0)
            return 0;
        int tmpMax = -1;
        for (int i = 0; i < length; i++) {
            tmpMax = Math.max(tmpMax, values[i] + getValue(values, length - i - 1));
        }
        return tmpMax;
    }

    public static void main(String[] args) {
        int[] values = new int[]{3, 7, 1, 3, 9};
        int rodLength = values.length;

        System.out.println("Max rod value: " + getValue(values, rodLength));
    }
}
Output:

Max rod value: 17
This solution, while correct, is highly inefficient. Recursive calls aren't memoized so the poor code has to solve the same subproblem every time there's a single overlapping solution.

Dynamic Approach
Utilizing the same basic principle from above, but adding memoization and excluding recursive calls, we get the following implementation:

public class dpSolution {
    static int getValue(int[] values, int rodLength) {
        int[] subSolutions = new int[rodLength + 1];

        for (int i = 1; i <= rodLength; i++) {
            int tmpMax = -1;
            for (int j = 0; j < i; j++)
                tmpMax = Math.max(tmpMax, values[j] + subSolutions[i - j - 1]);
            subSolutions[i] = tmpMax;
        }
        return subSolutions[rodLength];
    }

    public static void main(String[] args) {
        int[] values = new int[]{3, 7, 1, 3, 9};
        int rodLength = values.length;

        System.out.println("Max rod value: " + getValue(values, rodLength));
    }
}
Output:

Max rod value: 17
As we can see, the resulting outputs are the same, only with different time/space complexity.

We eliminate the need for recursive calls by solving the subproblems from the ground-up, utilizing the fact that all previous subproblems to a given problem are already solved.

Performance Boost
Just to give a perspective of how much more efficient the Dynamic approach is, let's try running the algorithm with 30 values.

The Naive solution took ~5.2s to execute whereas the Dynamic solution took ~0.000095s to execute.

Simplified Knapsack Problem
The Simplified Knapsack problem is a problem of optimization, for which there is no one solution. The question for this problem would be - "Does a solution even exist?":

Given a set of items, each with a weight w1, w2... determine the number of each item to put in a knapsack so that the total weight is less than or equal to a given limit K.

So let's take a step back and figure out how will we represent the solutions to this problem. First, let's store the weights of all the items in an array W.

Next, let's say that there are n items and we'll enumerate them with numbers from 1 to n, so the weight of the i-th item is W[i].

We'll form a matrix M of (n+1)x(K+1) dimensions. M[x][y] corresponding to the solution of the knapsack problem, but only including the first x items of the beginning array, and with a maximum capacity of y.

Example
Let's say we have 3 items, with the weights being w1=2kg, w2=3kg, and w3=4kg.

Utilizing the method above, we can say that M[1][2] is a valid solution. This means that we are trying to fill a knapsack with a capacity of 2kg with just the first item from the weight array (w1).

While in M[3][5] we are trying to fill up a knapsack with a capacity of 5kg using the first 3 items of the weight array (w1,w2,w3). This isn't a valid solution, since we're overfitting it.

Matrix Initialization
There are 2 things to note when filling up the matrix:

Does a solution exist for the given subproblem (M[x][y].exists) AND does the given solution include the latest item added to the array (M[x][y].includes).

Therefore, initialization of the matrix is quite easy, M[0][k].exists is always false, if k > 0, because we didn't put any items in a knapsack with k capacity.

On the other hand, M[0][0].exists = true, because the knapsack should be empty to begin with since k = 0, and therefore we can't put anything in and this is a valid solution.

Furthermore, we can say that M[k][0].exists = true but also M[k][0].includes = false for every k.

Note: Just because a solution exists for a given M[x][y], it doesn't necessarily mean that that particular combination is the solution. In the case of M[10][0], a solution exists - not including any of the 10 elements. This is why M[10][0].exists = true but M[10][0].includes = false.

Algorithm Principle
Next, let's construct the recurrence relation for M[i][k] with the following pseudo-code:

if (M[i-1][k].exists == True):
    M[i][k].exists = True
    M[i][k].includes = False
elif (k-W[i]>=0):
    if(M[i-1][k-W[i]].exists == true):
        M[i][k].exists = True
        M[i][k].includes = True
else:
    M[i][k].exists = False
*
## Greedy Algorithms
*Greedy Algorithms
Greedy is an algorithmic paradigm that builds up a solution piece by piece, always choosing the next piece that offers the most obvious and immediate benefit. So the problems where choosing locally optimal also leads to global solution are best fit for Greedy.

For example consider the Fractional Knapsack Problem. The local optimal strategy is to choose the item that has maximum value vs weight ratio. This strategy also leads to global optimal solution because we allowed to take fractions of an item.
Activity Selection Problem | Greedy Algo-1
28-03-2012
Greedy is an algorithmic paradigm that builds up a solution piece by piece, always choosing the next piece that offers the most obvious and immediate benefit. Greedy algorithms are used for optimization problems. An optimization problem can be solved using Greedy if the problem has the following property: At every step, we can make a choice that looks best at the moment, and we get the optimal solution of the complete problem.
If a Greedy Algorithm can solve a problem, then it generally becomes the best method to solve that problem as the Greedy algorithms are in general more efficient than other techniques like Dynamic Programming. But Greedy algorithms cannot always be applied. For example, Fractional Knapsack problem (See this) can be solved using Greedy, but 0-1 Knapsack cannot be solved using Greedy.

Following are some standard algorithms that are Greedy algorithms.
1) Kruskal’s Minimum Spanning Tree (MST): In Kruskal’s algorithm, we create a MST by picking edges one by one. The Greedy Choice is to pick the smallest weight edge that doesn’t cause a cycle in the MST constructed so far.
2) Prim’s Minimum Spanning Tree: In Prim’s algorithm also, we create a MST by picking edges one by one. We maintain two sets: a set of the vertices already included in MST and the set of the vertices not yet included. The Greedy Choice is to pick the smallest weight edge that connects the two sets.
3) Dijkstra’s Shortest Path: The Dijkstra’s algorithm is very similar to Prim’s algorithm. The shortest path tree is built up, edge by edge. We maintain two sets: a set of the vertices already included in the tree and the set of the vertices not yet included. The Greedy Choice is to pick the edge that connects the two sets and is on the smallest weight path from source to the set that contains not yet included vertices.
4) Huffman Coding: Huffman Coding is a loss-less compression technique. It assigns variable-length bit codes to different characters. The Greedy Choice is to assign least bit length code to the most frequent character.

The greedy algorithms are sometimes also used to get an approximation for Hard optimization problems. For example, Traveling Salesman Problem is a NP-Hard problem. A Greedy choice for this problem is to pick the nearest unvisited city from the current city at every step. This solutions don’t always produce the best optimal solution but can be used to get an approximately optimal solution.

Let us consider the Activity Selection problem as our first example of Greedy algorithms. Following is the problem statement.
You are given n activities with their start and finish times. Select the maximum number of activities that can be performed by a single person, assuming that a person can only work on a single activity at a time.
Example:

Example 1 : Consider the following 3 activities sorted by
by finish time.
     start[]  =  {10, 12, 20};
     finish[] =  {20, 25, 30};
A person can perform at most two activities. The 
maximum set of activities that can be executed 
is {0, 2} [ These are indexes in start[] and 
finish[] ]

Example 2 : Consider the following 6 activities 
sorted by by finish time.
     start[]  =  {1, 3, 0, 5, 8, 5};
     finish[] =  {2, 4, 6, 7, 9, 9};
A person can perform at most four activities. The 
maximum set of activities that can be executed 
is {0, 1, 3, 4} [ These are indexes in start[] and 
finish[] ]


The greedy choice is to always pick the next activity whose finish time is least among the remaining activities and the start time is more than or equal to the finish time of previously selected activity. We can sort the activities according to their finishing time so that we always consider the next activity as minimum finishing time activity.



1) Sort the activities according to their finishing time
2) Select the first activity from the sorted array and print it.
3) Do following for remaining activities in the sorted array.
…….a) If the start time of this activity is greater than or equal to the finish time of previously selected activity then select this activity and print it.

// The following implementation assumes that the activities 
// are already sorted according to their finish time 
import java.util.*; 
import java.lang.*; 
import java.io.*; 
  
class ActivitySelection 
{ 
    // Prints a maximum set of activities that can be done by a single 
    // person, one at a time. 
    //  n   -->  Total number of activities 
    //  s[] -->  An array that contains start time of all activities 
    //  f[] -->  An array that contains finish time of all activities 
    public static void printMaxActivities(int s[], int f[], int n) 
    { 
    int i, j; 
       
    System.out.print("Following activities are selected : n"); 
       
    // The first activity always gets selected 
    i = 0; 
    System.out.print(i+" "); 
       
    // Consider rest of the activities 
    for (j = 1; j < n; j++) 
    { 
         // If this activity has start time greater than or 
         // equal to the finish time of previously selected 
         // activity, then select it 
         if (s[j] >= f[i]) 
         { 
              System.out.print(j+" "); 
              i = j; 
          } 
     } 
    } 
       
    // driver program to test above function 
    public static void main(String[] args) 
    { 
    int s[] =  {1, 3, 0, 5, 8, 5}; 
    int f[] =  {2, 4, 6, 7, 9, 9}; 
    int n = s.length; 
         
    printMaxActivities(s, f, n); 
    } 
      
} *
## Unit testing
*
Step 1: Get the required unit testing artefacts
Add in the JUnit dependency into maven `pom.xml` file.
I use Maven as my build tool/project management system for my projects most of the time. If you use other build tools such as Ant, Gradle, Ivy etc. then it would be similar.

JUnit 5 is the latest version but i normally use JUnit 4 as thats the most recent version that is very much stable enough to work with plus i use that in most of my projects. You can use JUnit 5. Just grab the correct dependency.
Step 2: Create your test class

A very contrived example i know, but I just want to showcase doing a simple unit test via a very common well known sample.
Unlike its predecessor JUnit 3 where you are required to extend another class JUnit 4 doesn’t need to. All you required to do is create a method and annotate it with:
@Test
Then write your unit test case as you would normally with the given test flow of setting the expectation, execute the method in test, and finally verifying the results as shown above.
Optionally, as I have shown there, you can use a set up method to setup the test data:
@Before    
private void setUp() {        
    number1 = 1;        
    number2 = 2;    
}
And also a tear down method to strip down the test setup:
@After    
private void tearDown() {        
    number1 = 0;        
    number2 = 0;    
}
I won’t cover all the JUnit features it has and this can be left as an exercise for the reader.
Step 3: run your test
That’s it. Simple as that. Just like that in order to use JUnit for unit testing in Java.
To run your test, you can easily run it from your beloved IDE.
Or if you’re using Maven like i am then you can this on the command line:
mvn clean test
Step 4: Add in Surefire plugin

Optionally, you can add this maven plugin to control running your unit tests as part of your build. For example, as shown above, you add in the configuration to skip tests in certain conditions.
For example, if you’re making small changes (non code related changes that doesn’t affect the code whatsoever), you may not want to each time run the full unit test suite every time you do a maven local build.
So this `maven-surefire-plugin` comes in handy for these scenarios. But use with care and be vigilant about using it.
Define the expected and desired output for a normal case, with correct input.

Now, implement the test by declaring a class, name it anything (Usually something like TestAddingModule), and add the testAdd method to it (i.e. like the one below) :

Write a method, and above it add the @Test annotation.
In the method, run your binary sum and assertEquals(expectedVal,calculatedVal).
Test your method by running it (in Eclipse, right click, select Run as → JUnit test).

//for normal addition 
@Test
public void testAdd1Plus1() 
{
    int x  = 1 ; int y = 1;
    assertEquals(2, myClass.add(x,y));
}
Add other cases as desired.

Test that your binary sum does not throw a unexpected exception if there is an integer overflow.
Test that your method handles Null inputs gracefully (example below).

//if you are using 0 as default for null, make sure your class works in that case.
@Test
public void testAdd1Plus1() 
{
    int y = 1;
    assertEquals(0, myClass.add(null,y));
    
    
    *
## Graphs 
*
2. Graph Data Structure
A graph is a data structure for storing connected data like a network of people on a social media platform.

A graph consists of vertices and edges. A vertex represents the entity (for example, people) and an edge represents the relationship between entities (for example, a person's friendships).

Let's define a simple Graph to understand this better:


Here, we've defined a simple graph with five vertices and six edges. The circles are vertices representing people and the lines connecting two vertices are edges representing friends on an online portal.

There are a few variations of this simple graph depending on the properties of the edges. Let's briefly go through them in the next sections.

However, we'll only focus on the simple graph presented here for the Java examples in this tutorial.

2.1. Directed Graph
The graph we've defined so far has edges without any direction. If these edges feature a direction in them, the resulting graph is known as a directed graph.

An example of this can be representing who send the friend request in a friendship on the online portal:


Here, we can see that the edges have a fixed direction. The edges can be bi-directional as well.

2.2. Weighted Graph
Again, our simple graph has edges which are unbiased or unweighted. If instead these edges carry relative weight, this graph is known as a weighted graph.

An example of a practical application of this can be representing how relatively old is a friendship on the online portal:


Here, we can see that the edges have weights associated with them. This provides a relative meaning to these edges.

3. Graph Representations
A graph can be represented in different forms like adjacency matrix and adjacency list. Each one has their pros and cons in a different set-up.

We'll introduce these graph representations in this section.

3.1. Adjacency Matrix
An adjacency matrix is a square matrix with dimensions equivalent to the number of vertices in the graph.

The elements of the matrix typically have values ‘0' or ‘1'. A value of ‘1' indicates adjacency between the vertices in the row and column and a value of ‘0' otherwise.

Let's see how the adjacency matrix looks like for our simple graph from the previous section:


This representation is fairly easier to implement and efficient to query as well. However, it's less efficient with respect to space occupied.

3.2. Adjacency List
An adjacency list is nothing but an array of lists. The size of the array is equivalent to the number of vertices in the graph.

The list at a specific index of the array represents the adjacent vertices of the vertex represented by that array index.

Let's see what the adjacency list looks like for our simple graph from the previous section:


This representation is comparatively difficult to create and less efficient to query. However, it offers better space efficiency.

We'll use the adjacency list to represent the graph in this tutorial.

4. Graphs in Java
Java doesn't have a default implementation of the graph data structure.

However, we can implement the graph using Java Collections.

Let's begin by defining a vertex:

class Vertex {
    String label;
    Vertex(String label) {
        this.label = label;
    }
 
    // equals and hashCode
}
The above definition of vertex just features a label but this can represent any possible entity like Person or City.

Also, note that we have to override the equals() and hashCode() methods as these are necessary to work with Java Collections.

As we discussed earlier, a graph is nothing but a collection of vertices and edges which can be represented as either an adjacency matrix or an adjacency list.

Let's see how we can define this using an adjacency list here:

class Graph {
    private Map<Vertex, List<Vertex>> adjVertices;
    
    // standard constructor, getters, setters
}
As we can see here, the class Graph is using Map from Java Collections to define the adjacency list.

There are several operations possible on a graph data structure, such as creating, updating or searching through the graph.

We'll go through some of the more common operations and see how we can implement them in Java.

5. Graph Mutation Operations
To start with, we'll define some methods to mutate the graph data structure.

Let's define methods to add and remove vertices:

void addVertex(String label) {
    adjVertices.putIfAbsent(new Vertex(label), new ArrayList<>());
}
 
void removeVertex(String label) {
    Vertex v = new Vertex(label);
    adjVertices.values().stream().forEach(e -> e.remove(v));
    adjVertices.remove(new Vertex(label));
}
These methods simply add and remove elements from the vertices Set.

Now, let's also define a method to add an edge:

void addEdge(String label1, String label2) {
    Vertex v1 = new Vertex(label1);
    Vertex v2 = new Vertex(label2);
    adjVertices.get(v1).add(v2);
    adjVertices.get(v2).add(v1);
}
This method creates a new Edge and updates the adjacent vertices Map.

In a similar way, we'll define the removeEdge() method:

void removeEdge(String label1, String label2) {
    Vertex v1 = new Vertex(label1);
    Vertex v2 = new Vertex(label2);
    List<Vertex> eV1 = adjVertices.get(v1);
    List<Vertex> eV2 = adjVertices.get(v2);
    if (eV1 != null)
        eV1.remove(v2);
    if (eV2 != null)
        eV2.remove(v1);
}
Next, let's see how we can create the simple graph we have drawn earlier using the methods we've defined so far:

Graph createGraph() {
    Graph graph = new Graph();
    graph.addVertex("Bob");
    graph.addVertex("Alice");
    graph.addVertex("Mark");
    graph.addVertex("Rob");
    graph.addVertex("Maria");
    graph.addEdge("Bob", "Alice");
    graph.addEdge("Bob", "Rob");
    graph.addEdge("Alice", "Mark");
    graph.addEdge("Rob", "Mark");
    graph.addEdge("Alice", "Maria");
    graph.addEdge("Rob", "Maria");
    return graph;
}
We'll finally define a method to get the adjacent vertices of a particular vertex:

List<Vertex> getAdjVertices(String label) {
    return adjVertices.get(new Vertex(label));
}
6. Traversing a Graph
Now that we have graph data structure and functions to create and update it defined, we can define some additional functions for traversing the graph. We need to traverse a graph to perform any meaningful action, like search within the graph.

There are two possible ways to traverse a graph, depth-first traversal and breadth-first traversal.

6.1. Depth-First Traversal
A depth-first traversal starts at an arbitrary root vertex and explores vertices as deeper as possible along each branch before exploring vertices at the same level.

Let's define a method to perform the depth-first traversal:

Set<String> depthFirstTraversal(Graph graph, String root) {
    Set<String> visited = new LinkedHashSet<String>();
    Stack<String> stack = new Stack<String>();
    stack.push(root);
    while (!stack.isEmpty()) {
        String vertex = stack.pop();
        if (!visited.contains(vertex)) {
            visited.add(vertex);
            for (Vertex v : graph.getAdjVertices(vertex)) {              
                stack.push(v.label);
            }
        }
    }
    return visited;
}
Here, we're using a Stack to store the vertices that need to be traversed.

Let's run this on the graph we created in the previous subsection:

assertEquals("[Bob, Rob, Maria, Alice, Mark]", depthFirstTraversal(graph, "Bob").toString());
Please note that we're using vertex “Bob” as our root for traversal here, but this can be any other vertex.

6.2. Breadth-First Traversal
Comparatively, a breadth-first traversal starts at an arbitrary root vertex and explores all neighboring vertices at the same level before going deeper in the graph.

Now let's define a method to perform the breadth-first traversal:

Set<String> breadthFirstTraversal(Graph graph, String root) {
    Set<String> visited = new LinkedHashSet<String>();
    Queue<String> queue = new LinkedList<String>();
    queue.add(root);
    visited.add(root);
    while (!queue.isEmpty()) {
        String vertex = queue.poll();
        for (Vertex v : graph.getAdjVertices(vertex)) {
            if (!visited.contains(v.label)) {
                visited.add(v.label);
                queue.add(v.label);
            }
        }
    }
    return visited;
}
Note that a breadth-first traversal makes use of Queue to store the vertices which need to be traversed.

Let's again run this traversal on the same graph:

assertEquals(
  "[Bob, Alice, Rob, Mark, Maria]", breadthFirstTraversal(graph, "Bob").toString());
Again, the root vertex which is “Bob” here can as well be any other vertex.

7. Java Libraries for Graphs
It's not necessary to always implement the graph from scratch in Java. There are several open source and mature libraries available which offers graph implementations.

In the next few subsections, we'll go through some of these libraries.

7.1. JGraphT
JGraphT is one of the most popular libraries in Java for the graph data structure. It allows the creation of a simple graph, directed graph, weighted graph, amongst others.

Additionally, it offers many possible algorithms on the graph data structure. One of our previous tutorials covers JGraphT in much more detail.

7.2. Google Guava
Google Guava is a set of Java libraries that offer a range of functions including graph data structure and its algorithms.

It supports creating simple Graph, ValueGraph, and Network. These can be defined as Mutable or Immutable.

7.3. Apache Commons
Apache Commons is an Apache project that offers reusable Java components. This includes Commons Graph which offers a toolkit to create and manage graph data structure. This also provides common graph algorithms to operate on the data structure.

7.4. Sourceforge JUNG
Java Universal Network/Graph (JUNG) is a Java framework that provides extensible language for modeling, analysis, and visualization of any data that can be represented as a graph.

JUNG supports a number of algorithms which includes routines like clustering, decomposition, and optimization.

 

These libraries provide a number of implementations based on the graph data structure. There are also more powerful frameworks based on graphs, such as Apache Giraph, currently used at Facebook to analyze the graph formed by their users, and Apache TinkerPop, commonly used on top of graph databases.*

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




   