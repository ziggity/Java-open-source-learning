

 # Java open source 
* Abstraction and Encapsulation - Java programmer must know difference Abstraction and Encapsulation and how these can be utilized in java. A good understanding of POJOs and why we need POJOs will always help you designing a better solution. 

Difference between Abstraction vs Encapsulation
Here are some of the key difference between Encapsulation and Abstraction in point format for your quick revision:

1) The most important difference between Abstraction and Encapsulation is that Abstraction solves the problem at design level while Encapsulation solves its implementation level.

2) Abstraction is about hiding unwanted details while giving out the most essential details, while Encapsulation means hiding the code and data into a single unit e.g. class or method to protect the inner working of an object from the outside world. In other words, Abstraction means extracting common details or generalizing things.

3) Abstraction lets you focus on what the object does instead of how it does, while Encapsulation means hiding the internal details of how an object works. When you keep internal working details private, you can change it later with a better method. The Head First Object-Oriented Analysis and Design has some excellent examples of these OOP concepts, I suggest you read that book at least once to revisit OOP fundamentals.



* Difference between equals and "== "operator - "==" operator compares the if instances refer to the same object. Whereas equals() is a method defined in Object class of java. equals() is used to compare the content of an object.
Collections - A good knowledge of collection can save you from many performance issues. It is always advisable know about:
Difference between list, set and map.
Difference between LinkedList and ArrayList - Arraylist is pretty fast for search operations however Linkedlist is good for fast addition and deletion.
Difference between HashSet and TreeSet - HashSet is usually faster than Treeset if you are not bothered about sorting elements.

Difference between HashMap, HashTable and ConcurrentHashMap - Use of maps can be a bit tricky if you are trying to access them concurrently.
Contract between equals and hashCode - You may or may not use the concept but it is always good to know how java operates internally.
Difference between an Abstract class and Interface - With Java 8 features, now it is even more important to know about Interfaces.
Difference between Instance variable and class variable - I have seen many programmer struggling with the concept of instance variable and class variable. Instance variable belongs to an object and every object will have its own copy of instance variable. Whereas a copy of class variable will be shared among all the objects of class. Mastering the fundamentals of Java programming Language - This is the most important skill that you must learn to become successful java programmer. You must master the fundamentals of the language, specially the areas like OOP, Collections, Generics, Concurrency, I/O, Stings, Exception handling, Inner Classes and JVM architecture.

Recommended readings are OCA Java SE 8 Programmer by by Kathy Sierra and Bert Bates (First read Head First Java if you are a new comer ) and Effective Java by Joshua Bloch.

(2) Data Structures and Algorithms - Programming languages are basically just a tool to solve problems. Problems generally has data to process on to make some decisions and we have to build a procedure to solve that specific problem domain. In any real life complexity of the problem domain and the data we have to handle would be very large. That’s why it is essential to knowing basic data structures like Arrays, Linked Lists, Stacks, Queues, Trees, Heap, Dictionaries ,Hash Tables and Graphs and also basic algorithms like Searching, Sorting, Hashing, Graph algorithms, Greedy algorithms and Dynamic Programming.

Recommended readings are Data Structures & Algorithms in Java by Robert Lafore (Beginner) , Algorithms Robert Sedgewick (intermediate) and Introduction to Algorithms-MIT press by CLRS (Advanced).

(3) Design Patterns - Design patterns are general reusable solution to a commonly occurring problem within a given context in software design and they are absolutely crucial as hard core Java Programmer. If you don't use design patterns you will write much more code, it will be buggy and hard to understand and refactor, not to mention untestable and they are really great way for communicating your intent very quickly with other programmers.

Recommended readings are Head First Design Patterns Elisabeth Freeman and Kathy Sierra and Design Patterns: Elements of Reusable by Gang of four.

(4) Programming Best Practices - Programming is not only about learning and writing code. Code readability is a universal subject in the world of computer programming. It helps standardize products and help reduce future maintenance cost. Best practices helps you, as a programmer to think differently and improves problem solving attitude within you. A simple program can be written in many ways if given to multiple developers. Thus the need to best practices come into picture and every programmer must aware about these things.

Recommended readings are Clean Code by Robert Cecil Martin and Code Complete by Steve McConnell.

(5) Testing and Debugging (T&D) - As you know about the writing the code for specific problem domain, you have to learn how to test that code snippet and debug it when it is needed. Some programmers skip their unit testing or other testing methodology part and leave it to QA guys. That will lead to delivering 80% bugs hiding in your code to the QA team and reduce the productivity and risking and pushing your project boundaries to failure. When a miss behavior or bug occurred within your code when the testing phase. It is essential to know about the debugging techniques to identify that bug and its root cause.
*
*This is an open source knowledge share on all things Java CS related*
## Multithreading
*Multithreading means that you have multiple threads of execution inside the same application. A thread is like a separate CPU executing your application. Thus, a multithreaded application is like an application that has multiple CPUs executing different parts of the code at the same time.
A thread is not equal to a CPU though. Usually a single CPU will share its execution time among multiple threads, switching between executing each of the threads for a given amount of time. It is also possible to have the threads of an application be executed by different CPUs.
Why Multithreading?
There are several reasons as to why one would use multithreading in an application. Some of the most common reasons for multithreading are:

Better utilization of a single CPU.
Better utilization of multiple CPUs or CPU cores.
Better user experience with regards to responsiveness.
Better user experience with regards to fairness.
I will explain each of these reasons in more detail in the following sections.

Better Utilization of a Single CPU
One of the most common reasons is to be able to better utilize the resources in the computer. For instance, if one thread is waiting for the response to a request sent over the network, then another thread could use the CPU in the meantime to do something else. Additionally, if the computer has multiple CPUs, or if the CPU has multiple execution cores, then multithreading can also help your application utilize these extra CPU cores.

Better Utilization of Multiple CPUs or CPU Cores
If a computer contains multiple CPUs or the CPU contains multiple execution cores, then you need to use multiple threads for your application to be able to utilize all of the CPUs or CPU cores. A single thread can at most utilize a single CPU, and as I mentioned above, sometimes not even completely utilize a single CPU.

Better User Experience with Regards to Responsiveness
Another reason to use multithreading is to provide a better user experience. For instance, if you click on a button in a GUI and this results in a request being sent over the network, then it matters which thread performs this request. If you use the same thread that is also updating the GUI, then the user might experience the GUI "hanging" while the GUI thread is waiting for the response for the request. Instead, such a request could be performed by a backgroun thread so the GUI thread is free to respond to other user requests in the meantime.

Better User Experience with Regards to Fairness
A fourth reason is to share resources of a computer more fairly among users. As example imagine a server that receives requests from clients, and only has one thread to execute these requests. If a client sends a requests that takes a long time to process, then all other client's requests would have to wait until that one request has finished. By having each client's request executed by its own thread then no single task can monopolize the CPU completely.

Multithreading vs. Multitasking
Back in the old days a computer had a single CPU, and was only capable of executing a single program at a time. Most smaller computers were not really powerful enough to execute multiple programs at the same time, so it was not attempted. To be fair, many mainframe systems have been able to execute multiple programs at a time for many more years than personal computers.

Multitasking
Later came multitasking which meant that computers could execute multiple programs (AKA tasks or processes) at the same time. It wasn't really "at the same time" though. The single CPU was shared between the programs. The operating system would switch between the programs running, executing each of them for a little while before switching.

