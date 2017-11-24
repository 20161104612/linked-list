#include<stdio.h>
#include<iostream>
using namespace std;

struct student
{
	char name[50];
	char num[12];
	int age;
	struct student *next;
};


int main()
{
	struct student *p,*q,*head;
	char s;
	p=new student;
	q=p;
	head=q;
	strcpy(head->name,"aaaaa");
	strcpy(head->num,"00001");
	head->age=18;
	cout<<"请输入学生数据;"<<endl;
	cin>>head->name; 
	cin>>head->num;
	cin>>head->age;
	while(cout<<"是否循环(y)or(n)",cin>>s,s=='y'&&'Y')
	{
		cout<<"请输入学生数据;"<<endl;
		p=new student;
		q->next=p;
		q=p;
		cin>>p->name;
		cin>>p->num;
		cin>>p->age;
		p->next=NULL;
	}
	p=head;
	while(p!=NULL)
	{
		cout<<p->name<<" "<<p->num<<" "<<p->age<<endl;
		p=p->next;
	}
	p=head;
	do
	{
		q=p->next;
		delete p;
		p=q;
	}while(q);
	return 0;
}
