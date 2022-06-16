# Housing-Two-Pointer-in-cpp
** Problem Statement**
Along one side of a road there is a sequence of vacant plots of land. Each plot has a different area
(non-zero). So, the areas form a sequence A[1], A[2], ... A[N].

You want to buy K acres of land to build a house. You want to find all segments of continguous plots
(i.e., a subsection in the sequence) of whose sum is exactly K.

**Input format**

1.First line take the size of the array

2.Next line take n size of array

3.Third line take the sum of window

**OUTPUT Format**

Output will be index of array in the range of i,j where window sum is equal to k

**code**
```


#include <bits/stdc++.h>

using namespace std;

void solve(int a[],int n,int k)
{
    int i=0;
    int j=0;
    int c=0;
    while(j<n)
    {
        c+=a[j];
        j++;
        while(c>k &&i<j)
        {
            c-=a[i];
           
        i++;
        }
        if(c==k)
        {
            cout<<i<<" "<<j-1<<endl;
        }
    }
    return;
}
int main()
{
   int n;
    cin>>n;
    int a[n];
    for(int i=0;i<n;i++)
    {
        cin>>a[i];
    }
    int k;
    cin>>k;
    solve(a,n,k);

    return 0;
}