Along with multitasking came new challenges for software developers. Programs can no longer assume to have all the CPU time available, nor all memory or any other computer resources. A "good citizen" program should release all resources it is no longer using, so other programs can use them.

Multithreading
Later yet came multithreading which mean that you could have multiple threads of execution inside the same program. A thread of execution can be thought of as a CPU executing the program. When you have multiple threads executing the same program, it is like having multiple CPUs execute within the same program.

Multithreading is Hard
Multithreading can be a great way to increase the performance of some types of programs. However, mulithreading is even more challenging than multitasking. The threads are executing within the same program and are hence reading and writing the same memory simultaneously. This can result in errors not seen in a singlethreaded program. Some of these errors may not be seen on single CPU machines, because two threads never really execute "simultaneously". Modern computers, though, come with multi core CPUs, and even with multiple CPUs too. This means that separate threads can be executed by separate cores or CPUs simultaneously.

Multithreading on a multi-CPU computer
If a thread reads a memory location while another thread writes to it, what value will the first thread end up reading? The old value? The value written by the second thread? Or a value that is a mix between the two? Or, if two threads are writing to the same memory location simultaneously, what value will be left when they are done? The value written by the first thread? The value written by the second thread? Or a mix of the two values written?

Without proper precautions any of these outcomes are possible. The behaviour would not even be predictable. The outcome could change from time to time. Therefore it is important as a developer to know how to take the right precautions - meaning learning to control how threads access shared resources like memory, files, databases etc. That is one of the topics this Java concurrency tutorial addresses.

Multithreading and Concurrency in Java
Java was one of the first languages to make multithreading easily available to developers. Java had multithreading capabilities from the very beginning. Therefore, Java developers often face the problems described above. That is the reason I am writing this trail on Java concurrency. As notes to myself, and any fellow Java developer whom may benefit from it.

The trail will primarily be concerned with multithreading in Java, but some of the problems occurring in multithreading are similar to problems occurring in multitasking and in distributed systems. References to multitasking and distributed systems may therefore occur in this trail too. Hence the word "concurrency" rather than "multithreading".

The first Java concurrency model assumed that multiple threads executing within the same application would also share objects. This type of concurrency model is typically referred to as a "shared state concurrency model". A lot of the concurrency language constructs and utilities are designed to support this concurrency model.

However, a lot has happened in the world of concurrent architecture and design since the first Java concurrency books were written, and even since the Java 5 concurrency utilities were released

The shared state concurrency model causes a lot of concurrency problems which can be hard to solve elegantly. Therefore, an alternative concurrency model referred to as "shared nothing" or "separate state" has gained popularity. In the separate state concurrency model the threads do not share any objects or data. This avoids a lot of the concurrent access problems of the shared state concurrency model.

New, asynchronous "separate state" platforms and toolkits like Netty, Vert.x and Play / Akka and Qbit have emerged. New non-blocking concurrency algorithms have been published, and new non-blocking tools like the LMax Disrupter have been added to our toolkits. New functional programming parallelism has been introduced with the Fork and Join framework in Java 7, and the collection streams API in Java 8.
*
## Algorithms

## Time Complexity

* O(1) -> constant time - near instant speed - ie only one operation needs to be performed to locate it.
* O(log n) -> logarithmic time -> often found in binary trees, for binary search, highly effecient
* O(n) ->linear time - takes time of n - linear of size of the input. 
* O(n log n) ->  Divide and conquer - not optimized for speed but gets the job done.
* O(n^2) -> polynomial time, (slow) nested for loop so for each loop on n array, do a loop on another array
* O(2^n)  -> exponential time - slow
* n! -> factorial time (very slow - traveling salesmen for example, travel N paths on a tree, but at each node calculate the entire path again (HUGE calculations))

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
## concurency 
*
1.1. What is concurrency?
Concurrency is the ability to run several programs or several parts of a program in parallel. If a time consuming task can be performed asynchronously or in parallel, this improves the throughput and the interactivity of the program.

A modern computer has several CPU’s or several cores within one CPU. The ability to leverage these multi-cores can be the key for a successful high-volume application.

1.2. Process vs. threads
A process runs independently and isolated of other processes. It cannot directly access shared data in other processes. The resources of the process, e.g. memory and CPU time, are allocated to it via the operating system.

A thread is a so called lightweight process. It has its own call stack, but can access shared data of other threads in the same process. Every thread has its own memory cache. If a thread reads shared data, it stores this data in its own memory cache.

A thread can re-read the shared data.

A Java application runs by default in one process. Within a Java application you work with several threads to achieve parallel processing or asynchronous behavior.

2. Improvements and issues with concurrency
2.1. Limits of concurrency gains
Within a Java application you work with several threads to achieve parallel processing or asynchronous behavior. Concurrency promises to perform certain task faster as these tasks can be divided into subtasks and these subtasks can be executed in parallel. Of course the runtime is limited by parts of the task which can be performed in parallel.

The theoretical possible performance gain can be calculated by the following rule which is referred to as Amdahl’s Law.

If F is the percentage of the program which can not run in parallel and N is the number of processes, then the maximum performance gain is 1 / (F+ ((1-F)/N)).

2.2. Concurrency issues
Threads have their own call stack, but can also access shared data. Therefore you have two basic problems, visibility and access problems.

A visibility problem occurs if thread A reads shared data which is later changed by thread B and thread A is unaware of this change.

An access problem can occur if several threads access and change the same shared data at the same time.

Visibility and access problem can lead to:

Liveness failure: The program does not react anymore due to problems in the concurrent access of data, e.g. deadlocks.

Safety failure: The program creates incorrect data.

3. Concurrency in Java
3.1. Processes and Threads
A Java program runs in its own process and by default in one thread. Java supports threads as part of the Java language via the Thread code. The Java application can create new threads via this class.

Java 1.5 also provides improved support for concurrency with the java.util.concurrent package.

3.2. Locks and thread synchronization
Java provides locks to protect certain parts of the code to be executed by several threads at the same time. The simplest way of locking a certain method or Java class is to define the method or class with the synchronized keyword.

The synchronized keyword in Java ensures:

that only a single thread can execute a block of code at the same time

that each thread entering a synchronized block of code sees the effects of all previous modifications that were guarded by the same lock

Synchronization is necessary for mutually exclusive access to blocks of and for reliable communication between threads.

You can use the synchronized keyword for the definition of a method. This would ensure that only one thread can enter this method at the same time. Another thread which is calling this method would wait until the first thread leaves this method.

public synchronized void critial() {
    // some thread critical stuff
    // here
}
You can also use the synchronized keyword to protect blocks of code within a method. This block is guarded by a key, which can be either a string or an object. This key is called the lock.

All code which is protected by the same lock can only be executed by one thread at the same time.

For example the following data structure will ensure that only one thread can access the inner block of the add() and next() methods.

package de.vogella.pagerank.crawler;

import java.util.ArrayList;
import java.util.List;

/**
 * Data structure for a web crawler. Keeps track of the visited sites and keeps
 * a list of sites which needs still to be crawled.
 *
 * @author Lars Vogel
 *
 */
public class CrawledSites {
    private List<String> crawledSites = new ArrayList<String>();
    private List<String> linkedSites = new ArrayList<String>();

    public void add(String site) {
        synchronized (this) {
            if (!crawledSites.contains(site)) {
                linkedSites.add(site);
            }
        }
    }

