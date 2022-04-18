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
**4.Implement a program using doubly linked list**<br>
#include <iostream><br>
using namespace std;<br>
struct Node<br>
{<br>
   int data;<br>
   struct Node *prev;<br>
   struct Node *next;<br>
};<br>
struct Node* head = NULL;<br>
void insert(int newdata) <br>
{<br>
   struct Node* newnode = (struct Node*) malloc(sizeof(struct Node));<br>
   newnode->data = newdata;<br>
   newnode->prev = NULL;<br>
   newnode->next = head;<br>
   if(head != NULL)<br>
   head->prev = newnode ;<br>
   head = newnode;<br>
}<br>
void display() <br>
{<br>
   struct Node* ptr;<br>
   ptr = head;<br>
   while(ptr != NULL) <br>
   {<br>
      cout<< ptr->data <<" ";<br>
      ptr = ptr->next;<br>
   }<br>
}<br>
int main() <br>
{<br>
   insert(3);<br>
   insert(1);<br>
   insert(7);<br>
   insert(2);<br>
   insert(9);<br>
   cout<<"The doubly linked list is: ";<br>
   display();<br>
   return 0;<br>
}<br>
**Output:-**<br><br>
The doubly linked list is: 9 2 7 1 3<br>
--------------------------------<br>
<br>
<br>
<br>
**5. Write a C++ program for implementing Heap sort technique.**<br>
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
**10.write a program to implement a N-Queens.**
#include <bits/stdc++.h>
#define N 4
using namespace std;

void printSolution(int board[N][N])
{
	for (int i = 0; i < N; i++) {
		for (int j = 0; j < N; j++)
			cout << " " << board[i][j] << " ";
	}
}
bool isSafe(int board[N][N], int row, int col)
{
	int i, j;
	for (i = 0; i < col; i++)
		if (board[row][i])
			return false;
	for (i = row, j = col; i >= 0 && j >= 0; i--, j--)
		if (board[i][j])
			return false;
	for (i = row, j = col; j >= 0 && i < N; i++, j--)
		if (board[i][j])
			return false;

	return true;
}

bool solveNQUtil(int board[N][N], int col)
{
	if (col >= N)
		return true;

	for (int i = 0; i < N; i++) {

		if (isSafe(board, i, col)) {
			board[i][col] = 1;
			if (solveNQUtil(board, col + 1))
				return true;

			board[i][col] = 0;
		}
	}

	return false;
}

bool solveNQ()
{
	int board[N][N] = { { 0, 0, 0, 0 },
						{ 0, 0, 0, 0 },
						{ 0, 0, 0, 0 },
						{ 0, 0, 0, 0 } };

	if (solveNQUtil(board, 0) == false) {
		cout << "Solution does not exist";
		return false;
	}

	printSolution(board);
	return true;
}

int main()
{
	solveNQ();
	return 0;
}
**output:-**
 0  0  1  0  1  0  0  0  0  0  0  1  0  1  0  0
--------------------------------
Process exited after 0.02414 seconds with return value 0
Press any key to continue . . .
	










