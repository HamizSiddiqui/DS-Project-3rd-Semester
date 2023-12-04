# DS-Project-3rd-Semester
#include <iostream>
#include<windows.h>// for sleep
#include<stdio.h>
#include<conio.h>//getch()
using namespace std;


class node {

public:
	node* left;
	node* right;
	int positions;
	string str;
	node(int p, string s) {
		positions = p;
		str = s;
		left = NULL;
		right = NULL;
	}
};

class node2
{
public:

	int index1;
	int index2;
	string  directions;
	node2* next;

	node2(int i1, int i2) : index1(i1), index2(i2), next(NULL) {}


};

class distancing
{
public:
	node2* head = NULL;

	void insert_distance(int i1, int i2)
	{
		node2* temp = head;

		if (temp == NULL) {
			head = new node2(i1, i2);
		}
		else
		{
			while (temp->next != NULL)
			{
				temp = temp->next;
			}
			node2* newnode = new node2(i1, i2);
			temp->next = newnode;
			newnode->next = NULL;
		}
	}

	node2* display_Indexing()               //ques
	{
		node2* temp = head;
		node2* temp2 = head;

		temp2 = temp2->next;

		head = temp2;
		return temp;

	}


};







class tree1 {

public:
	node* root = NULL;

	tree1(int p, string s) {
		root = new node(p, s);

	}

	node* insert_in_tree(node* temp, int p, string s) {

		if (temp == NULL) {
			temp = new node(p, s);
		}

		if (p < temp->positions) {
			temp->left = insert_in_tree(temp->left, p, s);
		}
		else if (p > temp->positions) {
			temp->right = insert_in_tree(temp->right, p, s);
		}

		return temp;

	}


	void displays(node* temp) {
		if (temp != NULL) {
			cout << temp->str << endl;
			displays(temp->left);
			displays(temp->right);
		}
	}

};

void load() {
	int i, j;
	int a = 177, b = 219; // 176,175
	printf("\t\t\t\t         ");
	for (j = 0; j < 25; j++)
		printf("%c", a);
	printf("]\r");
	printf("\t\t\t\tLoading [");
	for (i = 0; i < 25; i++) {
		Sleep(100);
		printf("%c", b);
	}
	printf("]\n\n");
}


void directions(int i1, int i2) {


	/*if (i1 < 0 && i2 < 0) {

	}
	else if (i1 > 0 && i2 > 0) {

	}
	else {*/


	if (i1 == 0) {

	}
	else if (i1 > 0) {
		cout << "Move RIGHT  ";
	}
	else {
		cout << "Move LEFT  ";
	}


	if (i2 == 0) {

	}
	else if (i2 > 0) {
		cout << "Move FORWARD  ";
	}
	else {
		cout << "Move BACKWARD  ";
	}
	cout << endl;




	//}
}