    /**
     * Get next site to crawl. Can return null (if nothing to crawl)
     */
    public String next() {
        if (linkedSites.size() == 0) {
            return null;
        }
        synchronized (this) {
            // Need to check again if size has changed
            if (linkedSites.size() > 0) {
                String s = linkedSites.get(0);
                linkedSites.remove(0);
                crawledSites.add(s);
                return s;
            }
            return null;
        }
    }

}
3.3. Volatile
If a variable is declared with the volatile keyword then it is guaranteed that any thread that reads the field will see the most recently written value. The volatile keyword will not perform any mutual exclusive lock on the variable.

As of Java 5, write access to a volatile variable will also update non-volatile variables which were modified by the same thread. This can also be used to update values within a reference variable, e.g. for a volatile variable person. In this case you must use a temporary variable person and use the setter to initialize the variable and then assign the temporary variable to the final variable. This will then make the address changes of this variable and the values visible to other threads.
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
* Stacks. A stack is a collection that is based on the last-in-first-out (LIFO) policy. By tradition, we name the stack insert method push() and the stack remove operation pop(). We also include a method to test whether the stack is empty, as indicated in the following API:
API for a stack
* Queue. A queue supports the insert and remove operations using a first-in first-out (FIFO) discipline. By convention, we name the queue insert operation enqueue and the remove operation dequeue, as indicated in the following API:
API for a LIFO queue
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

## Interview questions
* Basic Java Interview Questions
Q1. Explain JDK, JRE and JVM?
JDK vs JRE vs JVM
JDK	JRE	JVM
It stands for Java Development Kit.	It stands for Java Runtime Environment.	It stands for Java Virtual Machine.
It is the tool necessary to compile, document and package Java programs.	JRE refers to a runtime environment in which Java bytecode can be executed.	It is an abstract machine. It is a specification that provides a run-time environment in which Java bytecode can be executed.
It contains JRE + development tools.	It’s an implementation of the JVM which physically exists.	JVM follows three notations: Specification, Implementation, and Runtime Instance.

Q2. Explain public static void main(String args[]) in Java.
main() in Java is the entry point for any Java program. It is always written as public static void main(String[] args).

public: Public is an access modifier, which is used to specify who can access this method. Public means that this Method will be accessible by any Class.
static: It is a keyword in java which identifies it is class-based. main() is made static in Java so that it can be accessed without creating the instance of a Class. In case, main is not made static then the compiler will throw an error as main() is called by the JVM before any objects are made and only static methods can be directly invoked via the class. 
void: It is the return type of the method. Void defines the method which will not return any value.
main: It is the name of the method which is searched by JVM as a starting point for an application with a particular signature only. It is the method where the main execution occurs.
String args[]: It is the parameter passed to the main method.

Q3. Why Java is platform independent?
Java is called platform independent because of its byte codes which can run on any system irrespective of its underlying operating system.


Q4. Why Java is not 100% Object-oriented?

Java is not 100% Object-oriented because it makes use of eight primitive data types such as boolean, byte, char, int, float, double, long, short which are not objects.

Q5. What are wrapper classes in Java?

Wrapper classes convert the Java primitives into the reference types (objects). Every primitive data type has a class dedicated to it. These are known as wrapper classes because they “wrap” the primitive data type into an object of that class. Refer to the below image which displays different primitive type, wrapper class and constructor argument.


Q6. What are constructors in Java?
In Java, constructor refers to a block of code which is used to initialize an object. It must have the same name as that of the class. Also, it has no return type and it is automatically called when an object is created.

There are two types of constructors:

Default Constructor: In Java, a default constructor is the one which does not take any inputs. In other words, default constructors are the no argument constructors which will be created by default in case you no other constructor is defined by the user. Its main purpose is to initialize the instance variables with the default values. Also, it is majorly used for object creation. 
Parameterized Constructor: The parameterized constructor in Java, is the constructor which is capable of initializing the instance variables with the provided values. In other words, the constructors which take the arguments are called parameterized constructors.

Q7. What is singleton class in Java and how can we make a class singleton?
Singleton class is a class whose only one instance can be created at any given time, in one JVM. A class can be made singleton by making its constructor private.

Q8. What is the difference between Array list and vector in Java?
ArrayList	Vector
Array List is not synchronized.	 Vector is synchronized.
Array List is fast as it’s non-synchronized.	Vector is slow as it is thread safe.
If an element is inserted into the Array List, it increases its Array size by 50%.	Vector defaults to doubling size of its array.
Array List does not define the increment size.	Vector defines the increment size.
Array List can only use Iterator for traversing an Array List.	Vector can use both Enumeration and Iterator for traversing.

Q9. What is the difference between equals() and == in Java?
Equals() method is defined in Object class in Java and used for checking equality of two objects defined by business logic.

“==” or equality operator in Java is a binary operator provided by Java programming language and used to compare primitives and objects. public boolean equals(Object o) is the method provided by the Object class. The default implementation uses == operator to compare two objects. For example: method can be overridden like String class. equals() method is used to compare the values of two objects.

Q10. What are the differences between Heap and Stack Memory in Java?
The major difference between Heap and Stack memory are:

Features	Stack	Heap
Memory	Stack memory is used only by one thread of execution.	Heap memory is used by all the parts of the application.
Access	Stack memory can’t be accessed by other threads.	Objects stored in the heap are globally accessible.
Memory Management	Follows LIFO manner to free memory.	Memory management is based on the generation associated with each object.
Lifetime	Exists until the end of execution of the thread.	Heap memory lives from the start till the end of application execution.
Usage	Stack memory only contains local primitive and reference variables to objects in heap space.	Whenever an object is created, it’s always stored in the Heap space.

Q11. What is a package in Java? List down various advantages of packages.
Packages in Java, are the collection of related classes and interfaces which are bundled together. By using packages, developers can easily modularize the code and optimize its reuse. Also, the code within the packages can be imported by other classes and reused. Below I have listed down a few of its advantages:

Packages help in avoiding name clashes
They provide easier access control on the code
Packages can also contain hidden classes which are not visible to the outer classes and only used within the package
Creates a proper hierarchical structure which makes it easier to locate the related classes
Q12. Why pointers are not used in Java?
Java doesn’t use pointers because they are unsafe and increases the complexity of the program. Since, Java is known for its simplicity of code, adding the concept of pointers will be contradicting. Moreover, since JVM is responsible for implicit memory allocation, thus in order to avoid direct access to memory by the user,  pointers are discouraged in Java.

Q13. What is JIT compiler in Java?
JIT stands for Just-In-Time compiler in Java. It is a program that helps in converting the Java bytecode into instructions that are sent directly to the processor. By default, the JIT compiler is enabled in Java and is activated whenever a Java method is invoked. The JIT compiler then compiles the bytecode of the invoked method into native machine code, compiling it “just in time” to execute. Once the method has been compiled, the JVM summons the compiled code of that method directly rather than interpreting it. This is why it is often responsible for the performance optimization of Java applications at the run time.

Q14. What are access modifiers in Java?
In Java, access modifiers are special keywords which are used to restrict the access of a class, constructor, data member and method in another class. Java supports four types of access modifiers:

