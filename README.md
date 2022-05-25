**1.Write a c++ program to implement singly linked list.**<br>
#include<iostream><br>
#include<cstdlib><br>
using namespace std;<br>
struct node<br>
{<br>
	int info;<br>
	struct node *next;<br>
} *start;<br>
class single_list<br>
{<br>
	public:<br>
		node* create_node(int);<br>
		void insert_begin();<br>
		void insert_last();<br>
		void insert_pos();<br>
		void delete_begin();<br>
		void delete_last();<br>
		void delete_pos();<br>
		void update_begin();<br>
		void update_last();<br>
		void update_pos();<br>
		void sort();<br>
		void reverse();<br>
		void search();<br>
		void display();<br>
		single_list()<br>
		{<br>
			start=NULL;<br>
		}<br>
};<br>
int main()<br>
{<br>
	int choice;<br>
	single_list s1,s2;<br>
	start=NULL;<br>
	do<br>
	{<br>
		cout<<"__________"<<endl;<br>
		cout<<"Operations on singly linked list"<<endl;<br>
		cout<<"__________"<<endl;<br>
		cout<<"1.Insert at first"<<endl;<br>
		cout<<"2.Insert at last"<<endl;<br>
		cout<<"3.Insert at position"<<endl;<br>
		cout<<"4.Delete at first"<<endl;<br>
		cout<<"5.Delete at last"<<endl;<br>
		cout<<"6.Delete at position"<<endl;<br>
		cout<<"7.Update at first"<<endl;<br>
		cout<<"8.Update at last"<<endl;<br>
		cout<<"9.Update at position"<<endl;<br>
		cout<<"10.Asending order"<<endl;<br>
		cout<<"11.Descending order"<<endl;<br>
		cout<<"12.Search"<<endl;<br>
  cout<<"13.Display"<<endl;<br>
		cout<<"14.Exit"<<endl;<br>
		cout<<"Enter your choice:";<br>
		cin>>choice;<br>
		switch(choice)<br>
		{<br>
			case 1:s1.insert_begin();<br>
			s1.display();<br>
			break;<br>
			case 2:s1.insert_last();<br>
			s1.display();<br>
			break;<br>
			case 3:s1.insert_pos();<br>
			s1.display();<br>
			break;<br>
			case 4:s2.delete_begin();<br>
			s1.display();<br>
			break;<br>
			case 5:s2.delete_last();<br>
			s1.display();<br>
			break;<br>
			case 6:s1.delete_pos(); <br>
			s1.display(); <br>
 			break; <br>
 			case 7:s1.update_begin(); <br>
			s1.display(); <br>
 			break; <br>
 			case 8:s1.update_last(); <br>
 			s1.display(); <br>
 			break; <br>
 			case 9:s1.update_pos(); <br>
 			s1.display(); <br>
			break; <br>
 			case 10:s1.sort(); <br>
 			s1.display(); <br>
 			break; <br>
 			case 11:s1.reverse(); <br>
 			s1.display(); <br>
 			break; <br>
 			case 12:s1.search(); <br>
 			s1.display(); <br>
 			break; <br>
      			case 13:s1.display(); <br>
 			break; <br>
 			case 14:exit(0); <br>
 			break; <br>
 			default:cout<<"Wrong choice...???"<<endl; <br>
 			break; <br>

		}<br>
	}<br>
	while(choice != 14); <br>
} <br>
node *single_list::create_node(int value) <br>
{ <br>
 struct node *temp, *s; <br>
 temp = new(struct node); <br>
 if (temp == NULL) <br>
 { <br>
 cout<<"Memory not allocated"<<endl; <br>
 return 0; <br>
 } <br>
 else <br>
 { <br>
 temp->info = value; <br>
 temp->next = NULL; <br>
 return temp; <br>
 } <br>
} <br>
void single_list::insert_begin() <br>
{ <br>
 int value; <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 struct node *temp, *s; <br>
 temp = create_node(value); <br>
 if (start == NULL) <br>
 { <br>
 start = temp; <br>
 start->next = NULL; <br>
 cout<<temp->info<<" is inserted at first in the empty list"<<endl; <br>
 } <br>
 else <br>
 { <br>
 s = start; <br>
 start = temp; <br>
 start->next = s; <br>
 cout<<temp->info<<" is inserted at first"<<endl; <br>
 } <br>
} <br>
void single_list::insert_last() <br>
{ <br>
 int value; <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 struct node *temp, *s; <br>
 temp = create_node(value); <br>
 if (start == NULL) <br>
 { <br>
 start = temp; <br>
 start->next = NULL; <br>
 cout<<temp->info<<" is inserted at last in the empty list"<<endl; <br>
 } <br>
 else <br>
 { <br>
 s = start; <br>
 while (s->next != NULL) <br>
 { <br>
 s = s->next; <br>
 } <br>
 temp->next = NULL; <br>
 s->next = temp; <br>
 cout<<temp->info<<" is inserted at last"<<endl; <br>
 } <br>
} <br>
void single_list::insert_pos() <br>
{ <br>
 int value, pos, counter = 0, loc = 1; <br>
 struct node *temp, *s, *ptr; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (counter == 0){} <br>
 else <br>
 { <br>
 cout<<"Enter the postion from "<<loc<<" to "<<counter+1<<" : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if(pos == 1) <br>
 { <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 temp = create_node(value); <br>
 start = temp; <br>
 start->next = s; <br>
 cout<<temp->info<<" is inserted at first"<<endl; <br>
 } <br>
 else if (pos > 1 && pos <= counter) <br>
 { <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 temp = create_node(value); <br>
 for (int i = 1; i < pos; i++) <br>
 { <br>
 ptr = s; <br>
 s = s->next; <br>
 } <br>
 ptr->next = temp; <br>
 temp->next = s; <br>
 cout<<temp->info<<" is inserted at position "<<pos<<endl; <br>
 } <br>
 else if (pos == counter+1) <br>
 { <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 temp = create_node(value); <br>
 while (s->next != NULL) <br>
 { <br>
 s = s->next; <br>
 } <br>
 temp->next = NULL; <br>
 s->next = temp; <br>
 cout<<temp->info<<" is inserted at last"<<endl; <br>
 } <br>
 else <br>
 { <br>
 cout<<"Positon out of range...!!!"<<endl; <br>
 } <br>
 } <br>
} <br>
void single_list::delete_begin() <br>
{ <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 struct node *s, *ptr; <br>
 s = start; <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from first"<<endl; <br>
 free(s); <br>
 } <br>
} <br>
void single_list::delete_last() <br>
{ <br>
 int i, counter = 0; <br>
 struct node *s, *ptr; <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 s = start; <br>
 if (counter == 1) <br>
 { <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from last"<<endl; <br>
 free(s); <br>
 } <br>
 else <br>
 { <br>
 for (i = 1;i < counter;i++) <br>
 { <br>
 ptr = s; <br>
 s = s->next; <br>
 } <br>
 ptr->next = s->next; <br>
 cout<<s->info<<" deleted from last"<<endl; <br>
 free(s); <br>
 } <br>
 } <br>
} <br>
void single_list::delete_pos() <br>
{ <br>
 int pos, i, counter = 0, loc = 1; <br>
 struct node *s, *ptr; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (counter == 0){} <br>
 else <br>
 { <br>
 if (counter == 1) <br>
 { <br>
 cout<<"Enter the postion [ SAY "<<loc<<" ] : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from first"<<endl; <br>
 free(s); <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } <br>
 else <br>
 { <br>
 cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from first"<<endl; <br>
 free(s); <br>
 } <br>
 else if (pos > 1 && pos <= counter) <br>
 { <br>
 for (i = 1;i < pos;i++) <br>
 { <br>
 ptr = s; <br>
 s = s->next; <br>
 } <br>
 ptr->next = s->next; <br>
 if(pos == counter) <br>
 {cout<<s->info<<" deleted from last"<<endl; <br>
 free(s);} <br>
 else <br>
 {cout<<s->info<<" deleted from postion "<<pos<<endl; <br>
 free(s);} <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } <br>
 } <br>
} <br>
void single_list::update_begin() <br>
{ <br>
 int value, pos=1, i,counter = 0; <br>
 struct node *s, *ptr; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (counter == 0){} <br>
 else if (pos == 1) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 start->info = value; <br>
 cout<<"Node updated at first position : "<<pos<<" = "<<start->info<<endl; <br>
 } <br>
} <br>
void single_list::update_last() <br>
{ <br>
 int value, pos, i,counter = 0; <br>
 struct node *s, *ptr; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 s=start; <br>
 if (counter == 0){} <br>
 else <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 for (i = 1; i < counter ; i++) <br>
 { <br>
 s = s->next; <br>
 } <br>
 s->info = value; <br>
 cout<<"Node updated at last position : "<<counter<<" = "<<s->info<<endl; <br>
 } <br>
} <br>
void single_list::update_pos() <br>
{ <br>
 int value, pos, i,counter = 0, loc = 1; <br>
 struct node *s, *ptr; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (counter == 0){} <br>
 else <br>
 { <br>
 if (counter == 1) <br>
 { <br>
 cout<<"Enter the postion [ SAY "<<loc<<" ] : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 start->info = value; <br>
 cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl; <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } <br>
 else <br>
 { <br>
 cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 start->info = value; <br>
 cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl; <br>
 } <br>
 else if (pos > 1 && pos <= counter) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 for (i = 1; i < pos ; i++) <br>
 { <br>
 s = s->next; <br>
 } <br>
 s->info = value; <br>
 cout<<"Node updated at position : "<<pos<<" = "<<s->info<<endl; <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } <br>
 } <br>
} <br>
void single_list::sort() <br>
{ <br>
 struct node *ptr, *s; <br>
 int value; <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 ptr = start; <br>
 while (ptr != NULL) <br>
 { <br>
 for (s = ptr->next;s !=NULL;s = s->next) <br>
 { <br>
 if (ptr->info > s->info) <br>
 { <br>
 value = ptr->info; <br>
 ptr->info = s->info; <br>
 s->info = value; <br>
 } <br>
 } <br>
 ptr = ptr->next; <br>
 } <br>
 } <br>
} <br>
void single_list::reverse() <br>
{ <br>
 struct node *ptr, *s; <br>
 int value; <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 ptr = start; <br>
 while (ptr != NULL) <br>
 { <br>
 for (s = ptr->next;s !=NULL;s = s->next) <br>
 { <br>
 if (ptr->info < s->info) <br>
 { <br>
 value = ptr->info; <br>
 ptr->info = s->info; <br>
 s->info = value; <br>
 } <br>
 } <br>
 ptr = ptr->next; <br>
 } <br>
 } <br>
} <br>
void single_list::search() <br>
{ <br>
 int value, loc = 0, pos = 0, counter = 0; <br>
 struct node *s; <br>
 s = start; <br>
 while (s != NULL) <br>
 
 {<br> 
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 cout<<"Enter the value to be searched : "; <br>
 cin>>value; <br>
 struct node *s; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 pos++;<br> 
 if (s->info == value) <br>
 { <br>
 loc++;<br> 
 if(loc == 1) <br>
 cout<<"Element "<<value<<" is found at position "<<pos; <br>
 else if(loc <= counter) <br>
 cout<<" , "<<pos; <br>
 } <br>
 s = s->next; <br>
 } <br>
 cout<<endl; <br>
 if (loc == 0) <br>
 cout<<"Element "<<value<<" not found in the list"<<endl; <br>
 } <br>
} <br>
void single_list::display() <br>
{ <br>
 struct node *temp; <br>
 if (start == NULL) <br>
 cout<<"Linked list is empty...!!!"<<endl; <br>
 else <br>
 { <br>
 cout<<"Linked list contains : "; <br>
 temp = start; <br>
 while (temp != NULL) <br>
 { <br>
 cout<<temp->info<<" "; <br>
 temp = temp->next; <br>
 } <br>
 cout<<endl; <br>
 } <br>
}<br>
  <br>
  **Output:-**<br>
  _________<br>