int main()
{

	int checking = 0;
	while (checking != 1) {

		/*cout << endl;
		cout << "\t\t\t\t===============================================\n\n";
		cout << "\t\t\t\t\t    FAST GEOSPATIAL INDEXING\n\n";
		cout << "\t\t\t\t===============================================";

		cout << "\n\n\n\n";
		cout << "\t\t\t\t\t    M.Hamiz Siddiqui  22k5055\n\n";
		cout << "\t\t\t\t\t    Zuhair Zeeshan    22k5062\n\n";

		int check = 0;


		//login
		string id;
		cout << "\n Enter Your Roll No = ";
		cin >> id;

		cout << endl;

		while (check != 1) {



			char l1, l2, l3;

			l1 = id[0];// 2
			l2 = id[1]; //0,1,2,3
			l3 = id[2];

			if ((l1 == '2') && (l2 >= '0' && l2 <= '3') && (l3 == 'k' || l3 == 'K'))
			{

				check = 1;

			}
			else
			{
				system("cls");
				cout << "Enter Your Roll No Again = \n";
				cin >> id;
			}

			system("cls");

		}


		//load();
		cout << "\n\t\t\t\t /-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-\n\n\n";
		cout << "\t\t\t\t\t      WELCOME TO FAST MAP\n";
		cout << "\n\n\t\t\t\t /-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-\n";

		*/
		int ch1, ch2;


		tree1 obj(10, " ");
		obj.insert_in_tree(obj.root, 1, "\t\t\t\t\t\tCURRENT LOCATION");
		obj.insert_in_tree(obj.root, 2, "\t\t\t\t\t\t================\n\n");

		obj.insert_in_tree(obj.root, 3, "-> Uni Front Gate (Press 1)");
		obj.insert_in_tree(obj.root, 4, "-> Uni Back Gate (Press 2)");
		obj.insert_in_tree(obj.root, 5, "-> CS Front Gate (Press 3)");
		obj.insert_in_tree(obj.root, 6, "-> CS Back Gate (Press 4)");
		obj.insert_in_tree(obj.root, 7, "-> EE Front Gate (Press 5)");
		obj.insert_in_tree(obj.root, 8, "-> Multi-Purpose Front Gate (Press 6)");
		obj.insert_in_tree(obj.root, 9, "-> Sports Room (Press 7)");

		obj.displays(obj.root);
		cout << "\n\nEnter Your Current Position = ";
		cin >> ch1;

		system("cls");


		tree1 obj1(20, "\t\t\t\t\t\tDESTINATION LOCATION");
		obj1.insert_in_tree(obj1.root, 19, "\t\t\t\t\t\t====================\n\n");

		obj1.insert_in_tree(obj1.root, 18, "-> Shawarma Point (Press 1)");
		obj1.insert_in_tree(obj1.root, 17, "-> Imtiaz`s Photocopy (Press 2)");
		obj1.insert_in_tree(obj1.root, 16, "-> Pizza Fast (Press 3)");
		obj1.insert_in_tree(obj1.root, 15, "-> Basketball Ground (Press 4)");
		obj1.insert_in_tree(obj1.root, 14, "-> Badminton Court (Press 5)");
		obj1.insert_in_tree(obj1.root, 13, "-> Futsall Court (Press 6)");
		obj1.insert_in_tree(obj1.root, 12, "-> Sports Room (Press 7)");
		obj1.insert_in_tree(obj1.root, 11, "-> Dhaba (Press 8)");

		obj1.displays(obj1.root);
		cout << "\n\nEnter Your Destination Position = ";
		cin >> ch2;

		system("cls");


		node2* temp;
		int n, t1, t2;
		char j;
		distancing obj2;

		if (ch1 == 1) {//front gate


			if (ch2 == 1)
			{

				obj2.insert_distance(0, 40);
				obj2.insert_distance(5, 0);
				n = 2;

			}
			else if (ch2 == 2)
			{
				obj2.insert_distance(0, 40);
				obj2.insert_distance(10, 0);
				n = 2;

			}
			else if (ch2 == 3)
			{
				obj2.insert_distance(0, 40);
				obj2.insert_distance(15, 0);
				n = 2;
			}
			else if (ch2 == 4)
			{
				obj2.insert_distance(0, 10);
				obj2.insert_distance(-15, 0);
				n = 2;
			}
			else if (ch2 == 5)
			{
				obj2.insert_distance(0, 10);
				obj2.insert_distance(-50, 0);
				n = 2;
			}
			else if (ch2 == 6)
			{
				obj2.insert_distance(0, 10);
				obj2.insert_distance(-20, 0);
				obj2.insert_distance(-15, 15);
				n = 3;
			}
			else if (ch2 == 7)
			{
				obj2.insert_distance(0, 10);
				obj2.insert_distance(-20, 0);
				obj2.insert_distance(-15, 15);
				obj2.insert_distance(0, 5);
				n = 4;
			}
			else if (ch2 == 8)
			{
				obj2.insert_distance(0, 40);
				obj2.insert_distance(-40, 0);
				n = 4;
			}



		}
		else if (ch1 == 2) {//back gate

			if (ch2 == 1)
			{
				obj2.insert_distance(-5, 0);
				n = 1;
			}
			else if (ch2 == 2)
			{
				obj2.insert_distance(-10, 0);
				n = 1;
			}
			else if (ch2 == 3)
			{
				obj2.insert_distance(-15, 0);
				n = 1;
			}
			else if (ch2 == 4)
			{
				obj2.insert_distance(0, 40);
				obj2.insert_distance(15, 0);
				n = 2;
			}
			else if (ch2 == 5)
			{
				obj2.insert_distance(0, 40);
				obj2.insert_distance(50, 0);
				n = 2;
			}
			else if (ch2 == 6)
			{
				obj2.insert_distance(40, 0);
				obj2.insert_distance(0, -5);
				obj2.insert_distance(10, 0);
				obj2.insert_distance(0, 5);
				n = 4;
			}
			else if (ch2 == 7)
			{
				obj2.insert_distance(40, 0);
				obj2.insert_distance(0, -5);
				obj2.insert_distance(10, 0);
				n = 3;
			}
			else if (ch2 == 8)
			{
				obj2.insert_distance(40, 0);
				n = 1;
			}



		}
		else if (ch1 == 3) {//CS front gate


			if (ch2 == 1)
			{
				obj2.insert_distance(-10, 0);
				obj2.insert_distance(0, -40);
				obj2.insert_distance(-5, 0);
				n = 3;
			}
			else if (ch2 == 2)
			{
				obj2.insert_distance(-10, 0);
				obj2.insert_distance(0, -40);
				obj2.insert_distance(-15, 0);
				n = 3;
			}
			else if (ch2 == 3)
			{
				obj2.insert_distance(-10, 0);
				obj2.insert_distance(0, -40);
				obj2.insert_distance(-20, 0);
				n = 3;
			}
			else if (ch2 == 4)
			{
				obj2.insert_distance(0, 2);
				n = 1;
			}
			else if (ch2 == 5)
			{
				obj2.insert_distance(15, 0);
				n = 1;
			}
			else if (ch2 == 6)
			{
				obj2.insert_distance(5, 0);
				obj2.insert_distance(15, -15);
				n = 2;
			}
			else if (ch2 == 7)
			{
				obj2.insert_distance(5, 0);
				obj2.insert_distance(15, -15);
				obj2.insert_distance(0, -5);
				n = 3;
			}
			else if (ch2 == 8)
			{
				obj2.insert_distance(5, 0);
				obj2.insert_distance(0, -15);
				n = 3;
			}


		}
		else if (ch1 == 4) {//CS Back gate

			if (ch2 == 1)
			{
				obj2.insert_distance(10, 0);
				obj2.insert_distance(0, 2);
				n = 2;
			}
			else if (ch2 == 2)
			{
				obj2.insert_distance(10, 0);
				obj2.insert_distance(0, 2);
				obj2.insert_distance(10, 0);
				n = 3;
			}
			else if (ch2 == 3)
			{
				obj2.insert_distance(10, 0);
				obj2.insert_distance(0, 2);
				obj2.insert_distance(15, 0);
				n = 3;
			}
			else if (ch2 == 4)
			{
				obj2.insert_distance(0, -10);
				n = 1;
			}
			else if (ch2 == 5)
			{
				obj2.insert_distance(0, -10);
				obj2.insert_distance(-30, 0);
				n = 2;
			}
			else if (ch2 == 6)
			{
				obj2.insert_distance(0, -10);
				obj2.insert_distance(-30, 0);
				n = 2;
			}
			else if (ch2 == 7)
			{
				obj2.insert_distance(-10, 0);
				obj2.insert_distance(0, 5);
				obj2.insert_distance(-10, 0);
				n = 3;
			}
			else if (ch2 == 8)
			{
				obj2.insert_distance(-5, 0);
				n = 1;
			}


		}
		else if (ch1 == 5) {//EE front gate
			if (ch2 == 1)
			{
				obj2.insert_distance(10, 0);
				obj2.insert_distance(0, 10);
				n = 2;
			}
			else if (ch2 == 2)
			{
				obj2.insert_distance(10, 0);
				n = 1;
			}
			else if (ch2 == 3)
			{
				obj2.insert_distance(5, 0);
				n = 1;
			}
			else if (ch2 == 4)
			{
				obj2.insert_distance(0, 10);
				obj2.insert_distance(-5, 0);
				obj2.insert_distance(0, 5);
				n = 3;
			}
			else if (ch2 == 5)
			{
				obj2.insert_distance(0, 10);
				obj2.insert_distance(-5, 0);
				obj2.insert_distance(0, 40);
				n = 3;
			}
			else if (ch2 == 6)
			{
				obj2.insert_distance(0, 10);
				obj2.insert_distance(-5, 0);
				obj2.insert_distance(0, 20);
				obj2.insert_distance(15, 15);
				n = 4;
			}
			else if (ch2 == 7)
			{
				obj2.insert_distance(0, 10);
				obj2.insert_distance(-5, 0);
				obj2.insert_distance(0, 20);
				obj2.insert_distance(15, 15);
				obj2.insert_distance(0, 5);
				n = 5;
			}
			else if (ch2 == 8)
			{
				obj2.insert_distance(0, 10);
				obj2.insert_distance(5, 0);
				obj2.insert_distance(0, 30);
				n = 3;
			}


		}
		else if (ch1 == 6) {//Front Multipurpose
			if (ch2 == 1)
			{
				obj2.insert_distance(-5, 0);
				obj2.insert_distance(0, -5);
				obj2.insert_distance(-40, 0);
				obj2.insert_distance(0, -2);
				n = 4;
			}
			else if (ch2 == 2)
			{
				obj2.insert_distance(-5, 0);
				obj2.insert_distance(0, -5);
				obj2.insert_distance(-40, 0);
				obj2.insert_distance(0, -2);
				obj2.insert_distance(-10, 0);
				n = 5;
			}
			else if (ch2 == 3)
			{
				obj2.insert_distance(-5, 0);
				obj2.insert_distance(0, -5);
				obj2.insert_distance(-40, 0);
				obj2.insert_distance(0, -2);
				obj2.insert_distance(-15, 0);
				n = 5;
			}
			else if (ch2 == 4)
			{
				obj2.insert_distance(-15, 15);
				n = 1;
			}
			else if (ch2 == 5)
			{
				obj2.insert_distance(10, 10);
				n = 1;
			}
			else if (ch2 == 6)
			{
				obj2.insert_distance(5, 0);
				n = 1;
			}
			else if (ch2 == 7)
			{
				obj2.insert_distance(5, 0);
				obj2.insert_distance(0, -5);
				n = 2;
			}
			else if (ch2 == 8)
			{
				obj2.insert_distance(-5, 0);
				obj2.insert_distance(0, -5);
				n = 2;
			}


		}
		else if (ch1 == 7) {//Sports Room gate
			if (ch2 == 1)
			{
				obj2.insert_distance(-2, 0);
				obj2.insert_distance(0, 5);
				obj2.insert_distance(5, 0);
				obj2.insert_distance(0, 40);
				obj2.insert_distance(-2, 0);
				n = 5;
			}
			else if (ch2 == 2)
			{
				obj2.insert_distance(-2, 0);
				obj2.insert_distance(0, 5);
				obj2.insert_distance(5, 0);
				obj2.insert_distance(0, 40);
				obj2.insert_distance(-2, 0);
				obj2.insert_distance(0, 10);
				n = 6;
			}
			else if (ch2 == 3)
			{
				obj2.insert_distance(-2, 0);
				obj2.insert_distance(0, 5);
				obj2.insert_distance(5, 0);
				obj2.insert_distance(0, 40);
				obj2.insert_distance(-2, 0);
				obj2.insert_distance(0, 15);
				n = 6;
			}
			else if (ch2 == 4)
			{
				obj2.insert_distance(10, 0);
				obj2.insert_distance(15, 15);
				n = 2;
			}
			else if (ch2 == 5)
			{
				obj2.insert_distance(15, 0);
				obj2.insert_distance(-2, 0);
				n = 2;
			}
			else if (ch2 == 6)
			{
				obj2.insert_distance(5, 0);
				n = 1;
			}
			else if (ch2 == 7)
			{
				obj2.insert_distance(0, 0);
				n = 1;
			}
			else if (ch2 == 8)
			{
				obj2.insert_distance(-2, 0);
				obj2.insert_distance(0, 10);
				n = 2;
			}


		}





		//printing
		cout << "\t\t\t\tTotal Number of steps Required = " << n << endl << endl;
		for (int i = 0; i < n; i++) {
			char z;
			temp = obj2.display_Indexing();
			cout << "Step [" << i + 1 << "]" << endl;
			cout << "(" << temp->index1 << " , " << temp->index2 << ")" << " m" << endl;
			directions(temp->index1, temp->index2);
			cout << endl;
		}


		cout << endl << endl;

		cout << "\t\t\t\tYOU HAVE ARRIVED AT YOUR DESTINATION!" << endl;

		string cont;
		cout << "\t\t\t\tEnter YES to Continue OR Enter NO to exit" << endl;
		cin >> cont;

		if (cont == "YES" || cont == "yes") {
			checking = 0;
		}
		else {
			checking = 1;
		}

		system("cls");

	}
	//timer for steps



}






