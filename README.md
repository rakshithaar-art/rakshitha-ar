Sort a given set of n integer elements using Merge Sort method and compute its time complexity. Run the program for varied values of n> 5000, and record the time taken to sort. Plot a graph of the time taken versus non graph sheet. The elements can be read from a file or can be generated using the random number generator. Demonstrate using Java how the divide-and-conquer method works along with its time complexity analysis: worst case, average case and best case. 

 

package program5;

public class mergesort 

{

	Static void merge(int a[],int low,int high)

	{

		int mid;

		if(low<high)

		{

			mid=(low+high)/2;

			merge(a,low,mid);

			merge(a,mid+1,high);

			simplemerge(a,low,mid,high);

		}

	}



	Static void simplemerge(int a[],int low,int mid,int high)

	{

		int i=low,j=mid+1,k=low,c[]=new int[10000];

		while((i<=mid)&&(j<=high))

		{

			if(a[i]<a[j])

			{

				c[k]=a[i];

				i++;

				k++;

			}

			else

			{

				c[k]=a[j];

				j++;

				k++;

			}

		}

		while(i<=mid)

		{

			c[k]=a[i];

			k++;

			i++;

		}

		while(j<=high)

		{

			c[k]=a[j];

			j++;

			k++;

		}

		for(i=low;i<=high;i++)

		{

			a[i]=c[i];

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



	    System.out.println("Enter the array elements:");

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

	    q.merge(a,0,n-1);

	    long endTime   = System.currentTimeMillis();

	    long totalTime = endTime - startTime;

	    

	    System.out.println("The sorted elements are");

	    for(i=0;i<n;i++)

	    {

	    	System.out.println(a[i]);

	    }

	    System.out.println("total time: "+totalTime + " ms");        

	}

}
