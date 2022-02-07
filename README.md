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
