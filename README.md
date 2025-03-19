	Sort a given set of n integer elements using Quick Sort method and compute its time complexity. Run the program for varied values of n> 5000 and record the time taken to sort. Plot a graph of the time taken versus non graph sheet. The elements can be read from a file or can be generated using the random number generator. Demonstrate using Java how the divide-and-conquer method works along with its time complexity analysis: worst case, average case and best case. 



package program4;



import java.util.*;

public class quicksort 

{



	Static public void quick(int a[ ],int low,int high)

	 {

	    int j;

	    if(low<high)

	    {

	    	j=partition(a,low,high);

	    	quick(a,low,j-1);

	    	quick(a,j+1,high);

	    }

	 }



	Static  public int partition(int a[ ],int low,int high)

	{

		int i,j,key,temp;

		key=a[low];

		i=low+1;

		j=high;

		for(;;)

		{

			while((i<high)&&(key>=a[i]))

			{

				i++;

			}

			while((key<a[j])&&(j>=low))

			{

				j--;

			}

			if(i<j)

			{

				temp=a[i];

				a[i]=a[j];

				a[j]=temp;

			}

			else

			{

				temp=a[low];

				a[low]=a[j];

				a[j]=temp;

				return j;

			}

		}

	}
 public static void main(String[] args) 

	{

		

	    Random r = new Random();

	    int a[]=new int[100000],i,n;

	    long start,end;

	

	    Scanner s1=new Scanner(System.in);

	    System.out.println("Enter the number of elements:");

	    n=s1.nextInt();



	    System.out.println("Random elements are:");

	    for(i=0;i<n;i++)

	    {

	    	a[i]=r.nextInt(1000);	

	    }

	       

	    System.out.println("The array elements are:\n");

	    for(i=0;i<n;i++)

	    {

	    	System.out.println(a[i]);

	    }

	

	    long startTime = System.currentTimeMillis();

	    q.quick(a,0,n-1);

	    long endTime   = System.currentTimeMillis();

	    long totalTime = endTime - startTime;



	    System.out.println("\nThe sorted elements are:\n");

	    for(i=0;i<n;i++)

	    {

	    	System.out.println(a[i]);

	    }

	

	    System.out.println("Total Time Taken: "+totalTime+"ms");        

	}