Operations on singly linked list<br>
__________<br>
1.Insert at first<br>
2.Insert at last<br>
3.Insert at position<br>
4.Delete at first<br>
5.Delete at last<br>
6.Delete at position<br>
7.Update at first<br>
8.Update at last<br>
9.Update at position<br>
10.Asending order<br>
11.Descending order<br>
12.Search<br>
13.Display<br>
14.Exit<br>
Enter your choice:1<br>
Enter the value to be inserted : 10<br>
10 is inserted at first in the empty list<br>
Linked list contains : 10<br>
__________<br>
Operations on singly linked list<br>
__________<br>
1.Insert at first<br>
2.Insert at last<br>
3.Insert at position<br>
4.Delete at first<br>
5.Delete at last<br>
6.Delete at position<br>
7.Update at first<br>
8.Update at last<br>
9.Update at position<br>
10.Asending order<br>
11.Descending order<br>
12.Search<br>
13.Display<br>
14.Exit<br>
Enter your choice:1<br>
Enter the value to be inserted : 30<br>
30 is inserted at first<br>
Linked list contains : 30 10<br>
__________<br>
Operations on singly linked list<br>
__________<br>
1.Insert at first<br>
2.Insert at last<br>
3.Insert at position<br>
4.Delete at first<br>
5.Delete at last<br>
6.Delete at position<br>
7.Update at first<br>
8.Update at last<br>
9.Update at position<br>
10.Asending order<br>
11.Descending order<br>
12.Search<br>
13.Display<br>
14.Exit<br>
Enter your choice:2<br>
Enter the value to be inserted : 40<br>
40 is inserted at last<br>
Linked list contains : 30 10 40<br>
__________<br>
Operations on singly linked list<br>
__________<br>
1.Insert at first<br>
2.Insert at last<br>
3.Insert at position<br>
4.Delete at first<br>
5.Delete at last<br>
6.Delete at position<br>
7.Update at first<br>
8.Update at last<br>
9.Update at position<br>
10.Asending order<br>
11.Descending order<br>
12.Search<br>
13.Display<br>
14.Exit<br>
Enter your choice:3<br>
Enter the postion from 1 to 4 : 2<br>
Enter the value to be inserted : 50<br>
50 is inserted at position 2<br>
Linked list contains : 30 50 10 40<br>
__________<br>
Operations on singly linked list<br>
__________<br>
1.Insert at first<br>
2.Insert at last<br>
3.Insert at position<br>
4.Delete at first<br>
5.Delete at last<br>
6.Delete at position<br>
7.Update at first<br>
8.Update at last<br>
9.Update at position<br>
10.Asending order<br>
11.Descending order<br>
12.Search<br>
13.Display<br>
14.Exit<br>
Enter your choice:7<br>
Enter the new node : 12<br>
Node updated at first position : 1 = 12<br>
Linked list contains : 12 50 10 40<br>
__________<br>
Operations on singly linked list<br>
__________<br>
1.Insert at first<br>
2.Insert at last<br>
3.Insert at position<br>
4.Delete at first<br>
5.Delete at last<br>
6.Delete at position<br>
7.Update at first<br>
8.Update at last<br>
9.Update at position<br>
10.Asending order<br>
11.Descending order<br>
12.Search<br>
13.Display<br>
14.Exit<br>
Enter your choice:5<br>
40 deleted from last<br>
Linked list contains : 12 50 10<br>
__________<br>
Operations on singly linked list<br>
__________<br>
1.Insert at first<br>
2.Insert at last<br>
3.Insert at position<br>
4.Delete at first<br>
5.Delete at last<br>
6.Delete at position<br>
7.Update at first<br>
8.Update at last<br>
9.Update at position<br>
10.Asending order<br>
11.Descending order<br>
12.Search<br>
13.Display<br>
14.Exit<br>
Enter your choice:8<br>
Enter the new node : 33<br>
Node updated at last position : 3 = 33<br>
Linked list contains : 12 50 33<br>
__________<br>
Operations on singly linked list<br>
__________<br>
1.Insert at first<br>
2.Insert at last<br>
3.Insert at position<br>
4.Delete at first<br>
5.Delete at last<br>
6.Delete at position<br>
7.Update at first<br>
8.Update at last<br>
9.Update at position<br>
10.Asending order<br>
11.Descending order<br>
12.Search<br>
13.Display<br>
14.Exit<br>
Enter your choice:9<br>
Enter the postion from 1 to 3 : 2<br>
Enter the new node : 55<br>
Node updated at position : 2 = 55<br>
Linked list contains : 12 55 33<br>
__________<br>
Operations on singly linked list<br>
__________<br>
1.Insert at first<br>
2.Insert at last<br>
3.Insert at position<br>
4.Delete at first<br>
5.Delete at last<br>
6.Delete at position<br>
7.Update at first<br>
8.Update at last<br>
9.Update at position<br>
10.Asending order<br>
11.Descending order<br>
12.Search<br>
13.Display<br>
14.Exit<br>
Enter your choice:10<br>
Linked list contains : 12 33 55<br>
__________<br>
Operations on singly linked list<br>
__________<br>
1.Insert at first<br>
2.Insert at last<br>
3.Insert at position<br>
4.Delete at first<br>
5.Delete at last<br>
6.Delete at position<br>
7.Update at first<br>
8.Update at last<br>
9.Update at position<br>
10.Asending order<br>
11.Descending order<br>
12.Search<br>
13.Display<br>
14.Exit<br>
Enter your choice:11<br>
Linked list contains : 55 33 12<br>
__________<br>
Operations on singly linked list<br>
__________<br>
1.Insert at first<br>
2.Insert at last<br>
3.Insert at position<br>
4.Delete at first<br>
5.Delete at last<br>
6.Delete at position<br>
7.Update at first<br>
8.Update at last<br>
9.Update at position<br>
10.Asending order<br>
11.Descending order<br>
12.Search<br>
13.Display<br>
14.Exit<br>
Enter your choice:12<br>
Enter the value to be searched : 30<br>
<br>
Element 30 not found in the list<br>
Linked list contains : 55 33 12<br>
__________<br>
Operations on singly linked list<br>
__________<br>
1.Insert at first<br>
2.Insert at last<br>
3.Insert at position<br>
4.Delete at first<br>
5.Delete at last<br>
6.Delete at position<br>
7.Update at first<br>
8.Update at last<br>
9.Update at position<br>
10.Asending order<br>
11.Descending order<br>
12.Search<br>
13.Display<br>
14.Exit<br>
Enter your choice:12<br>
Enter the value to be searched : 55<br>
Element 55 is found at position 1<br>
Linked list contains : 55 33 12<br>
__________<br>
Operations on singly linked list<br>
__________<br>
1.Insert at first<br>
2.Insert at last<br>
3.Insert at position<br>
4.Delete at first<br>
5.Delete at last<br>
6.Delete at position<br>
7.Update at first<br>
8.Update at last<br>
9.Update at position<br>
10.Asending order<br>
11.Descending order<br>
12.Search<br>
13.Display<br>
14.Exit<br>
Enter your choice:13<br>
Linked list contains : 55 33 12<br>
__________<br>
Operations on singly linked list<br>
__________<br>
1.Insert at first<br>
2.Insert at last<br>
3.Insert at position<br>
4.Delete at first<br>
5.Delete at last<br>
6.Delete at position<br>
7.Update at first<br>
8.Update at last<br>
9.Update at position<br>
10.Asending order<br>
11.Descending order<br>
12.Search<br>
13.Display<br>
14.Exit<br>
Enter your choice:4<br>
55 deleted from first<br>
Linked list contains : 33 12<br>
__________<br>
Operations on singly linked list<br>
__________<br>
1.Insert at first<br>
2.Insert at last<br>
3.Insert at position<br>
4.Delete at first<br>
5.Delete at last<br>
6.Delete at position<br>
7.Update at first<br>
8.Update at last<br>
9.Update at position<br>
10.Asending order<br>
11.Descending order<br>
12.Search<br>
13.Display<br>
14.Exit<br>
Enter your choice:6<br>
Enter the postion from 1 to 2 : 1<br>
33 deleted from first<br>
Linked list contains : 12<br>
__________<br>
Operations on singly linked list<br>
__________<br>
1.Insert at first<br>
2.Insert at last<br>
3.Insert at position<br>
4.Delete at first<br>
5.Delete at last<br>
6.Delete at position<br>
7.Update at first<br>
8.Update at last<br>
9.Update at position<br>
10.Asending order<br>
11.Descending order<br>
12.Search<br>
13.Display<br>
14.Exit<br>
Enter your choice:13<br>
Linked list contains : 12<br>
__________<br>
Operations on singly linked list<br>
__________<br>
1.Insert at first<br>
2.Insert at last<br>
3.Insert at position<br>
4.Delete at first<br>
5.Delete at last<br>
6.Delete at position<br>
7.Update at first<br>
8.Update at last<br>
9.Update at position<br>
10.Asending order<br>
11.Descending order<br>
12.Search<br>
13.Display<br>
14.Exit<br>
Enter your choice:14<br>
--------------------------------<br>
<br>
**2.. Write a C++ program to split the linked list into two halves such that the element ‘e’ should be the first element of second list.**<br>
#include<iostream><br>
using namespace std;<br>
struct Node <br>
{<br>
	int value;<br>
	struct Node *next;<br>
};<br>
struct Node* head=NULL;<br>
struct Node* sHead=NULL;<br>
struct Node* temp=NULL;<br>
void insert(int new_data)<br>
{<br>
	struct Node* new_node = new Node();<br>
	new_node->value = new_data;<br>
	new_node->next = head;<br>
	head = new_node;<br>
}<br>
int n;<br>
int ele;<br>
int splitlndex;<br>
int main()<br>
{<br>
	cout<<"Enter number of elements you want in the list\t";<br>
	cin>>n;<br>
	cout<<"Enter elements:"<<endl;<br>
	for(i=0;i<n;i++)<br>
	{<br>
		cin>>ele;<br>
		insert(ele);<br>
	}<br>
	cout<<"\nList of elements:"<<endl;<br>
	Node *t;<br>
	t=head;<br>
	while(t!=NULL)<br>
	{<br>
		cout<<t->value<<"\t";<br>
		t=t->next;<br>
	}<br>
	cout<<"\n\nEnter the position you want the list to split";<br>
	cin>>splitlndex;<br>
	while(splitlndex<0||splitlndex>n-1)<br>
	{<br>
		cout<<"Invalid position.Try again."<<endl;<br>
		cin>>splitlndex;<br>
	}<br>
	temp = head;<br>
	for(i=0;i<splitlndex;i++)<br>
	{<br>
		if(i==splitlndex-1)<br>
		{<br>
			Node *tN;<br>
			tN=temp->next;<br>
			sHead=tN;<br>
			temp->next=NULL;<br>
			break;<br>
		}<br>
		temp=temp->next;<br>
	}<br>
	temp=head;<br>
	if(temp==NULL)<br>
	{<br>
		cout<<"\n First list is empty"<<endl;<br>
	}<br>
	else<br>
	{<br>
		cout<<"\n\nFirst list element"<<endl;<br>
		while(temp!=NULL)<br>
		{<br>
			cout<<temp->value<<"\t";<br>
			temp=temp->next;<br>
		}<br>
	}<br>
	temp=sHead;<br>
	if(temp==NULL)<br>
	{<br>
		cout<<"\nSecond list is empty"<<endl;<br>
	}<br>
	else<br>
	{<br>
		cout<<"\n\nSecond list elements"<<endl;<br>
		while(temp!=NULL)<br>
		{<br>
			cout<<temp->value<<"\t";<br>
			temp=temp->next;<br>
		}<br>
	}<br>
	return 0;<br>
}<br>
<br>
**Output:-**<br>
Enter number of elements you want in the list   5<br>
Enter elements :<br>
1<br>
2<br>
3<br>
4<br>
5<br>
List of elements :<br>
5       4       3       2       1<br>
Enter the position you want the list to split 6<br>
Invalid position. Try again.<br>
3<br>
First list element<br>
5       4       3<br>
Second list elements<br>
2       1<br>
	<br>
	<br>
