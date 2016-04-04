# kinghts.java
/*
The program is to find the least number of steps for a knight to move across a field.

The program is to find the least number of steps for a knight to move from the upper left corner of an array to lower right corner. Where the knight refers to the knight in the Chess. The movements of the knights are limited as described by the rules of Chess.
*/

import java.io.*;
class Knights
{
	static BufferedReader br=new BufferedReader(new InputStreamReader(System.in));
	static int a[][],c=0,n;
	public static void main(String arghh[])throws IOException
	{
		System.out.println("Enter the size");
		n=Integer.parseInt(br.readLine());
		a=new int[n][n];
		a[0][0]=1;
		generate(a,0,0);
		System.out.println(c);
	}
	static void generate(int [][]a,int i,int j)throws IOException
	{
		if(i==n-1&&j==n-1)
		c++;
		else
		{
			if(i+2<n&&j+1<n)	//dr
			{
				if(a[i+1][j]!=1&&a[i+2][j]!=1&&a[i+2][j+1]!=1)
				{
					a[i+1][j]=1;
					a[i+2][j]=1;
					a[i+2][j+1]=1;
					generate(a,i+2,j+1);
					a[i+2][j+1]=0;
					a[i+2][j]=0;
					a[i+1][j]=0;
				}
			}
			if(i+2<n&&j-1>=0)	//dl
			{
				if(a[i+1][j]!=1&&a[i+2][j]!=1&&a[i+2][j-1]!=1)
				{
					a[i+1][j]=1;
					a[i+2][j]=1;
					a[i+2][j-1]=1;
					generate(a,i+2,j-1);
					a[i+2][j-1]=0;
					a[i+2][j]=0;
					a[i+1][j]=0;
				}
			}
			if(i-2>=0&&j+1<n)	//ur
			{
				if(a[i-1][j]!=1&&a[i-2][j]!=1&&a[i-2][j+1]!=1)
				{
					a[i-1][j]=1;
					a[i-2][j]=1;
					a[i-2][j+1]=1;
					generate(a,i-2,j+1);
					a[i-2][j+1]=0;
					a[i-2][j]=0;
					a[i-1][j]=0;
				}
			}
			if(i-2>=0&&j-1>=0)	//ul
			{
				if(a[i-1][j]!=1&&a[i-2][j]!=1&&a[i-2][j-1]!=1)
				{
					a[i-1][j]=1;
					a[i-2][j]=1;
					a[i-2][j-1]=1;
					generate(a,i-2,j-1);
					a[i-2][j-1]=0;
					a[i-2][j]=0;
					a[i-1][j]=0;
				}
			}
			if(i+1<n&&j+2<n)	//rd
			{
				if(a[i][j+1]!=1&&a[i][j+2]!=1&&a[i+1][j+2]!=1)
				{
					a[i][j+1]=1;
					a[i][j+2]=1;
					a[i+1][j+2]=1;
					generate(a,i+1,j+2);
					a[i+1][j+2]=0;
					a[i][j+2]=0;
					a[i][j+1]=0;
				}
			}
			if(i-1>=0&&j+2<n)	//ru
			{
				if(a[i][j+1]!=1&&a[i][j+2]!=1&&a[i-1][j+2]!=1)
				{
					a[i][j+1]=1;
					a[i][j+2]=1;
					a[i-1][j+2]=1;
					generate(a,i-1,j+2);
					a[i-1][j+2]=0;
					a[i][j+2]=0;
					a[i][j+1]=0;
				}
			}
			if(i+1<n&&j-2>=0)	//ld
			{
				if(a[i][j-1]!=1&&a[i][j-2]!=1&&a[i+1][j-2]!=1)
				{
					a[i][j-1]=1;
					a[i][j-2]=1;
					a[i+1][j-2]=1;
					generate(a,i+1,j-2);
					a[i+1][j-2]=0;
					a[i][j-2]=0;
					a[i][j-1]=0;
				}
			}
			if(i-1>=0&&j-2>=0)	//lu
			{
				if(a[i][j-1]!=1&&a[i][j-2]!=1&&a[i-1][j-2]!=1)
				{
					a[i][j-1]=1;
					a[i][j-2]=1;
					a[i-1][j-2]=1;
					generate(a,i-1,j-2);
					a[i-1][j-2]=0;
					a[i][j-2]=0;
					a[i][j-1]=0;
				}
			}
		}
	}
}
