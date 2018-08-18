//c program to print spiral matrix
#include<stdio.h>
main()
{
	int m,i,j,n,a[100][100];
	scanf("%d%d",&m,&n);
	int sri=0,eri=m-1,sci=0,eci=n-1,num=1;
	for(i=0;i<m;i++)
	{
		for(j=0;j<n;j++)
		{
			a[i][j]=0;
		}
	}
	while(num<=m*n)
	{
		for(j=sci;j<=eci&&a[sri][j]==0;j++)
		a[sri][j]=num++;
		for(i=sri+1;i<=eri&&a[i][eci]==0;i++)
		a[i][eci]=num++;
		for(j=eci-1;j>=sci&&a[eri][j]==0;j--)
		a[eri][j]=num++;
		for(i=eri-1;i>=sri-1&&a[i][sci]==0;i--)
		a[i][sci]=num++;
        sri++;eri--;sci++;eci--;
	}
	for(i=0;i<m;i++)
	{
		for(j=0;j<n;j++)
		{
			printf("%d ",a[i][j]);
		}
		printf("\n");
	}
}
