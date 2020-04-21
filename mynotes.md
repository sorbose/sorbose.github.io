# lower_bound与upper_bound二分查找
lower_bound传入三个参数，分别是起始地址first,结束地址last（左闭右开区间），待查找元素x，返回第一个大于或等于x的地址
upper_bound传参同lower_bound,返回第一个大于x的地址，头文件#include<algorithm>
例如
'''
#include<stdio.h>
#include<iostream>
#include<string.h>
#include<stdlib.h>
#include<algorithm>
using namespace std;
int cmp(const void* a, const void* b)
{return *(int*)a-*(int*)b;}
int main()
{
	int i,n=10;
	int a[]={999,20,20,70,60,0,90,10,50,40};
	int x=20;
	qsort(a+1,n-1,sizeof(a[0]),cmp);
	for(i=0;i<=n-1;i++)
	{cout<<a[i]<<" ";}
	cout<<endl;
	cout<<lower_bound(a+1,a+n,x)-a<<endl;
	cout<<upper_bound(a+1,a+n,x)-a<<endl;
	return 0;
} 
'''
最后两行输出为3，5（下标）