**3.Write a program to store k keys into an array of size n at the location compute using a hash function, loc=key%n, where k<=n and  key takes values from [1 to m], m>n. Handle the collision using Linear Probing technique.**<br>
#include<iostream><br>
#include<limits.h><br>
using namespace std;<br>
void Insert(int ary[],int hFn,int Size)<br>
{<br>
	int element ,pos,n=0;<br>
	cout<<"Enter key element to insert\n";<br>
	cin>>element;<br>
	pos=element%hFn;<br>
	while(ary[pos]!=INT_MIN)<br>
	{<br>
		if(ary[pos]==INT_MAX)<br>
		break;<br>
		pos=(pos+1)%hFn;<br>
		n++;<br>
		if(n==Size)<br>
		break;<br>
	}<br>
	if(n==Size)<br>
		cout<<"Hash table was full of element\nNo Place to insert this element\n\n";<br>
	else<br>
		ary[pos]=element;<br>
}<br>
void display(int ary[],int Size)<br>
{<br>
	int i;<br>
	cout<<"Index\tValue\n";<br>
	for(i=0;i<Size;i++)<br>
		cout<<i<<"\t"<<ary[i]<<"\n";<br>
}<br>
int main()<br>
{<br>
	int Size,hFn,i,choice;<br>
	cout<<"Enter size of hash table\n";<br>
	cin>>Size;<br>
	hFn=Size;<br>
	int ary[Size];<br>
	for(i=0;i<Size;i++)<br>
		ary[i]=INT_MIN;<br>
		do<br>
		{<br>
			cout<<"Entwr your choice\n";<br>
			cout<<"1->Insert\n 2->Display\n 0-> Exit\n";<br>
			cin>>choice;<br>
			switch(choice)<br>
			{<br>
			case 1:<br>
			Insert(ary,hFn,Size);<br>
			break;<br>
			case 2:<br>
			display(ary,Size);<br>
			break;<br>
			dfault:<br>
			cout<<"Enter correct choice\n";<br>
			break;<br>
			}<br>
		}<br>
		while(choice);<br>
		return 0;<br>
	}<br>
**Output:-**<br>
Enter size of hash table<br>
5<br>
Entwr your choice<br>
1->Insert<br>
 2->Display<br>
 0-> Exit<br>
1<br>
Enter key element to insert<br>
31<br>
Entwr your choice<br>
1->Insert<br>
 2->Display<br>
 0-> Exit<br>
1<br>
Enter key element to insert<br>
24<br>
Entwr your choice<br>
1->Insert<br>
 2->Display<br>
 0-> Exit<br>
1<br>
Enter key element to insert<br>
20<br>
Entwr your choice<br>
1->Insert<br>
 2->Display<br>
 0-> Exit<br>
1<br>
Enter key element to insert<br>
55<br>
Entwr your choice<br>
1->Insert<br>
 2->Display<br>
 0-> Exit<br>
1<br>
Enter key element to insert<br>
11<br>
Entwr your choice<br>
1->Insert<br>
 2->Display<br>
 0-> Exit<br>
2<br>
Index   Value<br>
0       20<br>
1       31<br>
2       55<br>
3       11<br>
4       24<br>
Entwr your choice<br>
1->Insert<br>
 2->Display<br>
 0-> Exit<br>
<br>
<br>
<br>
**4.Write a C++ program to implement Min Heap.**<br>
#include <iostream>
#include <conio.h>
using namespace std;
void min_heap(int *a, int m, int n){
int j, t;
t= a[m];
j = 2 * m;
while (j <= n) {
if (j < n && a[j+1] < a[j])
j = j + 1;
if (t < a[j])
break;
else if (t >= a[j]) {
a[j/2] = a[j];
j = 2 * j;
}
}
a[j/2] = t;
return;
}
void build_minheap(int *a, int n) 
{
int k;
for(k = n/2; k >= 1; k--) {
min_heap(a,k,n);
}
}
int main() {
int n, i;
cout<<"enter no of elements of array\n";
cin>>n;
int a[30];
for (i = 1; i <= n; i++) {
cout<<"enter element"<<" "<<(i)<<endl;
cin>>a[i];
}
build_minheap(a, n);
cout<<"Min Heap\n";
for (i = 1; i <= n; i++)
 {
cout<<a[i]<<endl;
}
}
**Output:-**
enter no of elements of array
6
enter element 1
3
enter element 2
4
enter element 3
5
enter element 4
8
enter element 5
0
enter element 6
6
Min Heap
0
3
5
8
4
6
**5.Write a C++ program to Sort elements using Max Heap Sort.**<br>
#include <iostream><br>
using namespace std;<br>
void MaxHeapify (int a[], int i, int n)<br>
{<br>
	int j, temp;<br>
	temp = a[i];<br>
	j = 2*i;<br>
	while (j <= n)<br>
	{<br>
		if (j < n && a[j+1] > a[j])<br>
		j = j+1;<br>
		if (temp > a[j])<br>
			break;<br>
		else if (temp <= a[j])<br>
		{<br>
			a[j/2] = a[j];<br>
			j = 2*j;<br>
		}<br>
	}<br>
	a[j/2] = temp;<br>
	return;<br>
}<br>
void HeapSort(int a[], int n)<br>
{<br>
	int i, temp;<br>
	for (i = n; i >= 2; i--)<br>
	{<br>
		temp = a[i];<br>
		a[i] = a[1];<br>
		a[1] = temp;<br>
		MaxHeapify(a, 1, i - 1);<br>
	}<br>
}<br>
void Build_MaxHeap(int a[], int n)<br>
{<br>
	int i;<br>
	for(i = n/2; i >= 1; i--)<br>
		MaxHeapify(a, i, n);<br>
}<br>
int main()<br>
{<br>
int n, i,arr[100];<br>
	cout<<"\nEnter the number of data element to be sorted: ";<br>
	cin>>n;<br>
	n++;<br>
	for(i=1;i<n;i++)<br>
	 {<br>
	 cout<<"Enter element"<<i<<":";<br>
	 cin>>arr[i];<br>
	 }<br>
	Build_MaxHeap(arr, n-1);<br>
	HeapSort(arr, n-1);<br>
	cout<<"\nSorted Data ";<br>
	for (i = 1; i < n; i++)<br>
		cout<<" "<<arr[i];<br>
	return 0;<br>
}<br>
<br>
<br>
**Output:-**<br>
Enter the number of data element to be sorted: 5<br>
Enter element1:81<br>
Enter element2:3<br>
Enter element3:5<br>
Enter element4:19<br>
Enter element5:44<br>

Sorted Data  3 5 19 44 81<br>
--------------------------------<br>
<br>
<br>
<br>
**6.Program to create minimum and maximum heap.**<br>
#include <iostream><br>
#include <conio.h><br>
using namespace std;<br>
void max_heapify(int *a, int i, int n)<br>
{<br>
    int j, temp;<br>
    temp = a[i];<br>
    j = 2 * i;<br>
    while (j <= n)<br>
    {<br>
        if (j < n && a[j+1] > a[j])<br>
            j = j + 1;<br>
        if (temp > a[j])<br>
            break;<br>
        else if (temp <= a[j])<br>
        {<br>
            a[j / 2] = a[j];<br>
            j = 2 * j;<br>
        }<br>
    }<br>
    a[j/2] = temp;<br>
    return;<br>
}<br>
void min_heapify(int *a,int i,int n)<br>
{<br>
    int j, temp;<br>
    temp = a[i];<br>
    j = 2 * i;<br>
    while (j <= n)<br>
    {<br>
        if (j < n && a[j+1] < a[j])<br>
            j = j + 1;<br>
        if (temp < a[j])<br>
            break;<br>
        else if (temp >= a[j])<br>
        {<br>
            a[j/2] = a[j];<br>
            j = 2 * j;<br>
        }<br>
    }<br>
    a[j/2] = temp;<br>
    return;<br>	
}<br>
void build_minheap(int *a, int n)<br>
{ <br>
    int i;<br>
    for(i= n/2; i >= 1; i--)<br>
    {<br>
        min_heapify(a,i,n);<br>
    }<br>
}<br>
void build_maxheap(int *a,int n)<br>
{<br>
    int i;<br>
    for(i = n/2; i >= 1; i--)<br>
    {<br>
        max_heapify(a,i,n);<br>
    }<br>
}<br>
int main()<br>
{<br>
    int n, i, x;<br>
    cout<<"enter no of elements of array\n";<br>
    cin>>n;<br>
    int a[20];<br>
    for (i = 1; i <= n; i++)<br>
    {<br>
        cout<<"enter element"<<(i)<<endl;<br>
        cin>>a[i];<br>
    }<br>
    build_maxheap(a,n);<br>
    {<br>
		cout<<"Max Heap\n";<br>
    	for (i = 1; i <= n; i++)<br>
    	{<br>
        	cout<<a[i]<<endl;<br>
    	}<br>
	}<br>
	build_minheap(a,n);<br>
    {<br>
		cout<<"Min Heap\n";<br>
    	for (i = 1; i <= n; i++)<br>
    	{<br>
        	cout<<a[i]<<endl;<br>
    	}<br>
	}<br>
    getch();<br>
}<br>
<br>
**Output:-**<br>
enter no of elements of array<br>
5<br>
enter element1<br>
32<br>
enter element2<br>
7<br>
enter element3<br>
4<br>
enter element4<br>
89<br>
enter element5<br>
14<br>
Max Heap<br>
89<br>
32<br>
4<br>
7<br>
14<br>
Min Heap<br>
4<br>
7<br>
89<br>
32<br>
14<br>
<br>
<br>
**7. program to create a sum of subset using back tracking**<br>
#include<iostream><br>
using namespace std;<br>
int s[10],d,n,set[10],count=0;<br>
void display(int);<br>
int flag = 0;<br>
int main()<br>
{<br>
	int subset(int,int);<br>
 	int i;<br>
	cout<<"ENTER THE NUMBER OF THE ELEMENTS IN THE SET : ";<br>
 	cin>>n;<br>
 	cout<<"ENTER THE SET OF VALUES : ";<br>
 	for(i=0;i<n;i++)<br>
    	cin>>s[i];<br>
 	cout<<"ENTER THE SUM : ";<br>
 	cin>>d;<br>
 	cout<<"THE PROGRAM OUTPUT IS: ";<br>
 	subset(0 , 0);<br>
 	if(flag == 0)<br>
 	cout<<"There is no solution";<br>
 }<br>