Default
Private
Protected
Public
Modifier	Default	Private	Protected	Public
Same class	YES	YES	YES	YES
Same Package subclass	YES	NO	YES	YES
Same Package non-subclass	YES	NO	YES	YES
Different package subclass	NO	NO	YES	YES
Different package non-subclass	NO	NO	NO	YES
Q15. Define a Java Class.
A class in Java is a blueprint which includes all your data.  A class contains fields (variables) and methods to describe the behavior of an object. Let’s have a look at the syntax of a class.

class Abc {
member variables // class body
methods}
Q16. What is an object in Java and how is it created?
An object is a real-world entity that has a state and behavior. An object has three characteristics:

State
Behavior
Identity
An object is created using the ‘new’ keyword. For example:

ClassName obj = new ClassName();

Q17. What is Object Oriented Programming?
Object-oriented programming or popularly known as OOPs is a programming model or approach where the programs are organized around objects rather than logic and functions. In other words, OOP mainly focuses on the objects that are required to be manipulated instead of logic. This approach is ideal for the programs large and complex codes and needs to be actively updated or maintained.

Q18. What are the main concepts of OOPs in Java?
Object-Oriented Programming or OOPs is a programming style that is associated with concepts like:

Inheritance: Inheritance is a process where one class acquires the properties of another.
Encapsulation: Encapsulation in Java is a mechanism of wrapping up the data and code together as a single unit.
Abstraction: Abstraction is the methodology of hiding the implementation details from the user and only providing the functionality to the users. 
Polymorphism: Polymorphism is the ability of a variable, function or object to take multiple forms.
Q19. What is the difference between a local variable and an instance variable?
In Java, a local variable is typically used inside a method, constructor, or a block and has only local scope. Thus, this variable can be used only within the scope of a block. The best benefit of having a local variable is that other methods in the class won’t be even aware of that variable.

Example

if(x > 100)
{
String test = "Edureka";
}
 

Whereas, an instance variable in Java, is a variable which is bounded to its object itself. These variables are declared within a class, but outside a method. Every object of that class will create it’s own copy of the variable while using it. Thus, any changes made to the variable won’t reflect in any other instances of that class and will be bound to that particular instance only.


class Test{
public String EmpName;
public int empAge;
}
Q20. Differentiate between the constructors and methods in Java?
Methods	Constructors
1. Used to represent the behavior of an object	1. Used to initialize the state of an object
2. Must have a return type	2. Do not have any return type
3. Needs to be invoked explicitly	3. Is invoked implicitly
4. No default method is provided by the compiler	4. A default constructor is provided by the compiler if the class has none
5. Method name may or may not be same as class name	5. Constructor name must always be the same as the class name

Q21. What is final keyword in Java?
final is a special keyword in Java that is used as a non-access modifier. A final variable can be used in different contexts such as:

final variable
When the final keyword is used with a variable then its value can’t be changed once assigned. In case the no value has been assigned to the final variable then using only the class constructor a value can be assigned to it.

final method
When a method is declared final then it can’t be overridden by the inheriting class.

final class
When a class is declared as final in Java, it can’t be extended by any subclass class but it can extend other class.

Q22. What is the difference between break and continue statements?
break	continue
1. Can be used in switch and loop (for, while, do while) statements	1. Can be only used with loop statements
2. It causes the switch or loop statements to terminate the moment it is executed	2. It doesn’t terminate the loop but causes the loop to jump to the next iteration
3. It terminates the innermost enclosing loop or switch immediately	3. A continue within a loop nested with a switch will cause the next loop iteration to execute
Example break:

for (int i = 0; i < 5; i++)
{
if (i == 3)
{
break;
}
System.out.println(i);
}
Example continue:

for (int i = 0; i < 5; i++)
{
if(i == 2)
{
continue;
}
System.out.println(i);
}
Q23.What is an infinite loop in Java? Explain with an example.
An infinite loop is an instruction sequence in Java that loops endlessly when a functional exit isn’t met. This type of loop can be the result of a programming error or may also be a deliberate action based on the application behavior. An infinite loop will terminate automatically once the application exits.

For example:

public class InfiniteForLoopDemo
{
public static void main(String[] arg) {
for(;;)
System.out.println("Welcome to Edureka!");
// To terminate this program press ctrl + c in the console.
}
}
 

Q24. What is the difference between this() and super() in Java?
In Java, super() and this(), both are special keywords that are used to call the constructor. 

this()	super()
1. this() represents the current instance of a class	1. super() represents the current instance of a parent/base class
2. Used to call the default constructor of the same class	2. Used to call the default constructor of the parent/base class
3. Used to access methods of the current class	3. Used to access methods of the base class
4.  Used for pointing the current class instance	4. Used for pointing the superclass instance
5. Must be the first line of a block	5. Must be the first line of a block
Q25. What is Java String Pool?
Java String pool refers to a collection of Strings which are stored in heap memory. In this, whenever a new object is created, String pool first checks whether the object is already present in the pool or not. If it is present, then the same reference is returned to the variable else new object will be created in the String pool and the respective reference will be returned.

String pool - Java Interview Questions - Edureka

Q26. Differentiate between static and non-static methods in Java.
Static Method	Non-Static Method
1. The static keyword must be used before the method name	1. No need to use the static keyword before the method name
2. It is called using the class (className.methodName) 	2. It is can be called like any general method
3. They can’t access any non-static instance variables or methods	3. It can access any static method and any static variable without creating an instance of the class
Q27. What is constructor chaining in Java?
In Java, constructor chaining is the process of calling one constructor from another with respect to the current object. Constructor chaining is possible only through legacy where a subclass constructor is responsible for invoking the superclass’ constructor first. There could be any number of classes in the constructor chain. Constructor chaining can be achieved in two ways:

Within the same class using this()
From base class using super()
Q28. Difference between String, StringBuilder, and StringBuffer.

Factor	String	StringBuilder	StringBuffer
Storage Area	Constant String Pool	Heap Area	Heap Area
Mutability	Immutable	Mutable	Mutable
Thread Safety	Yes	No	Yes
Performance	Fast	More efficient	Less efficient
Q29. What is a classloader in Java?
The Java ClassLoader is a subset of JVM (Java Virtual Machine) that is responsible for loading the class files. Whenever a Java program is executed it is first loaded by the classloader. Java provides three built-in classloaders:

Bootstrap ClassLoader
Extension ClassLoader
System/Application ClassLoader
Q30. Why Java Strings are immutable in nature?
In Java, string objects are immutable in nature which simply means once the String object is created its state cannot be modified. Whenever you try to update the value of that object instead of updating the values of that particular object, Java creates a new string object. Java String objects are immutable as String objects are generally cached in the String pool. Since String literals are usually shared between multiple clients, action from one client might affect the rest. It enhances security, caching, synchronization, and performance of the application. 
Q31. What is the difference between an array and an array list?
Array	ArrayList
Cannot contain values of different data types	Can contain values of different data types.
Size must be defined at the time of declaration	Size can be dynamically changed
Need to specify the index in order to add data	No need to specify the index
Arrays are not type parameterized	Arraylists are type 
Arrays can contain primitive data types as well as objects	Arraylists can contain only objects, no primitive data types are allowed
Q32. What is a Map in Java?
In Java, Map is an interface of Util package which maps unique keys to values. The Map interface is not a subset of the main Collection interface and thus it behaves little different from the other collection types. Below are a few of the characteristics of Map interface: 

Map doesn’t contain duplicate keys.
Each key can map at max one value.

