


#include<stdio.h>
#include<limits.h>
#define MAX 100


int findBig(int a, int b)
{
   return((a>b) ? a:b);
}

int FindMaxSum(int arr[], int n)
{
  int in = arr[0];
  int ex = INT_MIN;
  int ex_new;
  int i;

  for (i = 1; i < n; i++)
  {

     ex_new = findBig(in, ex);
     if (ex<0)
       ex = 0;
     in = ex + arr[i];
     ex = ex_new;
  }

   return ((in > ex)? in : ex);
}


int main()
{
  int arr[MAX] ;
  int n,i;

  scanf("%d",&n);
  for( i=0; i<n;i++)
  scanf("%d",&arr[i]);
  printf("%d \n", FindMaxSum(arr, n));

  return 0;
}