int subset(int sum,int i)<br>
{<br>
	if(sum == d)<br>
	{<br>
 		flag = 1;<br>
 		display(count);<br>
 		return 0;<br>
	}<br>
	if(sum>d || i>=n)<br>
	return 1;<br>
	else<br>
	{<br>
 		set[count]=s[i];<br>
 		count++;<br>
 		subset(sum+s[i],i+1);<br>
 		count--;<br>
 		subset(sum,i+1);<br>
	}<br>
}<br>

void display(int count)<br>
{<br>
 int i;<br>
 cout<<"\t { ";<br>
 for(i=0;i<count;i++)<br>
 cout<<set[i];<br>
 cout<<"}";<br>
}<br>
<br>
**Output:-**<br>
ENTER THE NUMBER OF THE ELEMENTS IN THE SET : 5<br>
ENTER THE SET OF VALUES : 1<br>
4<br>
6<br>
10<br>
9<br>
ENTER THE SUM : 20<br>
THE PROGRAM OUTPUT IS:  {1469}  {1109}  {4610}<br>
--------------------------------<br>
<br>
<br>
**8.Write a program to insertion into an AVL tree and deletion from an AVL tree.**<br>
#include<iostream><br>
#include<cstdio><br>
#include<sstream><br>
#include<algorithm><br>
#define pow2(n) (1 << (n))<br>
using namespace std;<br>
struct avl {<br>
   int d;<br>
   struct avl *l;<br>
   struct avl *r;<br>
}*r;<br>
class avl_tree {<br>
   public:<br>
      int height(avl *);<br>
      int difference(avl *);<br>
      avl *rr_rotat(avl *);<br>
      avl *ll_rotat(avl *);<br>
      avl *lr_rotat(avl*);<br>
      avl *rl_rotat(avl *);<br>
      avl * balance(avl *);<br>
      avl * insert(avl*, int);<br>
      void show(avl*, int);<br>
      void inorder(avl *);<br>
      void preorder(avl *);<br>
      void postorder(avl*);<br>
      avl_tree() {<br>
         r = NULL;<br>
      }<br>
};<br>
int avl_tree::height(avl *t) {<br>
   int h = 0;<br>
   if (t != NULL) {<br>
      int l_height = height(t->l);<br>
      int r_height = height(t->r);<br>
      int max_height = max(l_height, r_height);<br>
      h = max_height + 1;<br>
   }<br>
   return h;<br>
}<br>
int avl_tree::difference(avl *t) {<br>
   int l_height = height(t->l);<br>
   int r_height = height(t->r);<br>
   int b_factor = l_height - r_height;<br>
   return b_factor;<br>
}<br>
avl *avl_tree::rr_rotat(avl *parent) {<br>
   avl *t;<br>
   t = parent->r;<br>
   parent->r = t->l;<br>
   t->l = parent;<br>
   cout<<"Right-Right Rotation";<br>
   return t;<br>
}<br>
avl *avl_tree::ll_rotat(avl *parent) {<br>
   avl *t;<br>
   t = parent->l;<br>
   parent->l = t->r;<br>
   t->r = parent;<br>
   cout<<"Left-Left Rotation";<br>
   return t;<br>
}<br>
avl *avl_tree::lr_rotat(avl *parent) {<br>
   avl *t;<br>
   t = parent->l;<br>
   parent->l = rr_rotat(t);<br>
   cout<<"Left-Right Rotation";<br>
   return ll_rotat(parent);<br>
}<br>
avl *avl_tree::rl_rotat(avl *parent) {<br>
   avl *t;<br>
   t = parent->r;<br>
   parent->r = ll_rotat(t);<br>
   cout<<"Right-Left Rotation";<br>
   return rr_rotat(parent);<br>
}<br>
avl *avl_tree::balance(avl *t) {<br>
   int bal_factor = difference(t);<br>
   if (bal_factor > 1) {<br>
      if (difference(t->l) > 0)<br>
         t = ll_rotat(t);<br>
      else<br>
         t = lr_rotat(t);<br>
   } else if (bal_factor < -1) {<br>
      if (difference(t->r) > 0)<br>
         t = rl_rotat(t);<br>
      else<br>
         t = rr_rotat(t);<br>
   }<br>
   return t;<br>
}<br>
avl *avl_tree::insert(avl *r, int v) {<br>
   if (r == NULL) {<br>
      r = new avl;<br>
      r->d = v;<br>
      r->l = NULL;<br>
      r->r = NULL;<br>
      return r;<br>
   } else if (v< r->d) {<br>
      r->l = insert(r->l, v);<br>
      r = balance(r);<br>
   } else if (v >= r->d) {<br>
      r->r = insert(r->r, v);<br>
      r = balance(r);<br>
   } return r;<br>
}<br>
void avl_tree::show(avl *p, int l) {<br>
   int i;<br>
   if (p != NULL) {<br>
      show(p->r, l+ 1);<br>
      cout<<" ";<br>
      if (p == r)<br>
         cout << "Root -> ";<br>
      for (i = 0; i < l&& p != r; i++)<br>
         cout << " ";<br>
         cout << p->d;<br>
         show(p->l, l + 1);<br>
   }<br>
}<br>
void avl_tree::inorder(avl *t) {<br>
   if (t == NULL)<br>
      return;<br>
      inorder(t->l);<br>
      cout << t->d << " ";<br>
      inorder(t->r);<br>
}<br>
void avl_tree::preorder(avl *t) {<br>
   if (t == NULL)<br>
      return;<br>
      cout << t->d << " ";<br>
      preorder(t->l);<br>
      preorder(t->r);<br>
}<br>
void avl_tree::postorder(avl *t) {<br>
   if (t == NULL)<br>
      return;<br>
      postorder(t ->l);<br>
      postorder(t ->r);<br>
      cout << t->d << " ";<br>
}<br>
int main() {<br>
   int c, i;<br>
   avl_tree avl;<br>
   while (1) {<br>
      cout << "1.Insert Element into the tree" << endl;<br>
      cout << "2.show Balanced AVL Tree" << endl;<br>
      cout << "3.InOrder traversal" << endl;<br>
      cout << "4.PreOrder traversal" << endl;<br>
      cout << "5.PostOrder traversal" << endl;<br>
      cout << "6.Exit" << endl;<br>
      cout << "Enter your Choice: ";<br>
      cin >> c;<br>
      switch (c) {<br>
         case 1:<br>
            cout << "Enter value to be inserted: ";<br>
            cin >> i;<br>
            r = avl.insert(r, i);<br>
         break;<br>
         case 2:<br>
            if (r == NULL) {<br>
               cout << "Tree is Empty" << endl;<br>
               continue;<br>
            }<br>
            cout << "Balanced AVL Tree:" << endl;<br>
            avl.show(r, 1);<br>
            cout<<endl;<br>
         break;<br>
         case 3:<br>
            cout << "Inorder Traversal:" << endl;<br>
            avl.inorder(r);<br>
            cout << endl;<br>
         break;<br>
         case 4:<br>
            cout << "Preorder Traversal:" << endl;<br>
            avl.preorder(r);<br>
            cout << endl;<br>
         break;<br>
         case 5:<br>
            cout << "Postorder Traversal:" << endl;<br>
            avl.postorder(r);<br>
            cout << endl;<br>
         break;<br>
         case 6:<br>
            exit(1);<br>
         break;<br>
         default:<br>
            cout << "Wrong Choice" << endl;<br>
      }<br>
   }<br>
   return 0;<br>
}<br>
**Output:-**<br>
1.Insert Element into the tree<br>
2.show Balanced AVL Tree<br>
3.InOrder traversal<br>
4.PreOrder traversal<br>
5.PostOrder traversal<br>
6.Exit<br>
Enter your Choice: 1<br>
Enter value to be inserted: 2<br>
1.Insert Element into the tree<br>
2.show Balanced AVL Tree<br>
3.InOrder traversal<br>
4.PreOrder traversal<br>
5.PostOrder traversal<br>
6.Exit<br>
Enter your Choice: 1<br>
Enter value to be inserted: 3<br>
1.Insert Element into the tree<br>
2.show Balanced AVL Tree<br>
3.InOrder traversal<br>
4.PreOrder traversal<br>
5.PostOrder traversal<br>
6.Exit<br>
Enter your Choice: 1<br>
Enter value to be inserted: 4<br>
Right-Right Rotation1.Insert Element into the tree<br>
2.show Balanced AVL Tree<br>
3.InOrder traversal<br>
4.PreOrder traversal<br>
5.PostOrder traversal<br>
6.Exit<br>
Enter your Choice: 1<br>
Enter value to be inserted: 5<br>
1.Insert Element into the tree<br>
2.show Balanced AVL Tree<br>
3.InOrder traversal<br>
4.PreOrder traversal<br>
5.PostOrder traversal<br>
6.Exit<br>
Enter your Choice: 1<br>
Enter value to be inserted: 8<br>
Right-Right Rotation1.Insert Element into the tree<br>
2.show Balanced AVL Tree<br>
3.InOrder traversal<br>
4.PreOrder traversal<br>
5.PostOrder traversal<br>
6.Exit<br>
Enter your Choice: 2<br>
Balanced AVL Tree:<br>
    8   5    4 Root -> 3   2<br>