Q33. What is collection class in Java? List down its methods and interfaces.
In Java, the collection is a framework that acts as an architecture for storing and manipulating a group of objects. Using Collections you can perform various tasks like searching, sorting, insertion, manipulation, deletion, etc. Java collection framework includes the following:

Interfaces
Classes
Methods
The below image shows the complete hierarchy of the Java Collection.

FrameworkHierarchy - Java Collections -

In case you are facing any challenges with these java interview questions, please comment on your problems in the section below.

OOPS Java Interview Questions
Q1. What is Polymorphism?
Polymorphism is briefly described as “one interface, many implementations”. Polymorphism is a characteristic of being able to assign a different meaning or usage to something in different contexts – specifically, to allow an entity such as a variable, a function, or an object to have more than one form. There are two types of polymorphism:

Compile time polymorphism
Run time polymorphism
Compile time polymorphism is method overloading whereas Runtime time polymorphism is done using inheritance and interface.

Q2. What is runtime polymorphism or dynamic method dispatch?
In Java, runtime polymorphism or dynamic method dispatch is a process in which a call to an overridden method is resolved at runtime rather than at compile-time. In this process, an overridden method is called through the reference variable of a superclass. Let’s take a look at the example below to understand it better.

class Car {
void run()
{
System.out.println(“car is running”); 
}
}
class Audi extends Car {
void run()
{
System.out.prinltn(“Audi is running safely with 100km”);
}
public static void main(String args[])
{
Car b= new Audi();    //upcasting
b.run();
}
}
Q3. What is abstraction in Java?
Abstraction refers to the quality of dealing with ideas rather than events. It basically deals with hiding the details and showing the essential things to the user. Thus you can say that abstraction in Java is the process of hiding the implementation details from the user and revealing only the functionality to them. Abstraction can be achieved in two ways:

Abstract Classes (0-100% of abstraction can be achieved)
Interfaces (100% of abstraction can be achieved)
Q4. What do you mean by an interface in Java?
An interface in Java is a blueprint of a class or you can say it is a collection of abstract methods and static constants. In an interface, each method is public and abstract but it does not contain any constructor. Thus, interface basically is a group of related methods with empty bodies. Example:

public interface Animal {
  public void eat();
  public void sleep();
  public void run();
}
Q5. What is the difference between abstract classes and interfaces?
Abstract Class	Interfaces
An abstract class can provide complete, default code and/or just the details that have to be overridden	An interface cannot provide any code at all, just the signature
In the case of an abstract class, a class may extend only one abstract class	A Class may implement several interfaces
An abstract class can have non-abstract methods	All methods of an Interface are abstract
An abstract class can have instance variables	An Interface cannot have instance variables
An abstract class can have any visibility: public, private, protected	An Interface visibility must be public (or) none
If we add a new method to an abstract class then we have the option of providing default implementation and therefore all the existing code might work properly	If we add a new method to an Interface then we have to track down all the implementations of the interface and define implementation for the new method
An abstract class can contain constructors	An Interface cannot contain constructors
Abstract classes are fast	Interfaces are slow as it requires extra indirection to find the corresponding method in the actual class
Q6. What is inheritance in Java?

Inheritance in Java is the concept where the properties of one class can be inherited by the other. It helps to reuse the code and establish a relationship between different classes. Inheritance is performed between two types of classes:

Parent class (Super or Base class)
Child class (Subclass or Derived class)

A class which inherits the properties is known as Child Class whereas a class whose properties are inherited is known as Parent class.

Q7. What are the different types of inheritance in Java?
Java supports four types of inheritance which are:

Single Inheritance: In single inheritance, one class inherits the properties of another i.e there will be only one parent as well as one child class.
Multilevel Inheritance: When a class is derived from a class which is also derived from another class, i.e. a class having more than one parent class but at different levels, such type of inheritance is called Multilevel Inheritance.
Hierarchical Inheritance: When a class has more than one child classes (subclasses) or in other words, more than one child classes have the same parent class, then such kind of inheritance is known as hierarchical.
Hybrid Inheritance: Hybrid inheritance is a combination of two or more types of inheritance.
Q8. What is method overloading and method overriding?
Method Overloading :
In Method Overloading, Methods of the same class shares the same name but each method must have a different number of parameters or parameters having different types and order.
Method Overloading is to “add” or “extend” more to the method’s behavior.
It is a compile-time polymorphism.
The methods must have a different signature.
It may or may not need inheritance in Method Overloading.
Let’s take a look at the example below to understand it better.

class Adder {
Static int add(int a, int b)
{
return a+b;
}
Static double add( double a, double b)
{
return a+b;
}
public static void main(String args[])
{
System.out.println(Adder.add(11,11));
System.out.println(Adder.add(12.3,12.6));
}}
Method Overriding:  
In Method Overriding, the subclass has the same method with the same name and exactly the same number and type of parameters and same return type as a superclass.
Method Overriding is to “Change” existing behavior of the method.
It is a run time polymorphism.
The methods must have the same signature.
It always requires inheritance in Method Overriding.
Let’s take a look at the example below to understand it better.

