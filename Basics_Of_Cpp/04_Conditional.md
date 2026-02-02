// Conditional statement in c++
// Normal if
#include <iostream>
using namespace std;
int main()
{
    int age;
    cout << "Enter your age: ";
    cin >> age;
    if (age >= 18)
    {
        cout << "You can vote";
    }
}

// if else
#include <iostream>
using namespace std
int main(){
    int age;
    cout<<"Enter your age: ";
    cin>>age;
    if(age>=18){
        cout<<"You can vote";
    }

    else{
        cout<<"You can't vote";
    }
}

// else if
#include <iostream>
using namespace std
int main(){
    int age;
    cout<<"Enter your age: ";
    cin>>age;
    if(age>=18){
        cout<<"You can vote";
    }
    else if(age<18){
        cout<<"You can't vote";
    }
    else{
        cout<<"Invalid age";
    }
}

// Nested if 
#include <iostream>
using namespace std
int main(){

}

// ternary operator
#include <iostream>
using namespace std
int main(){
    int age;
    cout<<"Enter your age: ";
    cin>>age;
    (age>=18)?cout<<"You can vote":cout<<"You can't vote";
}

// switch case
#include <iostream>
using namespace std
int main(){
    int age;
    cout<<"Enter your age: ";
    cin>>age;
    switch (age){
        case 18:
        cout<<"You can vote";
        break;
        case 17:
        cout<<"You can't vote";
        break;
        default:
        cout<<"Invalid age";
        break;
    
    }
}


// Design calculator using if else if and else
#include <iostream>
using namespace std
int main() {
    float num1, num2;
    char op;
    cout << "Enter the first number: ";
    cin >> num1;
    cout << "Enter the second number: ";
    cin >> num2;
    cout << "Enter the operator: ";
    cin >> op;
    if (op == '+') {
        cout << num1 + num2;
    }
    else if (op == '-') {
        cout << num1 - num2;
    }

    else if (op == '*') {
        cout << num1 * num2;
    }
    else if (op == '/') {
        cout << num1 / num2;
    }

    else {
        cout << "Invalid operator";
    }

    return 0;
}

// Calculator using switch statement
#include<iostream>
using namespace std;
int main(){
    float num1,num2;
    char op;
    cout<<"Enter the first number: ";
    cin>>num1;
    cout<<"Enter the second number: ";
    cin>>num2;
    cout<<"Enter the operator: ";
    cin>>op;

    switch(op){
        case '+':
        cout<<num1+num2;
        break;
        case '-':
        cout<<num1-num2;
        break;
        case '*':
        cout<<num1*num2;
        break;
        case '/':
        cout<<num1/num2;
        break;
        default:
        cout<<"Invalid operator";
        break;
    }
    return 0;
}


// Checking leap year or not
#include<iostream>
using namespace std;
