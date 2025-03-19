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