class Car {
void run(){
System.out.println(“car is running”); 
}
Class Audi extends Car{
void run()
{
System.out.prinltn("Audi is running safely with 100km");
}
public static void main( String args[])
{
Car b=new Audi();
b.run();
}
}
Q9. Can you override a private or static method in Java?
You cannot override a private or static method in Java. If you create a similar method with the same return type and same method arguments in child class then it will hide the superclass method; this is known as method hiding. Similarly, you cannot override a private method in subclass because it’s not accessible there. What you can do is create another private method with the same name in the child class. Let’s take a look at the example below to understand it better.

class Base {
private static void display() {
System.out.println("Static or class method from Base");
}
public void print() {
System.out.println("Non-static or instance method from Base");
}
class Derived extends Base {
private static void display() {
System.out.println("Static or class method from Derived");
}
public void print() {
System.out.println("Non-static or instance method from Derived");
}
public class test {
public static void main(String args[])
{
Base obj= new Derived();
obj1.display();
obj1.print();
}
}
Q10. What is multiple inheritance? Is it supported by Java?
MultipleInheritance - Java Interview Questions - EdurekaIf a child class inherits the property from multiple classes is known as multiple inheritance. Java does not allow to extend multiple classes.

The problem with multiple inheritance is that if multiple parent classes have the same method name, then at runtime it becomes difficult for the compiler to decide which method to execute from the child class.

Therefore, Java doesn’t support multiple inheritance. The problem is commonly referred to as Diamond Problem.

Q11. What is encapsulation in Java?
Encapsulation is a mechanism where you bind your data(variables) and code(methods) together as a single unit. Here, the data is hidden from the outer world and can be accessed only via current class methods. This helps in protecting the data from any unnecessary modification. We can achieve encapsulation in Java by:

Declaring the variables of a class as private.
Providing public setter and getter methods to modify and view the values of the variables.
Q12. What is an association?
Association is a relationship where all object have their own lifecycle and there is no owner. Let’s take the example of Teacher and Student. Multiple students can associate with a single teacher and a single student can associate with multiple teachers but there is no ownership between the objects and both have their own lifecycle. These relationships can be one to one, one to many, many to one and many to many.

Q13. What do you mean by aggregation?
An aggregation is a specialized form of Association where all object has their own lifecycle but there is ownership and child object can not belong to another parent object. Let’s take an example of Department and teacher. A single teacher can not belong to multiple departments, but if we delete the department teacher object will not destroy. 

Q14. What is composition in Java?
Composition is again a specialized form of Aggregation and we can call this as a “death” relationship. It is a strong type of Aggregation. Child object does not have their lifecycle and if parent object deletes all child object will also be deleted. Let’s take again an example of a relationship between House and rooms. House can contain multiple rooms there is no independent life of room and any room can not belongs to two different houses if we delete the house room will automatically delete.

Q15. What is a marker interface?

A Marker interface can be defined as the interface having no data member and member functions. In simpler terms, an empty interface is called the Marker interface. The most common examples of Marker interface in Java are Serializable, Cloneable etc. The marker interface can be declared as follows.

public interface Serializable{
}
Q16. What is object cloning in Java?

Object cloning in Java is the process of creating an exact copy of an object. It basically means the ability to create an object with a similar state as the original object. To achieve this, Java provides a method clone() to make use of this functionality. This method creates a new instance of the class of the current object and then initializes all its fields with the exact same contents of corresponding fields. To object clone(), the marker interface java.lang.Cloneable must be implemented to avoid any runtime exceptions. One thing you must note is Object clone() is a protected method, thus you need to override it.

Q17. What is a copy constructor in Java?
Copy constructor is a member function that is used to initialize an object using another object of the same class. Though there is no need for copy constructor in Java since all objects are passed by reference. Moreover, Java does not even support automatic pass-by-value.

Q18. What is a constructor overloading in Java?
In Java, constructor overloading is a technique of adding any number of constructors to a class each having a different parameter list. The compiler uses the number of parameters and their types in the list to differentiate the overloaded constructors.

class Demo
{
int i;
public Demo(int a)
{
i=k;
}
public Demo(int a, int b)
{
//body
}
}
In case you are facing any challenges with these java interview questions, please comment on your problems in the section below. Apart from this Java Interview Questions Blog, if you want to get trained from professionals on this technology, you can opt for a structured training from edureka!
Servlets Interview Questions  
Q1. What is a servlet?
Java Servlet is server-side technologies to extend the capability of web servers by providing support for dynamic response and data persistence.
The javax.servlet and javax.servlet.http packages provide interfaces and classes for writing our own servlets.
All servlets must implement the javax.servlet.Servlet interface, which defines servlet lifecycle methods. When implementing a generic service, we can extend the GenericServlet class provided with the Java Servlet API. The HttpServlet class provides methods, such as doGet() and doPost(), for handling HTTP-specific services.
Most of the times, web applications are accessed using HTTP protocol and thats why we mostly extend HttpServlet class. Servlet API hierarchy is shown in below image.
Servlet - Java Interview Questions - Edureka

Q2. What are the differences between Get and Post methods?
Get	Post
Limited amount of data can be sent because data is sent in header.	Large amount of data can be sent because data is sent in body.
 Not Secured because data is exposed in URL bar.	 Secured because data is not exposed in URL bar.
 Can be bookmarked	 Cannot be bookmarked
 Idempotent	 Non-Idempotent
 It is more efficient and used than Post	 It is less efficient and used
Q3. What is Request Dispatcher?
RequestDispatcher interface is used to forward the request to another resource that can be HTML, JSP or another servlet in same application. We can also use this to include the content of another resource to the response.

There are two methods defined in this interface:

1.void forward()

2.void include()

ForwardMethod - Java Interview Questions - Edureka
IncludeMethod - Java Interview Questions - Edureka
Q4. What are the differences between forward() method and sendRedirect() methods?

forward() method	SendRedirect() method
forward() sends the same request to another resource.	sendRedirect() method sends new request always because it uses the URL bar of the browser.
 forward() method works at server side.	 sendRedirect() method works at client side.
 forward() method works within the server only.	sendRedirect() method works within and outside the server.
Q5. What is the life-cycle of a servlet?
There are 5 stages in the lifecycle of a servlet:LifeCycleServlet - Java Interview Questions - Edureka

Servlet is loaded
Servlet is instantiated
Servlet is initialized
Service the request
Servlet is destroyed
Q6. How does cookies work in Servlets?
Cookies are text data sent by server to the client and it gets saved at the client local machine.
Servlet API provides cookies support through javax.servlet.http.Cookie class that implements Serializable and Cloneable interfaces.
HttpServletRequest getCookies() method is provided to get the array of Cookies from request, since there is no point of adding Cookie to request, there are no methods to set or add cookie to request.
Similarly HttpServletResponse addCookie(Cookie c) method is provided to attach cookie in response header, there are no getter methods for cookie.
Q7. What are the differences between ServletContext vs ServletConfig?
The difference between ServletContext and ServletConfig in Servlets JSP is in below tabular format.

ServletConfig	ServletContext
Servlet config object represent single servlet	It represent whole web application running on particular JVM and common for all the servlet
Its like local parameter associated with particular servlet	Its like global parameter associated with whole application
It’s a name value pair defined inside the servlet section of web.xml file so it has servlet wide scope	ServletContext has application wide scope so define outside of servlet tag in web.xml file.
getServletConfig() method is used to get the config object	getServletContext() method is  used to get the context object.
for example shopping cart of a user is a specific to particular user so here we can use servlet config	To get the MIME type of a file or application session related information is stored using servlet context object.

Q8. What are the different methods of session management in servlets?
Session is a conversational state between client and server and it can consists of multiple request and response between client and server. Since HTTP and Web Server both are stateless, the only way to maintain a session is when some unique information about the session (session id) is passed between server and client in every request and response.

Some of the common ways of session management in servlets are:

User Authentication
HTML Hidden Field
Cookies
URL Rewriting
Session Management API

SessionManagement - Java Interview Questions - Edureka
In case you are facing any challenges with these java interview questions, please comment your problems in the section below. Apart from this Java Interview Questions Blog, if you want to get trained from professionals on this technology, you can opt for a structured training from edureka! Click below to know more.

JDBC Interview Questions 
1. What is JDBC Driver?
JDBC Driver is a software component that enables java application to interact with the database. There are 4 types of JDBC drivers:

JDBC-ODBC bridge driver
Native-API driver (partially java driver)
Network Protocol driver (fully java driver)
Thin driver (fully java driver)
2. What are the steps to connect to a database in java?
Registering the driver class
Creating connection
Creating statement
Executing queries
Closing connection
3. What are the JDBC API components?
The java.sql package contains interfaces and classes for JDBC API.

Interfaces:
Connection
Statement
PreparedStatement
ResultSet
ResultSetMetaData
DatabaseMetaData
CallableStatement etc.
Classes:
DriverManager
Blob
Clob
Types
SQLException etc.
4. What is the role of JDBC DriverManager class?
The DriverManager class manages the registered drivers. It can be used to register and unregister drivers. It provides factory method that returns the instance of Connection.

5. What is JDBC Connection interface?
The Connection interface maintains a session with the database. It can be used for transaction management. It provides factory methods that returns the instance of Statement, PreparedStatement, CallableStatement and DatabaseMetaData.

ConnectionInterface - Java Interview Questions - Edureka
6.  What is the purpose of JDBC ResultSet interface?
The ResultSet object represents a row of a table. It can be used to change the cursor pointer and get the information from the database.

7. What is JDBC ResultSetMetaData interface?
The ResultSetMetaData interface returns the information of table such as total number of columns, column name, column type etc.

8. What is JDBC DatabaseMetaData interface?
The DatabaseMetaData interface returns the information of the database such as username, driver name, driver version, number of tables, number of views etc.

9. What do you mean by batch processing in JDBC?
Batch processing helps you to group related SQL statements into a batch and execute them instead of executing a single query. By using batch processing technique in JDBC, you can execute multiple queries which makes the performance faster.

10. What is the difference between execute, executeQuery, executeUpdate?
Statement execute(String query) is used to execute any SQL query and it returns TRUE if the result is an ResultSet such as running Select queries. The output is FALSE when there is no ResultSet object such as running Insert or Update queries. We can use getResultSet() to get the ResultSet and getUpdateCount() method to retrieve the update count.

Statement executeQuery(String query) is used to execute Select queries and returns the ResultSet. ResultSet returned is never null even if there are no records matching the query. When executing select queries we should use executeQuery method so that if someone tries to execute insert/update statement it will throw java.sql.SQLException with message “executeQuery method can not be used for update”.

Statement executeUpdate(String query) is used to execute Insert/Update/Delete (DML) statements or DDL statements that returns nothing. The output is int and equals to the row count for SQL Data Manipulation Language (DML) statements. For DDL statements, the output is 0.

You should use execute() method only when you are not sure about the type of statement else use executeQuery or executeUpdate method.

Q11. What do you understand by JDBC Statements?
JDBC statements are basically the statements which are used to send SQL commands to the database and retrieve data back from the database. Various methods like execute(), executeUpdate(), executeQuery, etc. are provided by JDBC to interact with the database.

JDBC supports 3 types of statements:

Statement: Used for general purpose access to the database and executes a static SQL query at runtime.
PreparedStatement: Used to provide input parameters to the query during execution.
CallableStatement: Used to access the database stored procedures and helps in accepting runtime parameters.
In case you are facing any challenges with these java interview questions, please comment your problems in the section below. Apart from this Java Interview Questions Blog, if you want to get trained from professionals on this technology, you can opt for a structured training from edureka!

Spring Interview Questions 
Q1. What is Spring?
Wikipedia defines the Spring framework as “an application framework and inversion of control container for the Java platform. The framework’s core features can be used by any Java application, but there are extensions for building web applications on top of the Java EE platform.” Spring is essentially a lightweight, integrated framework that can be used for developing enterprise applications in java.

Q2. Name the different modules of the Spring framework.
Some of the important Spring Framework modules are:

Spring Context – for dependency injection.
Spring AOP – for aspect oriented programming.
Spring DAO – for database operations using DAO pattern
Spring JDBC – for JDBC and DataSource support.
Spring ORM – for ORM tools support such as Hibernate
Spring Web Module – for creating web applications.
Spring MVC – Model-View-Controller implementation for creating web applications, web services etc.
SpringFramework - Java Interview Questions - EdurekaQ3. List some of the important annotations in annotation-based Spring configuration.
The important annotations are:

@Required
@Autowired
@Qualifier
@Resource
@PostConstruct
@PreDestroy
Q4. Explain Bean in Spring and List the different Scopes of Spring bean.
Beans are objects that form the backbone of a Spring application. They are managed by the Spring IoC container. In other words, a bean is an object that is instantiated, assembled, and managed by a Spring IoC container.

There are five Scopes defined in Spring beans.

SpringBean - Java Interview Questions - Edureka

Singleton: Only one instance of the bean will be created for each container. This is the default scope for the spring beans. While using this scope, make sure spring bean doesn’t have shared instance variables otherwise it might lead to data inconsistency issues because it’s not thread-safe.
Prototype: A new instance will be created every time the bean is requested.
Request: This is same as prototype scope, however it’s meant to be used for web applications. A new instance of the bean will be created for each HTTP request.
Session: A new bean will be created for each HTTP session by the container.
Global-session: This is used to create global session beans for Portlet applications.
Q5. Explain the role of DispatcherServlet and ContextLoaderListener.
DispatcherServlet is basically the front controller in the Spring MVC application as it loads the spring bean configuration file and initializes all the beans that have been configured. If annotations are enabled, it also scans the packages to configure any bean annotated with @Component, @Controller, @Repository or @Service annotations.

DispatcherServlet - Java Interview Questions - EdurekaContextLoaderListener, on the other hand, is the listener to start up and shut down the WebApplicationContext in Spring root. Some of its important functions includes tying up the lifecycle of Application Context to the lifecycle of the ServletContext and automating the creation of ApplicationContext.

ContextLoader - Java Interview Questions - Edureka
Q6. What are the differences between constructor injection and setter injection?
No.	Constructor Injection	Setter Injection
 1)	 No Partial Injection	 Partial Injection
 2)	 Doesn’t override the setter property	 Overrides the constructor property if both are defined.
 3)	Creates a new instance if any modification occurs	Doesn’t create a new instance if you change the property value
 4) 	 Better for too many properties	 Better for a few properties.