1.Insert Element into the tree<br>
2.show Balanced AVL Tree<br>
3.InOrder traversal<br>
4.PreOrder traversal<br>
5.PostOrder traversal<br>
6.Exit<br>
Enter your Choice: 3<br>
Inorder Traversal:<br>
2 3 4 5 8<br>
1.Insert Element into the tree<br>
2.show Balanced AVL Tree<br>
3.InOrder traversal<br>
4.PreOrder traversal<br>
5.PostOrder traversal<br>
6.Exit<br>
Enter your Choice: 4<br><br>
Preorder Traversal:<br>
3 2 5 4 8<br>
1.Insert Element into the tree<br>
2.show Balanced AVL Tree<br>
3.InOrder traversal<br>
4.PreOrder traversal<br>
5.PostOrder traversal<br>
6.Exit<br>
Enter your Choice: 5<br>
Postorder Traversal:<br>
2 4 8 5 3<br>
1.Insert Element into the tree<br>
2.show Balanced AVL Tree<br>
3.InOrder traversal<br>
4.PreOrder traversal<br>
5.PostOrder traversal<br>
6.Exit<br>
Enter your Choice: 6<br>
--------------------------------<br>
Process exited after 236.7 seconds with return value 1<br>
Press any key to continue . . .<br
<br>
<br>
**9.Merge sort using divide and Conquer array.**<br>
#include <iostream><br>
using namespace std;<br>
void mergeofarrays(int a[], int low, int mid, int high) <br>
{<br>
 int i = low, j = mid + 1, index = low, temp[100], k;<br>
  while ((i <= mid) && (j <= high)) <br>
  {<br>
    if (a[i] < a[j]) <br>
    {<br>
      temp[index] = a[i];<br>
      i++;<br>
    } <br>
    else <br>
    {<br>
      temp[index] = a[j];<br>
      j++;<br>
    }<br>
    index++;<br>
  }<br>
 
  if (i > mid) <br>
  {<br>
    while (j <= high) <br>
    {<br>
      temp[index] = a[j];<br>
      j++;<br>
      index++;<br>
    }<br>
  } <br>
  else <br>
  {<br>
    while (i <= mid) <br>
    {<br>
      temp[index] = a[i];<br>
      i++;<br>
      index++;<br>
    }<br>
  }<br>
  for (k = low; k < index; k++)<br>
  {<br>
    a[k] = temp[k];<br>
  }<br>
}<br>
void mergesort(int a[], int low, int high) <br>
{<br>
  if (low < high) <br>
  {<br>
    int middle = (low + high) / 2; <br>
    mergesort(a, low, middle); <br>
    mergesort(a, middle + 1, high);<br> 
    mergeofarrays(a, low, middle, high); <br>
  }<br>
}<br>
int main() <br>
{<br>
  int n = 7;<br>
  int a[100] = {54,34,23,10,98,2,3};<br>
  mergesort(a, 0, 6);<br>
  for (int i = 0; i < n; i++) <br>
  {<br>
    cout << a[i] << " ";<br>
  }<br>
}<br>
<br>
**Output:-**<br>
2 3 10 23 34 54 98 <br>
<br>
<br>
**10.write a program to implement a N-Queens.**<br>
#include<iostream><br>
using namespace std;<br>
int grid[100][100];<br>
void print(int n) <br>
{<br>
    for (int i = 0;i <= n-1; i++) <br>
	{<br>
        for (int j = 0;j <= n-1; j++) <br>
		{<br>
            
            cout <<grid[i][j]<< " ";<br>
            
        }<br>
        cout<<endl;<br>
    }<br>
    cout<<endl;<br>
    cout<<endl;<br>
}<br>
bool isSafe(int col, int row, int n)<br>
{<br>
  for (int i = 0; i < row; i++)<br> 
    {<br>
        if (grid[i][col]) <br>
		{<br>
            return false;<br>
        }<br>
    }<br>
    for (int i = row,j = col;i >= 0 && j >= 0; i--,j--)<br>  
	{<br>
        if (grid[i][j])<br> 
		{<br>
            return false;<br>
        }<br>
    }<br>
    for (int i = row, j = col; i >= 0 && j < n; j++, i--)<br> 
	{<br>
        if (grid[i][j]) <br>
		{<br>
            return false;<br>
        }<br>
    }<br>
    return true;<br>
}<br>

bool solve (int n, int row)<br> 
{<br>
    if (n == row) <br>
	{<br>
        print(n);<br>
        return true;<br>
    }<br>
     bool res = false;<br>
    for (int i = 0;i <=n-1;i++)<br> 
	{<br>
        if (isSafe(i, row, n))<br> 
		{<br>
            grid[row][i] = 1;<br>
            
            res = solve(n, row+1) || res;<br> 
        	grid[row][i] = 0;<br>
        }<br>
    }<br>
    return res;<br>
}<br>
int main()<br>
{<br>
  	int n;<br>
    cout<<"Enter the number of queen"<<endl;<br>
    cin >> n;<br>
    for (int i = 0;i < n;i++)<br> 
	{<br>
        for (int j = 0;j < n;j++)<br> 
		{<br>
                grid[i][j] = 0;<br>
    	}<br>
    }<br>
    bool res = solve(n, 0);<br>
    if(res == false)<br> 
	{<br>
        cout << "No solution"<< endl;<br> 
    }<br> 
	else <br>
	{<br>
        cout << endl;<br>
    }<br>
  return 0;<br>
}<br>
<br>
**Output:-**<br>
Enter the number of queen 4<br>
0 1 0 0<br>
0 0 0 1<br>
1 0 0 0<br>
0 0 1 0<br>
<br>
0 0 1 0<br>
1 0 0 0<br>
0 0 0 1<br>
0 1 0 0<br>
--------------------------------<br>
<br>
<br>
<br>
**11.program of BFS AND DFS.**<br>
#include<iostream><br>
#include<vector><br>
#include<queue><br>
#include<stack><br>
using namespace std;<br>
void edge(vector<int>adj[],int u,int v){<br>
  adj[u].push_back(v);<br>
}<br>
void bfs(int s,vector<int>adj[],bool visit[]){<br>
  queue<int>q;<br>
  q.push(s);<br>
  visit[s]=true;<br>
  while(!q.empty()){<br>
    int u=q.front();<br>
    cout<<u<<" ";<br>
    q.pop();<br>
    for(int i=0;i<adj[u].size();i++){<br>
      if(!visit[adj[u][i]]){<br>
        q.push(adj[u][i]);<br>
        visit[adj[u][i]]=true;<br>
      }<br>
    }<br>
  }<br>
}<br>
void dfs(int s,vector<int>adj[],bool visit[]){<br>
  stack<int>stk;<br>
  stk.push(s);<br>
  visit[s]=true;<br>
  while(!stk.empty()){<br>
    int u=stk.top();<br>
    cout<<u<<" ";<br>
    stk.pop();<br>
for(int i=0;i<adj[u].size();i++){<br>
      if(!visit[adj[u][i]]){<br>
        stk.push(adj[u][i]);<br>
        visit[adj[u][i]]=true;<br>
      }<br>
    }<br>
  }<br>
}<br>
int main(){<br>
  vector<int>adj[5];<br>
  bool visit[5];<br>
  for(int i=0;i<5;i++){<br>
    visit[i]=false;<br>
  }<br>
  edge(adj,0,2);<br>
  edge(adj,0,1);<br>
  edge(adj,1,3);<br>
  edge(adj,2,0);<br>
  edge(adj,2,3);<br>
  edge(adj,2,4);<br>
  cout<<"BFS traversal is"<<"  ";<br>
  bfs(0,adj,visit);<br>
  cout<<endl;<br>
  for(int i=0;i<5;i++){<br>
    visit[i]=false;<br>
  }<br>
  cout<<"DFS traversal is"<<"  ";<br>
  dfs(0,adj,visit);<br>
}<br>
<br>
**Output:-**<br>
BFS traversal is  0 2 1 3 4<br>
DFS traversal is  0 1 3 2 4<br>
--------------------------------<br>
<br>
<br>
**12.Write a c++ program to implement a binary serach tree.**<br>
# include <iostream> <br>
# include <cstdlib> <br>
using namespace std; <br>
struct node <br>
{ <br>
 int info; <br>
 struct node *left;<br> 
 struct node *right; <br>
}*root; <br>
class BST <br>
{ <br>
 public: <br>
 void find(int, node **, node **); <br>
 void insert(node *, node *); <br>
 void del(int); <br>
 void case_a(node *,node *); <br>
 void case_b(node *,node *); <br>
 void case_c(node *,node *); <br>
 void preorder(node *); <br>
 void inorder(node *); <br>
 void postorder(node *); <br>
 void display(node *, int); <br>
 BST() <br>
 { <br>
 root = NULL; <br>
 } <br>
}; <br>
int main() <br>
{ <br>
 int choice, num; <br>
 BST bst; <br>
 node *temp; <br>
 while (1) <br>
 { <br>
 cout<<"-----------------"<<endl; <br>
 cout<<"Operations on BST"<<endl; <br>
 cout<<"-----------------"<<endl; <br>
 cout<<"1.Insert Element "<<endl; <br>
 cout<<"2.Delete Element "<<endl; <br>
 cout<<"3.Inorder Traversal"<<endl; <br>
 cout<<"4.Preorder Traversal"<<endl; <br>
 cout<<"5.Postorder Traversal"<<endl; <br>
 cout<<"6.Display"<<endl; <br>
 cout<<"7.Quit"<<endl; <br>
 cout<<"Enter your choice : "; <br>
 cin>>choice; <br>
 switch(choice) <br>
 { <br>
 case 1: <br>
 temp = new node; <br>
 cout<<"Enter the number to be inserted : "; <br>
 cin>>temp->info; <br>
 bst.insert(root, temp); <br>
 break; <br>
 case 2: <br>
 if (root == NULL) <br>
 { <br>
 cout<<"Tree is empty, nothing to delete"<<endl; <br>
 continue; <br>
 } <br>
 cout<<"Enter the number to be deleted : "; <br>
 cin>>num; <br>
 bst.del(num); <br>
 break; <br>
 case 3: <br>
 cout<<"Inorder Traversal of BST:"<<endl; <br>
 bst.inorder(root); <br>
 cout<<endl; <br>
 break; <br>
 case 4: <br>
 cout<<"Preorder Traversal of BST:"<<endl; <br>
 bst.preorder(root); <br>
 cout<<endl; <br>
 break; <br>
 case 5: <br>
 cout<<"Postorder Traversal of BST:"<<endl; <br>
 bst.postorder(root); <br>
 cout<<endl; <br>
 break; <br>
 case 6: <br>
 cout<<"Display BST:"<<endl; <br>
 bst.display(root,1); <br>
 cout<<endl; <br>
 break; <br>
 case 7: <br>
 exit(1); <br>
 default: <br>
 cout<<"Wrong choice"<<endl; <br>
 } <br>
 } <br>
} <br>
void BST::find(int item, node **par, node **loc) <br>
{ <br>
 node *ptr, *ptrsave; <br>
 if (root == NULL) <br>
 { <br>
 *loc = NULL; <br>
 *par = NULL; <br>
 return; <br>
 } <br>
 if (item == root->info) <br>
 { <br>
 *loc = root; <br>
 *par = NULL; <br>
 return; <br>
 } <br>
 if (item < root->info) <br>
 ptr = root->left; <br>
 else <br>
 ptr = root->right; <br>
 ptrsave = root; <br>
 while (ptr != NULL) <br>
 { <br>
 if (item == ptr->info) <br>
 { <br>
 *loc = ptr; <br>
 *par = ptrsave; <br>
 return; <br>
 } <br>
 ptrsave = ptr; <br>
 if (item < ptr->info) <br>
 ptr = ptr->left; <br>
 else <br>
 ptr = ptr->right; <br>
 } <br>
 *loc = NULL; <br>
 *par = ptrsave; <br>
} <br>

void BST::insert(node *tree, node *newnode) <br>
{ <br>
 if (root == NULL) <br>
 { <br>
 root = new node; <br>
 root->info = newnode->info; <br>
 root->left = NULL; <br>
 root->right = NULL; <br>
 cout<<"Root Node is Added"<<endl; <br>
 return; <br>
 } <br>
 if (tree->info == newnode->info) <br>
 { <br>
 cout<<"Element already in the tree"<<endl; <br>
 return; <br>
 } <br>
 if (tree->info > newnode->info) <br>
 { <br>
 if (tree->left != NULL) <br>
 { <br>
 insert(tree->left, newnode); <br>
 } <br>
 else <br>
 { <br>
 tree->left = newnode; <br>
 (tree->left)->left = NULL;<br> 
 (tree->left)->right = NULL; <br>
 cout<<"Node Added To Left"<<endl; <br>
 return; <br>
 } <br>
 } <br>
 else <br>
 { <br>
 if (tree->right != NULL) <br>
 { <br>
 insert(tree->right, newnode); <br>
 } <br>
 else <br>
 { <br>
 tree->right = newnode; <br>
 (tree->right)->left = NULL;<br> 
 (tree->right)->right = NULL; <br>
 cout<<"Node Added To Right"<<endl; <br>
 return; <br>
 } <br>
 } <br>
} <br>

