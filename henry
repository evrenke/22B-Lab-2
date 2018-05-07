/*
	
	Authors: Evren Keskin, and Henry 

	Date:	05/02/2018

	Description: This program will make 
	duplicates of four string methods: strlen, strncpy, strncat, and strncmp
*/

#include <iostream>
#include <string>

using namespace std;

//Selection Methods
int getOperation();
char *getInput(int size);
bool again();
//Lab 02 Methods
int stringLength(const char str[]);
void stringNCopy(char str1[], char str2[], int max);
void stringNAdd(char s1[], char s2[], int copiedInd);
int stringNCompare(char s1[], char s2[], int compInd);

int main() {
	int op;
	int num = 0;
	int num2 = 0;
	char *input1;
	char *input2;
	do {
		op = getOperation();
		//Lab 02 specific methods goes inside switch
		switch (op) {
		case 1:
			cout << "Testing stringLength()" << endl;
			input1 = getInput(25);
			input2 = new char;
			num = stringLength(input1);
			cout << "The size of (" << input1 << ") is " << num << " characters long" << endl;
			break;
		case 2:
			cout << "Testing stringNCopy()" << endl;
			input1 = getInput(25);
			input2 = getInput(25);
			cout << "Please enter an int" << endl;
			cin >> num;
			cout << "The result of StringNCopy using <" << input1 << "> and <" << input2 << "> with the specified length of " << num;
			stringNCopy(input1, input2, num);
			cout << "> is <" << input2 << ">"<< endl;
			break;
		case 3:
			cout << "Testing StringNAdd()" << endl;
			input1 = getInput(25);
			input2 = getInput(25);
			cout << "Please enter an int" << endl;
			cin >> num;
			cout << "The result of StringNAdd using <" << input1 << "> and <" << input2 << "> with the specified length of <" << num;
			stringNAdd(input1, input2, num);
			cout << "> is <" << input1 << ">" << endl;
			break;
		case 4:
			cout << "Testing StringNCompare()" << endl;
			input1 = getInput(25);
			input2 = getInput(25);
			cout << "Please enter an int" << endl;
			cin >> num;
			cout << "Comparing the given strings <" << input1 << "> and <" << input2 << "> up to the given length of <" << num << ">" << endl;
			num2 = stringNCompare(input1, input2, num);
			switch (num2) {
			case -1:
				cout << "<" << input2 << "> is greater" << endl;
				break;
			case 0:
				cout << "The two strings are equal" << endl;
				break;
			case 1:
				cout << "<" << input1 << "> is greater" << endl;
				break;
			}
			break;
		default:
			input1 = new char;
			input2 = new char;
		}
	} while (again());
	delete input1;
	delete input2;
	//system("pause");
	return 0;
}

int getOperation() {
	int op;
	cout << "What would you like to test?" << endl;
	cout << "Enter 1 to test stringLength()" << endl;
	cout << "Enter 2 tp test stringNCopy()" << endl;
	cout << "Enter 3 to test stringNAdd()" << endl;
	cout << "Enter 4 to test stringNCompare()" << endl;
	cin >> op;
	cout << endl;
	return op;
}

char *getInput(int size) {
	cout << "Please enter a String" << endl;
	char *input = new char[size];
	cin >> input;
	return input;
}

bool again() {
	string responce;
	while (true) {
		cout << endl;
		cout << "Would you like to try another method?" << endl;
		cout << "Please respond with yes or no" << endl;
		cin >> responce;
		cout << endl;
		if (!responce.compare("yes"))
			return true;
		else if (!responce.compare("no"))
			return false;
		cout << endl;
		cout << "Error, Invalid input" << endl;
		cout << "Reprompting..." << endl << endl;
	}
}

int stringLength(const char str[]) {
	for (int index = 0;;index++) {
		if (*(str+index) == '\0')
			return index;
	}
}

void stringNCopy(char str1[], char str2[],int max) {
	for (int index = 0; index < max; index++) {
		if (*(str1+index) == '\0')
			break;
		*(str2 + index) = *(str1 + index);
	}
}

void stringNAdd(char s1[], char s2[], int copiedInd)
{
	int ind = stringLength(s1);
	int add;
	for (add = 0; add < copiedInd; add++)
	{
		*(s1 + ind + add) = *(s1 + add);
	}
	*(s1 + ind + add) = '\0';
}

int stringNCompare(char s1[], char s2[], int compInd)
{
	for (int ind = 0; ind < compInd; ind++)
	{
		if (*(s1 + ind) == '\0' || *(s1 + ind) < *(s2 + ind))
			return -1; //s1 is smaller than s2
		if (*(s2 + ind) == '\0' || *(s1 + ind) > *(s2 + ind))
			return 1; // s1 is bigger than s2
	}
	return 0;//comparison ended with both string equal in compared section
}