Q7. What is autowiring in Spring? What are the autowiring modes?
Autowiring enables the programmer to inject the bean automatically. We don’t need to write explicit injection logic. Let’s see the code to inject bean using dependency injection.

Programming & Frameworks Training
<bean id=“emp” class=“com.javatpoint.Employee” autowire=“byName” />  
The autowiring modes are given below:

No.	Mode	Description
 1)	 no	 this is the default mode, it means autowiring is not enabled.
 2)	 byName	 Injects the bean based on the property name. It uses setter method.
 3)	 byType	 Injects the bean based on the property type. It uses setter method.
 4)	 constructor	 It injects the bean using constructor
Q8. How to handle exceptions in Spring MVC Framework?
Spring MVC Framework provides the following ways to help us achieving robust exception handling.

Controller Based:
We can define exception handler methods in our controller classes. All we need is to annotate these methods with @ExceptionHandler annotation.

Global Exception Handler:
Exception Handling is a cross-cutting concern and Spring provides @ControllerAdvice annotation that we can use with any class to define our global exception handler.

HandlerExceptionResolver implementation: 
For generic exceptions, most of the times we serve static pages. Spring Framework provides HandlerExceptionResolver interface that we can implement to create global exception handler. The reason behind this additional way to define global exception handler is that Spring framework also provides default implementation classes that we can define in our spring bean configuration file to get spring framework exception handling benefits.


Q9. What are some of the important Spring annotations which you have used?
Some of the Spring annotations that I have used in my project are:

@Controller – for controller classes in Spring MVC project.

@RequestMapping – for configuring URI mapping in controller handler methods. This is a very important annotation, so you should go through Spring MVC RequestMapping Annotation Examples

@ResponseBody – for sending Object as response, usually for sending XML or JSON data as response.

@PathVariable – for mapping dynamic values from the URI to handler method arguments.

@Autowired – for autowiring dependencies in spring beans.

@Qualifier – with @Autowired annotation to avoid confusion when multiple instances of bean type is present.

@Service – for service classes.

@Scope – for configuring the scope of the spring bean.

@Configuration, @ComponentScan and @Bean – for java based configurations.

AspectJ annotations for configuring aspects and advices , @Aspect, @Before, @After, @Around, @Pointcut, etc.

Q10. How to integrate Spring and Hibernate Frameworks?
We can use Spring ORM module to integrate Spring and Hibernate frameworks if you are using Hibernate 3+ where SessionFactory provides current session, then you should avoid using HibernateTemplate or HibernateDaoSupport classes and better to use DAO pattern with dependency injection for the integration.