void BST::del(int item) <br>
{ <br>
 node *parent, *location; <br>
 if (root == NULL) <br>
 { <br>
 cout<<"Tree empty"<<endl; <br>
 return; <br>
 } <br>
 find(item, &parent, &location); <br>
 if (location == NULL) <br>
 { <br>
 cout<<"Item not present in tree"<<endl; <br>
 return; <br>
 } <br>
 if (location->left == NULL && location->right == NULL) <br>
 case_a(parent, location); <br>
 if (location->left != NULL && location->right == NULL) <br>
 case_b(parent, location); <br>
 if (location->left == NULL && location->right != NULL) <br>
 case_b(parent, location); <br>
 if (location->left != NULL && location->right != NULL) <br>
 case_c(parent, location); <br>
 free(location); <br>
} <br>
 

void BST::case_a(node *par, node *loc ) <br>
{ <br>
 if (par == NULL) <br>
 { <br>
 root = NULL; <br>
 } <br>
 else <br>
 { <br>
 if (loc == par->left) <br>
 par->left = NULL; <br>
 else <br>
 par->right = NULL; <br>
 } <br>
} <br>
 

void BST::case_b(node *par, node *loc) <br>
{ <br>
 node *child; <br>
 if (loc->left != NULL) <br>
 child = loc->left; <br>
 else <br>
 child = loc->right; <br>
 if (par == NULL) <br>
 { <br>
 root = child; <br>
 } <br>
 else <br>
 { <br>
 if (loc == par->left) <br>
 par->left = child; <br>
 else <br>
 par->right = child; <br>
 } <br>
} <br>
 

void BST::case_c(node *par, node *loc) <br>
{ <br>
 node *ptr, *ptrsave, *suc, *parsuc; <br>
 ptrsave = loc; <br>
 ptr = loc->right; <br>
 while (ptr->left != NULL) <br>
 { <br>
 ptrsave = ptr; <br>
 ptr = ptr->left; <br>
 } <br>
 suc = ptr; <br>
 parsuc = ptrsave;<br> 
 if (suc->left == NULL && suc->right == NULL) <br>
 case_a(parsuc, suc); <br>
 else <br>
 case_b(parsuc, suc); <br>
 if (par == NULL) <br>
 { <br>
 root = suc; <br>
 } <br>
 else <br>
 { <br>
 if (loc == par->left) <br>
 par->left = suc; <br>
 else <br>
 par->right = suc; <br>
 } <br>
 suc->left = loc->left; <br>
 suc->right = loc->right; <br>
} <br>
 
 
void BST::preorder(node *ptr) <br>
{ <br>
 if (root == NULL) <br>
 { <br>
 cout<<"Tree is empty"<<endl; <br>
 return; <br>
 } <br>
 if (ptr != NULL) <br>
 { <br>
 cout<<ptr->info<<" "; <br>
 preorder(ptr->left); <br>
 preorder(ptr->right); <br>
 } <br>
} <br>

void BST::inorder(node *ptr) <br>
{ <br>
 if (root == NULL) <br>
 { <br>
 cout<<"Tree is empty"<<endl; <br>
 return; <br>
 } <br>
 if (ptr != NULL) <br>
 { <br>
 inorder(ptr->left); <br>
 cout<<ptr->info<<" "; <br>
 inorder(ptr->right); <br>
 } <br>
} <br>
 
void BST::postorder(node *ptr) <br>
{ <br>
 if (root == NULL) <br>
 { <br>
 cout<<"Tree is empty"<<endl; <br>
 return; <br>
 } <br>
 if (ptr != NULL) <br>
 { <br>
 postorder(ptr->left); <br>
 postorder(ptr->right); <br>
 cout<<ptr->info<<" "; <br>
 } <br>
} <br>
 
void BST::display(node *ptr, int level) <br>
{ <br>
 int i; <br>
 if (ptr != NULL) <br>
 { <br>
 display(ptr->right, level+1); <br>
 cout<<endl; <br>
 if (ptr == root)<br> 
 cout<<"Root->: "; <br>
 else <br>
 { <br>
 for (i = 0;i < level;i++) <br>
 cout<<" "; <br>
 } <br>
 cout<<ptr->info; <br>
 display(ptr->left, level+1); <br>
 } <br>
}<br>
**Output:-**<br>
-----------------<br>
Operations on BST<br>
-----------------<br>
1.Insert Element<br>
2.Delete Element<br>
3.Inorder Traversal<br>
4.Preorder Traversal<br>
5.Postorder Traversal<br>
6.Display<br>
7.Quit<br>
Enter your choice : 1<br>
Enter the number to be inserted : 12<br>
Root Node is Added<br>
-----------------<br>
Operations on BST<br>
-----------------<br>
1.Insert Element<br>
2.Delete Element<br>
3.Inorder Traversal<br>
4.Preorder Traversal<br>
5.Postorder Traversal<br>
6.Display<br>
7.Quit<br>
Enter your choice : 1<br>
Enter the number to be inserted : 30<br>
Node Added To Right<br>
-----------------<br>
Operations on BST<br>
-----------------<br>
1.Insert Element<br>
2.Delete Element<br>
3.Inorder Traversal<br>
4.Preorder Traversal<br>
5.Postorder Traversal<br>
6.Display<br>
7.Quit<br>
Enter your choice : 1<br>
Enter the number to be inserted : 10<br>
Node Added To Left<br>
-----------------<br>
Operations on BST<br>
-----------------<br>
1.Insert Element<br>
2.Delete Element<br>
3.Inorder Traversal<br>
4.Preorder Traversal<br>
5.Postorder Traversal<br>
6.Display<br>
7.Quit<br>
Enter your choice : 1<br>
Enter the number to be inserted : 35<br>
Node Added To Right<br>
-----------------<br>
Operations on BST<br>
-----------------<br>
1.Insert Element<br>
2.Delete Element<br>
3.Inorder Traversal<br>
4.Preorder Traversal<br>
5.Postorder Traversal<br>
6.Display<br>
7.Quit<br>
Enter your choice : 1<br>
Enter the number to be inserted : 20<br>
Node Added To Left<br>
-----------------<br>
Operations on BST<br>
-----------------<br>
1.Insert Element<br>
2.Delete Element<br>
3.Inorder Traversal<br>
4.Preorder Traversal<br>
5.Postorder Traversal<br>
6.Display<br>
7.Quit<br>
Enter your choice : 6<br>
Display BST:<br>

   35<br>
  30<br>
   20<br>
Root->: 12<br>
  10<br>
-----------------<br>
Operations on BST<br>
-----------------<br>
1.Insert Element<br>
2.Delete Element<br>
3.Inorder Traversal<br>
4.Preorder Traversal<br>
5.Postorder Traversal<br>
6.Display<br>
7.Quit<br>
Enter your choice : 3<br>
Inorder Traversal of BST:<br>
10 12 20 30 35<br>
-----------------<br>
Operations on BST<br>
-----------------<br>
1.Insert Element<br>
2.Delete Element<br>
3.Inorder Traversal<br>
4.Preorder Traversal<br>
5.Postorder Traversal<br>
6.Display<br>
7.Quit<br>
Enter your choice : 4<br>
Preorder Traversal of BST:<br>
12 10 30 20 35<br>
-----------------<br>
Operations on BST<br>
-----------------<br>
1.Insert Element<br>
2.Delete Element<br>
3.Inorder Traversal<br>
4.Preorder Traversal<br>
5.Postorder Traversal<br>
6.Display<br>
7.Quit
Enter your choice : 5<br>
Postorder Traversal of BST:<br>
10 20 35 30 12<br>
-----------------<br>
Operations on BST<br>
-----------------<br>
1.Insert Element<br>
2.Delete Element<br>
3.Inorder Traversal<br>
4.Preorder Traversal<br>
5.Postorder Traversal<br>
6.Display<br>
7.Quit<br>
Enter your choice : 2<br>
Enter the number to be deleted : 30<br>
-----------------<br>
Operations on BST<br>
-----------------<br>
	
1.Insert Element<br>
	
2.Delete Element<br>
	
3.Inorder Traversal<br>
	
4.Preorder Traversal<br>
	
5.Postorder Traversal<br>
	
6.Display<br>
	
7.Quit<br>
	
Enter your choice : 6<br>
	
Display BST:<br>
	

  35<br>
	
   20<br>
	
Root->: 12<br>
	
  10<br>
	
-----------------<br>
	
Operations on BST<br>
	
-----------------<br>
	
1.Insert Element<br>
	
2.Delete Element<br>
	
3.Inorder Traversal<br>
	
4.Preorder Traversal<br>
	
5.Postorder Traversal<br>
	
6.Display<br>
	
7.Quit<br>
	
Enter your choice : 7<br>
	

--------------------------------<br>
	<br>
	<br>
<br>
** 13.Write a program to implement a doubly linked list.**<br>
	/*<br>
 * C++ Program to Implement Doubly Linked List <br>
 */
#include<iostream><br>
#include<cstdio><br>
#include<cstdlib><br>
/*<br>
 * Node Declaration<br>
 */<br>
using namespace std;<br>
struct node<br>
{<br>
    int info;<br>
    struct node *next;<br>
    struct node *prev;<br>
}*start;<br>
 <br>
/*<br>
 Class Declaration <br>
 */<br>
class double_llist<br>
{<br>
    public:<br>
        void create_list(int value);<br>
        void add_begin(int value);<br>
        void add_after(int value, int position);<br>
        void delete_element(int value);<br>
        void search_element(int value);<br>
        void display_dlist();<br>
       double_llist()<br>
        {<br>
            start = NULL;  <br>
        }<br>
};<br>
 
/*<br>
 * Main: Conatins Menu<br>
 */<br>
int main()<br>
{<br>
    int choice, element, position;<br>
    double_llist dl;<br>
    while (1)<br>
    {<br>
        cout<<endl<<"----------------------------"<<endl;<br>
        cout<<endl<<"Operations on Doubly linked list"<<endl;<br>
        cout<<endl<<"----------------------------"<<endl; <br>        
        cout<<"1.Create Node"<<endl;<br>
        cout<<"2.Add at begining"<<endl;<br>
        cout<<"3.Add after position"<<endl;<br>
        cout<<"4.Delete"<<endl;<br>
        cout<<"5.Display"<<endl;<br>
        cout<<"6.Quit"<<endl;<br>
        cout<<"Enter your choice : ";<br>
        cin>>choice;<br>
        switch ( choice )<br>
        {<br>
        case 1:<br>
            cout<<"Enter the element: ";<br>
            cin>>element;<br>
            dl.create_list(element);<br>
            cout<<endl;<br>
            break;<br>
        case 2:<br>
            cout<<"Enter the element: ";<br>
            cin>>element;<br>
            dl.add_begin(element);<br>
            cout<<endl;<br>
            break;<br>
        case 3:<br>
            cout<<"Enter the element: ";<br>
            cin>>element;<br>
            cout<<"Insert Element after postion: ";<br>
            cin>>position;<br>
            dl.add_after(element, position);<br>
            cout<<endl;<br>
            break;<br>
        case 4:<br>
            if (start == NULL)<br>
            {<br>                      
                cout<<"List empty,nothing to delete"<<endl; <br>  
                break;<br>
            }<br>
            cout<<"Enter the element for deletion: ";<br>
            cin>>element;<br>
            dl.delete_element(element);<br>
            cout<<endl;<br>
            break;<br>
        case 5:<br>
            dl.display_dlist();<br>
            cout<<endl;<br>
            break;<br>
        case 6:<br>
            exit(1);<br>
        default:<br>
            cout<<"Wrong choice"<<endl;<br>
        }<br>
    }<br>
    return 0;<br>
}<br>
 
/*<br>
 * Create Double Link List<br>
 */<br>