Also, Spring ORM provides support for using Spring declarative transaction management, so you should utilize that rather than going for hibernate boiler-plate code for transaction management. 

Q11. Name the types of transaction management that Spring supports.
Two types of transaction management are supported by Spring. They are:

Programmatic transaction management: In this, the transaction is managed with the help of programming. It provides you extreme flexibility, but it is very difficult to maintain.
Declarative transaction management: In this, transaction management is separated from the business code. Only annotations or XML based configurations are used to manage the transactions.
In case you are facing any challenges with these java interview questions, please comment your problems in the section below. Apart from this Java Interview Questions Blog, if you want to get trained from professionals on this technology, you can opt for structured training from edureka!

Hibernate Interview Questions
1. What is Hibernate Framework?
Object-relational mapping or ORM is the programming technique to map application domain model objects to the relational database tables. Hibernate is Java-based ORM tool that provides a framework for mapping application domain objects to the relational database tables and vice versa.

Hibernate provides a reference implementation of Java Persistence API, that makes it a great choice as ORM tool with benefits of loose coupling. We can use the Hibernate persistence API for CRUD operations. Hibernate framework provide option to map plain old java objects to traditional database tables with the use of JPA annotations as well as XML based configuration.

Similarly, hibernate configurations are flexible and can be done from XML configuration file as well as programmatically.

2. What are the important benefits of using Hibernate Framework?
Some of the important benefits of using hibernate framework are:

Hibernate eliminates all the boiler-plate code that comes with JDBC and takes care of managing resources, so we can focus on business logic.
Hibernate framework provides support for XML as well as JPA annotations, that makes our code implementation independent.
Hibernate provides a powerful query language (HQL) that is similar to SQL. However, HQL is fully object-oriented and understands concepts like inheritance, polymorphism, and association.
Hibernate is an open source project from Red Hat Community and used worldwide. This makes it a better choice than others because learning curve is small and there are tons of online documentation and help is easily available in forums.
Hibernate is easy to integrate with other Java EE frameworks, it’s so popular that Spring Framework provides built-in support for integrating hibernate with Spring applications.
Hibernate supports lazy initialization using proxy objects and perform actual database queries only when it’s required.
Hibernate cache helps us in getting better performance.
For database vendor specific feature, hibernate is suitable because we can also execute native sql queries.
Overall hibernate is the best choice in current market for ORM tool, it contains all the features that you will ever need in an ORM tool.

3. Explain Hibernate architecture.
HibernateArchitecture - Java Interview Questions - Edureka

4. What are the differences between get and load methods?
The differences between get() and load() methods are given below.

No.	get()	load()
 1)	 Returns null if object is not found.	Throws ObjectNotFoundException if an object is not found.
 2)	 get() method always hit the database.	 load() method doesn’t hit the database.
 3)	 It returns a real object, not a proxy.	 It returns a proxy object.
 4)	It should be used if you are not sure about the existence of instance.	It should be used if you are sure that the instance exists.
5. What are the advantages of Hibernate over JDBC?
Some of the important advantages of Hibernate framework over JDBC are:

Hibernate removes a lot of boiler-plate code that comes with JDBC API, the code looks cleaner and readable.
Hibernate supports inheritance, associations, and collections. These features are not present with JDBC API.
Hibernate implicitly provides transaction management, in fact, most of the queries can’t be executed outside transaction. In JDBC API, we need to write code for transaction management using commit and rollback. 
JDBC API throws SQLException that is a checked exception, so we need to write a lot of try-catch block code. Most of the times it’s redundant in every JDBC call and used for transaction management. Hibernate wraps JDBC exceptions and throw JDBCException or HibernateException un-checked exception, so we don’t need to write code to handle it. Hibernate built-in transaction management removes the usage of try-catch blocks.
Hibernate Query Language (HQL) is more object-oriented and close to Java programming language. For JDBC, we need to write native SQL queries.
Hibernate supports caching that is better for performance, JDBC queries are not cached hence performance is low.
Hibernate provides option through which we can create database tables too, for JDBC tables must exist in the database.
Hibernate configuration helps us in using JDBC like connection as well as JNDI DataSource for the connection pool. This is a very important feature in enterprise application and completely missing in JDBC API.
Hibernate supports JPA annotations, so the code is independent of the implementation and easily replaceable with other ORM tools. JDBC code is very tightly coupled with the application.

In case you are facing any challenges with these Java interview questions, please comment on your problems in the section below. Apart from this Java Interview Questions Blog, if you want to get trained from professionals on this technology, you can opt for structured training from edureka!

Java Interview Questions: JSP
1. What are the life-cycle methods for a jsp?
Methods	Description
 public void jspInit()	It is invoked only once, same as init method of servlet.
public void _jspService(ServletRequest request,ServletResponse)throws ServletException,IOException	It is invoked at each request, same as service() method of servlet.
 public void jspDestroy()	It is invoked only once, same as destroy() method of servlet.
2. What are the JSP implicit objects?
JSP provides 9 implicit objects by default. They are as follows:

Object	Type
1) out	 JspWriter
2) request	 HttpServletRequest
3) response	 HttpServletResponse
4) config	 ServletConfig
5) session	 HttpSession
6) application	 ServletContext
7) pageContext	 PageContext
8) page	 Object
9) exception	 Throwable
3. What are the differences between include directive and include action?
include directive	include action
The include directive includes the content at page translation time.	The include action includes the content at request time.
The include directive includes the original content of the page so page size increases at runtime.	The include action doesn’t include the original content rather invokes the include() method of Vendor provided class.
 It’s better for static pages.	 It’s better for dynamic pages.
4. How to disable caching on back button of the browser?
<%
response.setHeader(“Cache-Control”,”no-store”);
response.setHeader(“Pragma”,”no-cache”);
response.setHeader (“Expires”, “0”);                    //prevents caching at the proxy server
%>   

5. What are the different tags provided in JSTL?
There are 5 type of JSTL tags.

core tags
sql tags
xml tags
internationalization tags
functions tags
6. How to disable session in JSP?
<%@ page session=“false” %>   
7.  How to delete a Cookie in a JSP?
The following code explains how to delete a Cookie in a JSP :

1
2
3
4
5
6
7
8
9
10
11
Cookie mycook = new Cookie("name1","value1");
 
response.addCookie(mycook1);
 
Cookie killmycook = new Cookie("mycook1","value1");
 
killmycook . set MaxAge ( 0 );
 
killmycook . set Path ("/");
 
killmycook . addCookie ( killmycook 1 );
8. Explain the jspDestroy() method.
jspDestry() method is invoked from javax.servlet.jsp.JspPage interface whenever a JSP page is about to be destroyed. Servlets destroy methods can be easily overridden to perform cleanup, like when closing a database connection.

9.  How is JSP better than Servlet technology?
JSP is a technology on the server’s side to make content generation simple. They are document-centric, whereas servlets are programs. A Java server page can contain fragments of Java program, which execute and instantiate Java classes. However, they occur inside an HTML template file. It provides the framework for the development of a Web Application.

10. Why should we not configure JSP standard tags in web.xml?

We don’t need to configure JSP standard tags in web.xml because when container loads the web application and find TLD files, it automatically configures them to be used directly in the application JSP pages. We just need to include it in the JSP page using taglib directive.
## Footnotes

1. <a name="footnote-1"></a>Thanks,


## Credits




   