void double_llist::create_list(int value)<br>
{<br>
    struct node *s, *temp;<br>
    temp = new(struct node); <br>
    temp->info = value;<br>
    temp->next = NULL;<br>
    if (start == NULL)<br>
    {<br>
        temp->prev = NULL;<br>
        start = temp;<br>
    }<br>
    else<br>
    {<br>
        s = start;<br>
        while (s->next != NULL)<br>
            s = s->next;<br>
        s->next = temp;<br>
        temp->prev = s;<br>
    }<br>
}<br>
 
/*<br><br>
 * Insertion at the beginning<br><br>
 */<br><br>
void double_llist::add_begin(int value)<br><br>
{<br><br>
    if (start == NULL)<br><br>
    {<br><br>
        cout<<"First Create the list."<<endl;<br><br>
        return;<br><br>
    }<br><br>
    struct node *temp;<br><br>
    temp = new(struct node);<br><br>
    temp->prev = NULL;<br><br>
    temp->info = value;<br><br>
    temp->next = start;<br><br>
    start->prev = temp;<br><br>
    start = temp;<br><br>
    cout<<"Element Inserted"<<endl;<br><br>
}<br><br>
 
/*<br><br>
 * Insertion of element at a particular position<br><br>
 */<br><br>
void double_llist::add_after(int value, int pos)<br><br>
{<br><br>
    if (start == NULL)<br><br>
    {<br><br>
        cout<<"First Create the list."<<endl;<br><br>
        return;<br><br>
    }<br><br>
    struct node *tmp, *q;<br><br>
    int i;<br><br>
    q = start;<br>
    for (i = 0;i < pos - 1;i++)<br><br>
    {<br>
        q = q->next;<br>
        if (q == NULL)<br>
        {<br>
            cout<<"There are less than ";<br>
            cout<<pos<<" elements."<<endl;<br>
            return;<br>
        }<br>
    }<br>
    tmp = new(struct node);<br>
    tmp->info = value;<br>
    if (q->next == NULL)<br>
    {<br>
        q->next = tmp;<br>
        tmp->next = NULL;<br>
        tmp->prev = q;<br>  <br> <br> 
    }<br>
    else<br>
    {<br>
        tmp->next = q->next;<br>
        tmp->next->prev = tmp;<br>
        q->next = tmp;<br>
        tmp->prev = q;<br>
    }<br>
    cout<<"Element Inserted"<<endl;<br>
}<br>
 
/*<br>
 * Deletion of element from the list<br>
 */<br>
void double_llist::delete_element(int value)<br>
{<br>
    struct node *tmp, *q;<br>
     /*first element deletion*/<br>
    if (start->info == value)<br>
    {<br>
        tmp = start;<br>
        start = start->next;  <br>
        start->prev = NULL;<br>
        cout<<"Element Deleted"<<endl;<br>
        free(tmp);<br>
        return;<br>
    }<br>
    q = start;<br>
    while (q->next->next != NULL)<br>
    {   <br>
        /*Element deleted in between*/<br>
        if (q->next->info == value)  <br>
        {<br>
            tmp = q->next;<br>
            q->next = tmp->next;<br>
            tmp->next->prev = q;<br>
            cout<<"Element Deleted"<<endl;<br>
            free(tmp);<br>
            return;<br>
        }<br>
        q = q->next;<br>
    }<br>
     /*last element deleted*/<br>
    if (q->next->info == value) <br>   
    { 	<br>
        tmp = q->next;<br>
        free(tmp);<br>
        q->next = NULL;<br>
        cout<<"Element Deleted"<<endl;<br>
        return;<br>
    }<br>
    cout<<"Element "<<value<<" not found"<<endl;<br>
}<br>
 
/*<br>
 * Display elements of Doubly Link List<br>
 */<br>
void double_llist::display_dlist()<br>
{<br>
    struct node *q;<br>
    if (start == NULL)<br>
    {<br>
        cout<<"List empty,nothing to display"<<endl;<br>
        return;<br>
    }<br>
    q = start;<br>
    cout<<"The Doubly Link List is :"<<endl;<br>
    while (q != NULL)<br>
    {<br>
        cout<<q->info<<br>" <-> ";<br>
        q = q->next;<br>
    }<br>
    cout<<"NULL"<<endl;<br>
}<br>
**Output:-**<br><br>

----------------------------<br><br>

Operations on Doubly linked list<br><br>

----------------------------<br><br>
1.Create Node<br><br>
2.Add at begining<br><br>
3.Add after position<br><br>
4.Delete<br><br>
5.Display<br><br>
6.Quit<br><br>
Enter your choice : 1<br><br>
Enter the element: 10<br><br>


----------------------------<br><br>

Operations on Doubly linked list<br><br>

----------------------------<br><br>
1.Create Node<br><br>
2.Add at begining<br><br>
3.Add after position<br><br>
4.Delete<br><br>
5.Display<br><br>
6.Quit<br><br>
Enter your choice : 1<br><br>
Enter the element: 20<br><br>


----------------------------<br><br>

Operations on Doubly linked list<br>

----------------------------<br>
1.Create Node<br>
2.Add at begining<br>
3.Add after position<br>
4.Delete<br>
5.Display<br>
6.Quit<br>
Enter your choice : 1<br>
Enter the element: 30<br>


----------------------------<br>

Operations on Doubly linked list<br>

----------------------------<br>
1.Create Node<br>
2.Add at begining<br>
3.Add after position<br>
4.Delete<br>
5.Display<br>
6.Quit<br>
Enter your choice : 1<br>
Enter the element: 40<br>


----------------------------<br>

Operations on Doubly linked list<br>

----------------------------<br>
1.Create Node<br>
2.Add at begining<br>
3.Add after position<br>
4.Delete<br>
5.Display<br>
6.Quit<br>
Enter your choice : 1<br>
Enter the element: 50<br>


----------------------------<br>

Operations on Doubly linked list<br>

----------------------------<br>
1.Create Node<br>
2.Add at begining<br>
3.Add after position<br>
4.Delete<br>
5.Display<br>
6.Quit<br>
Enter your choice : 5<br>
The Doubly Link List is :<br>
10 <-> 20 <-> 30 <-> 40 <-> 50 <-> NULL<br>


----------------------------<br>

Operations on Doubly linked list<br>

----------------------------<br>
1.Create Node<br>
2.Add at begining<br>
3.Add after position<br>
4.Delete<br>
5.Display<br>
6.Quit<br>
Enter your choice : 2<br>
Enter the element: 15<br>
Element Inserted<br>


----------------------------<br>

Operations on Doubly linked list<br>

----------------------------<br>
1.Create Node<br>
2.Add at begining<br>
3.Add after position<br>
4.Delete<br>
5.Display<br>
6.Quit<br>
Enter your choice : 5<br>
The Doubly Link List is :<br>
15 <-> 10 <-> 20 <-> 30 <-> 40 <-> 50 <-> NULL<br>


----------------------------<br>

Operations on Doubly linked list<br>

----------------------------<br>
1.Create Node<br>
2.Add at begining<br>
3.Add after position<br>
4.Delete<br>
5.Display<br>
6.Quit<br>
Enter your choice : 3<br>
Enter the element: 40<br>
Insert Element after postion: 3<br>
Element Inserted<br>


----------------------------<br>

Operations on Doubly linked list<br>

----------------------------<br>
1.Create Node<br>
2.Add at begining<br>
3.Add after position<br>
4.Delete<br>
5.Display<br>
6.Quit<br>
Enter your choice : 5<br>
The Doubly Link List is :<br>
15 <-> 10 <-> 20 <-> 40 <-> 30 <-> 40 <-> 50 <-> NULL<br>


----------------------------<br>

Operations on Doubly linked list<br>

----------------------------<br>
1.Create Node<br>
2.Add at begining<br>
3.Add after position<br>
4.Delete<br>
5.Display<br>
6.Quit<br>
Enter your choice : 4<br>
Enter the element for deletion: 30<br>
Element Deleted<br>


----------------------------<br>

Operations on Doubly linked list<br>

----------------------------<br>
1.Create Node<br>
2.Add at begining<br>
3.Add after position<br>
4.Delete<br>
5.Display<br>
6.Quit<br>
Enter your choice : 5<br>
The Doubly Link List is :<br>
15 <-> 10 <-> 20 <-> 40 <-> 40 <-> 50 <-> NULL<br>


----------------------------<br>

Operations on Doubly linked list<br>

----------------------------<br>
1.Create Node<br>
2.Add at begining<br>
3.Add after position<br>
4.Delete<br>
5.Display<br>
6.Quit<br>
Enter your choice : 8<br>
Wrong choice<br>

----------------------------<br>

Operations on Doubly linked list<br>

----------------------------<br>
1.Create Node<br>
2.Add at begining<br>
3.Add after position<br>
4.Delete<br>
5.Display<br>
6.Quit<br>
Enter your choice : 6<br>

--------------------------------<br>
	<br>
	<br>
	<br>
**14.Finding minimum and maximum from given unsorted array by using divide conquer method.**<br>
#include <iostream><br>
using namespace std;<br>
void MinMax(int arr[], int low, int high, int &min, int &max)<br>
{<br>
if (low == high)<br>
{<br>
if (max < arr[low])<br>
	{<br>           // comparison 1
max = arr[low];<br>
}<br>

if (min > arr[high])<br>
	{     <br>     // comparison 2
min = arr[high];<br>
}<br>
return;<br>
}<br>
if (high - low == 1)<br>
{<br>
if (arr[low] < arr[high])<br>
{<br>
if (min > arr[low])<br>
{<br>
min = arr[low];<br>
}<br>
if (max < arr[high])<br>
{<br>
max = arr[high];<br>
}<br>
}<br>
else<br>
{<br>
if (min > arr[high])<br>
{<br>
min = arr[high];<br>
}<br>
if (max < arr[low])<br>
{<br>
max = arr[low];<br>
}<br>
}<br>
return;<br>
}<br>
int mid = (low + high) / 2;<br>
MinMax(arr, low, mid, min, max);<br>
MinMax(arr, mid + 1, high, min, max);<br>
}<br>
int main()<br>
{<br>
int i, n, arr[50];<br>
cout<<"Enter the number of elements : ";<br>
cin>>n;<br>
for( i = 0; i < n; i++ )<br>
{<br>
cout<<"Enter the element : ";<br>
cin>>arr[i];<br>
}<br>
int max = arr[0], min = arr[0];<br>
MinMax(arr, 0, n - 1, min, max);<br>
cout<<"The minimum array element is "<<min<<endl;<br>
cout<<"The maximum array element is "<<max;<br>
}<br>
**Output:-**<br>
Enter the number of elements : 5<br>
Enter the element : 20<br>
Enter the element : 45<br>
Enter the element : 23<br>
Enter the element : 98<br>
Enter the element : 35<br>
The minimum array element is 20<br>
The maximum array element is 98<br>
--------------------------------<br>
<br>	
<br>	
**15.Write a program to implement a tower of Hanoi.**<br>
#include <bits/stdc++.h><br>
using namespace std;<br>
 
void towerOfHanoi(int n, char from_rod,<br>
char to_rod, char aux_rod)<br>
{<br>
    if (n == 0)<br>
    {<br>
        return;<br>
    }<br>
    towerOfHanoi(n - 1, from_rod, aux_rod, to_rod);<br>
    cout << "Move disk " << n << " from rod " << from_rod <<
                                " to rod " << to_rod << endl;<br>
    towerOfHanoi(n - 1, aux_rod, to_rod, from_rod);<br>
}<br>
 

int main()<br>
{<br>
    int n = 4; <br>
    towerOfHanoi(n, 'A', 'C', 'B');<br>
    return 0;<br>
}<br>
**Output:-**<br>
Move disk 1 from rod A to rod B<br>
Move disk 2 from rod A to rod C<br>
Move disk 1 from rod B to rod C<br>
Move disk 3 from rod A to rod B<br>
Move disk 1 from rod C to rod A<br>
Move disk 2 from rod C to rod B<br>
Move disk 1 from rod A to rod B<br>
Move disk 4 from rod A to rod C<br>
Move disk 1 from rod B to rod C<br>
Move disk 2 from rod B to rod A<br>
Move disk 1 from rod C to rod A<br>
Move disk 3 from rod B to rod C<br>
Move disk 1 from rod A to rod B<br>
Move disk 2 from rod A to rod C<br>
Move disk 1 from rod B to rod C<br>

--------------------------------<br>
	<br>
	<br>
	<br>
**16.Write a C++ program to find   MST using Prim’s algorithm..**<br>
#include <bits/stdc++.h><br>
using namespace std;<br>
#define V 5<br>
int minKey(int key[], bool mstSet[])<br>
{<br>
int min = INT_MAX, min_index;<br>
for (int v = 0; v < V; v++)<br>
if (mstSet[v] == false && key[v] < min)<br>
min = key[v], min_index = v;<br>
return min_index;<br>
}<br>
void printMST(int parent[], int graph[V][V])<br>
{<br>
cout<<"Edge \tWeight\n";<br>
for (int i = 1; i < V; i++)<br>
cout<<parent[i]<<" - "<<i<<" \t"<<graph[i][parent[i]]<<" \n";<br>
}<br>

void primMST(int graph[V][V])<br>
{<br>
int parent[V];<br>
int key[V];<br>
bool mstSet[V];<br>
for (int i = 0; i < V; i++)<br>
key[i] = INT_MAX, mstSet[i] = false;<br>
key[0] = 0;<br>
parent[0] = -1; // First node is always root of MST<br>
for (int count = 0; count < V - 1; count++)<br>
{<br>
int u = minKey(key, mstSet);<br>
mstSet[u] = true;<br>
for (int v = 0; v < V; v++)<br>
if (graph[u][v] && mstSet[v] == false && graph[u][v] < key[v])<br>
parent[v] = u, key[v] = graph[u][v];<br>
}<br>
printMST(parent, graph);<br>
}<br>
int main()<br>
{<br>
int graph[V][V] = { { 0, 2, 0, 6, 0 },<br>
{ 2, 0, 3, 8, 5 },<br>
{ 0, 3, 0, 0, 7 },<br>
{ 6, 8, 0, 0, 9 },<br>
{ 0, 5, 7, 9, 0 } };<br>
primMST(graph);<br>
return 0;<br>
}<br>
<br>
<br>
**Output:-**<br>
Edge    Weight<br>
0 - 1   2<br>
1 - 2   3<br>
0 - 3   6<br>
1 - 4   5<br>
--------------------------------<br>
**17.Write a C++ program to find  MST Using  Kruskal’s algorithm.**<br>
#include<bits/stdc++.h><br>
using namespace std;<br>
typedef pair<int, int> iPair;<br>
struct Graph<br>
{<br>
int V, E;<br>
vector< pair<int, iPair> > edges;<br>
Graph(int V, int E)<br>
{<br>
this->V = V;<br>
this->E = E;<br>
}<br>
void addEdge(int u, int v, int w)<br>
{<br>
edges.push_back({w, {u, v}});<br>
}<br>
int kruskalMST();<br>
};<br>

struct DisjointSets<br>
{<br>
int *parent, *rnk;<br>
int n;<br>
DisjointSets(int n)<br>
{<br>
this->n = n;<br>
parent = new int[n+1];<br>
rnk = new int[n+1];<br>
for (int i = 0; i <= n; i++)<br>
{<br>
rnk[i] = 0;<br>
parent[i] = i;<br>
}<br>
}<br>
int find(int u)<br>
{<br>
if (u != parent[u])<br>
parent[u] = find(parent[u]);<br>
return parent[u];<br>
}<br>
void merge(int x, int y)<br>
{<br>
x = find(x), y = find(y);<br>
if (rnk[x] > rnk[y])<br>
parent[y] = x;<br>
else // If rnk[x] <= rnk[y]<br>
parent[x] = y;<br>
if (rnk[x] == rnk[y])<br>
rnk[y]++;<br>
}<br>
};<br>
int Graph::kruskalMST()<br>
{<br>
int mst_wt = 0; <br>
sort(edges.begin(), edges.end());<br>
DisjointSets ds(V);<br>
vector< pair<int, iPair> >::iterator it;<br>
for (it=edges.begin(); it!=edges.end(); it++)<br>
{<br>
int u = it->second.first;<br>
int v = it->second.second;<br>
int set_u = ds.find(u);<br>
int set_v = ds.find(v);<br>
if (set_u != set_v)<br>
{<br>
cout << u << " - " << v << endl;<br>
mst_wt += it->first;<br>
ds.merge(set_u, set_v);<br>
}<br>
}<br>
return mst_wt;<br>
}<br>
int main()<br>
{<br>
int V = 9, E = 14;<br>
Graph g(V, E);<br>
g.addEdge(0, 1, 4);<br>
g.addEdge(0, 7, 8);<br>
g.addEdge(1, 2, 8);<br>
g.addEdge(1, 7, 11);<br>
g.addEdge(2, 3, 7);<br>
g.addEdge(2, 8, 2);<br>
g.addEdge(2, 5, 4);<br>
g.addEdge(3, 4, 9);<br>
g.addEdge(3, 5, 14);<br>
g.addEdge(4, 5, 10);<br>
g.addEdge(5, 6, 2);<br>
g.addEdge(6, 7, 1);<br>
g.addEdge(6, 8, 6);<br>
g.addEdge(7, 8, 7);<br>
cout << "Edges of MST are \n";<br>
int mst_wt = g.kruskalMST();<br>
cout << "\nWeight of MST is " << mst_wt;<br>
return 0;<br>
}<br>
<br>
**Output:-**<br>
Edges of MST are<br>
6 - 7<br>
2 - 8<br>
5 - 6<br>
0 - 1<br>
2 - 5<br>
2 - 3<br>
0 - 7<br>
3 - 4<br>
Weight of MST is 37<br>
--------------------------------<br>
**18.Write a program to count number of connected component in an undirected graph.**<br>
#include <iostream><br>
#include <list><br>
using namespace std;<br>
 
// Graph class represents a undirected graph<br>
// using adjacency list representation<br>
class Graph {<br>
    int V; // No. of vertices<br>
 
    // Pointer to an array containing adjacency lists<br>
    list<int>* adj;<br>
 
    // A function used by DFS<br>
    void DFSUtil(int v, bool visited[]);<br>
 
public:<br>
    Graph(int V); // Constructor<br>
    ~Graph();<br>
    void addEdge(int v, int w);<br>
    void connectedComponents();<br>
};<br>
 
// Method to print connected components in an<br>
// undirected graph<br>
void Graph::connectedComponents()<br>
{<br>
    // Mark all the vertices as not visited<br>
    bool* visited = new bool[V];<br>
    for (int v = 0; v < V; v++)<br>
        visited[v] = false;<br>
 
    for (int v = 0; v < V; v++) {<br>
        if (visited[v] == false) {<br>
            // print all reachable vertices<br>
            // from v<br>
            DFSUtil(v, visited);<br>
 
            cout << "\n";<br>
        }<br>
    }<br>
    delete[] visited;<br>
}<br>
 
void Graph::DFSUtil(int v, bool visited[])<br>
{<br>
    // Mark the current node as visited and print it<br>
    visited[v] = true;<br>
    cout << v << " ";<br>
 
    // Recur for all the vertices<br>
    // adjacent to this vertex<br>
    list<int>::iterator i;<br>
    for (i = adj[v].begin(); i != adj[v].end(); ++i)<br>
        if (!visited[*i])<br>
            DFSUtil(*i, visited);<br>
}<br>
 
Graph::Graph(int V)<br>
{<br>
    this->V = V;<br>
    adj = new list<int>[V];<br>
}<br>
 
Graph::~Graph() { delete[] adj; }<br>
 
// method to add an undirected edge<br>
void Graph::addEdge(int v, int w)<br>
{<br>
    adj[v].push_back(w);<br>
    adj[w].push_back(v);<br>
}<br>
 
// Driver code<br>
int main()<br>
{<br>
    // Create a graph given in the above diagram<br>
    Graph g(5); // 5 vertices numbered from 0 to 4<br>
    g.addEdge(1, 0);<br>
    g.addEdge(2, 3);<br>
    g.addEdge(3, 4);<br>
 
    cout << "Following are connected components \n";<br>
    g.connectedComponents();<br>
 
    return 0;<br>
}<br>
<br><br>
<br><br>
**Output:-**<br>
Following are connected components<br>
0 1<br>
2 3 4<br>
--------------------------------<br>
<br>
<br>
**19.Write a C++ program to Find Hamiltonian circuit for a given graph by using
backtracking.**<br>
#include <iostream><br>
#include <cstdio><br>
#include <cstdlib><br>
#define N 5<br>
using namespace std;<br>
void displaytheSolution(int path[]);<br>
bool isSafe(int n, bool g[N][N], int path[], int pos) {<br>
 if (g [path[pos-1]][n] == 0)<br>
 return false;<br>
 for (int i = 0; i < pos; i++)<br>
 if (path[i] == n)<br>
 return false;<br>
 return true;<br>
}<br>
bool hamiltonianCycle(bool g[N][N], int path[], int pos) {<br>
 if (pos == N) {<br>
 if (g[ path[pos-1] ][ path[0] ] == 1)<br>
 return true;<br>
 else<br>
 return false;<br>
 }<br>
 for (int n = 1; n < N; n++) {<br>
 if (isSafe(n, g, path, pos)) {<br>
 path[pos] = n;<br>

 if (hamiltonianCycle (g, path, pos+1) == true)<br>
return true;<br>
 path[pos] = -1;<br>
 }<br>
 }<br>
 return false;<br>
}<br>
bool hamCycle(bool g[N][N]) {<br>
 int *path = new int[N];<br>
 for (int i = 0; i < N; i++)<br>
 path[i] = -1;<br>

 path[0] = 0;<br>
 if (hamiltonianCycle(g, path, 1) == false) {<br>
 cout<<"\nCycle does not exist"<<endl;<br>
 return false;<br>
 }<br>
 displaytheSolution(path);<br>
 return true;<br>
}<br>
void displaytheSolution(int p[]) {<br>
 cout<<"Cycle Exists:";<br>
 cout<<" Following is one Hamiltonian Cycle \n"<<endl;<br>
 for (int i = 0; i < N; i++)<br>
 cout<<p[i]<<" ";<br>
 cout<< p[0]<<endl;<br>
}<br>
int main() {<br>
 bool g[N][N] = {{0, 1, 0, 1, 1},<br>
 {0, 0, 1, 1, 0},<br>
 {0, 1, 0, 1, 1},<br>
 {1, 1, 1, 0, 1},<br>
 {0, 1, 1, 0, 0},<br>
 };<br>
 hamCycle(g);<br>
 return 0;<br>
}<br>
**Output:-**<br>
Cycle Exists: Following is one Hamiltonian Cycle<br>
0 4 1 2 3 0<br>


	





		 



	














