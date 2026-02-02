```diff
--- c/develop/DSA_Placed/Basics_Of_Cpp/04_Conditional.md
+++ c/develop/DSA_Placed/Basics_Of_Cpp/04_Conditional.md
@@ -1,173 +1,228 @@
-// Conditional statement in c++
-// Normal if
-#include <iostream>
-using namespace std;
-int main()
-{
-    int age;
-    cout << "Enter your age: ";
-    cin >> age;
-    if (age >= 18)
-    {
-        cout << "You can vote";
-    }
-}
-
-// if else
-#include <iostream>
-using namespace std
-int main(){
-    int age;
-    cout<<"Enter your age: ";
-    cin>>age;
-    if(age>=18){
-        cout<<"You can vote";
-    }
-
-    else{
-        cout<<"You can't vote";
-    }
-}
-
-// else if
-#include <iostream>
-using namespace std
-int main(){
-    int age;
-    cout<<"Enter your age: ";
-    cin>>age;
-    if(age>=18){
-        cout<<"You can vote";
-    }
-    else if(age<18){
-        cout<<"You can't vote";
-    }
-    else{
-        cout<<"Invalid age";
-    }
-}
-
-// Nested if 
-#include <iostream>
-using namespace std
-int main(){
-
-}
-
-// ternary operator
-#include <iostream>
-using namespace std
-int main(){
-    int age;
-    cout<<"Enter your age: ";
-    cin>>age;
-    (age>=18)?cout<<"You can vote":cout<<"You can't vote";
-}
-
-// switch case
-#include <iostream>
-using namespace std
-int main(){
-    int age;
-    cout<<"Enter your age: ";
-    cin>>age;
-    switch (age){
-        case 18:
-        cout<<"You can vote";
-        break;
-        case 17:
-        cout<<"You can't vote";
-        break;
-        default:
-        cout<<"Invalid age";
-        break;
-    
-    }
-}
-
-
-// Design calculator using if else if and else
-#include <iostream>
-using namespace std
-int main() {
-    float num1, num2;
-    char op;
-    cout << "Enter the first number: ";
-    cin >> num1;
-    cout << "Enter the second number: ";
-    cin >> num2;
-    cout << "Enter the operator: ";
-    cin >> op;
-    if (op == '+') {
-        cout << num1 + num2;
-    }
-    else if (op == '-') {
-        cout << num1 - num2;
-    }
-
-    else if (op == '*') {
-        cout << num1 * num2;
-    }
-    else if (op == '/') {
-        cout << num1 / num2;
-    }
-
-    else {
-        cout << "Invalid operator";
-    }
-
-    return 0;
-}
-
-// Calculator using switch statement
-#include<iostream>
-using namespace std;
-int main(){
-    float num1,num2;
-    char op;
-    cout<<"Enter the first number: ";
-    cin>>num1;
-    cout<<"Enter the second number: ";
-    cin>>num2;
-    cout<<"Enter the operator: ";
-    cin>>op;
-
-    switch(op){
-        case '+':
-        cout<<num1+num2;
-        break;
-        case '-':
-        cout<<num1-num2;
-        break;
-        case '*':
-        cout<<num1*num2;
-        break;
-        case '/':
-        cout<<num1/num2;
-        break;
-        default:
-        cout<<"Invalid operator";
-        break;
-    }
-    return 0;
-}
-
-
-// Checking leap year or not
-#include<iostream>
-using namespace std;
-int main(){
-    int year;
-    cout<<"Enter the year: ";
-    cin>>year;
-    if(year%4==0){
-        cout<<"Leap year";
-    }
-    else{
-        cout<<"Not a leap year";
-    }
-    return 0;
-}
-
-
-// Checking whether a number is Armstrong or not (3-digit)
-#include <iostream>
-using namespace std;
-
-int main() {
-    int n;
-    cout << "Enter the number: ";
-    cin >> n;
-    int original = n;   // store original number
-    int dig1 = n % 10;
-    n /= 10;
-    int dig2 = n % 10;
-    n /= 10;
-    int dig3 = n % 10;
-    int cubeSum = (dig1 * dig1 * dig1) +
-                  (dig2 * dig2 * dig2) +
-                  (dig3 * dig3 * dig3);
-    if (cubeSum == original) {
-        cout << "Armstrong number";
-    } else {
-        cout << "Not an Armstrong number";
-    }
-    return 0;
-}
-
-
-// VVI: typedef keyword is used to create an alias (new name) for an existing data type,
-// user-defined data type, or pointer.
-// It does NOT create a new data type; it only creates an alternative name.
-
-
-// 📌 Key Points (Very Very Important)
-// typedef = type alias
-
-// Works with:
-
-// Existing data types (int, float, etc.)
-
-// User-defined data types (struct, union)
-
-// Pointers
-
-// No new data type is created
-
-// ✅ Examples (Quick Recall)
-// 1️⃣ Existing Data Type
-// typedef int myInt;
-// myInt a = 10;
-// 2️⃣ User-Defined Data Type
-typedef struct {
-    int id;
-    float salary;
-} Employee;
-
-Employee e1;
-// 3️⃣ Pointer Alias
-typedef int* IntPtr;
-IntPtr p;
+# Conditional Statements in C++
+
+Conditional statements (also known as decision-making statements) allow a program to execute different blocks of code based on specified conditions. They control the flow of execution.
+
+## 1. The `if` Statement
+The `if` statement executes a block of code only if the specified condition is `true`.
+
+**Syntax:**
+```cpp
+if (condition) {
+    // code to be executed if condition is true
+}
+```
+
+**Example:**
+```cpp
+#include <iostream>
+using namespace std;
+
+int main() {
+    int age;
+    cout << "Enter your age: ";
+    cin >> age;
+
+    if (age >= 18) {
+        cout << "You can vote" << endl;
+    }
+    return 0;
+}
+```
+
+## 2. The `if-else` Statement
+The `if-else` statement provides an alternative block of code to execute if the condition is `false`.
+
+**Syntax:**
+```cpp
+if (condition) {
+    // code if true
+} else {
+    // code if false
+}
+```
+
+**Example:**
+```cpp
+#include <iostream>
+using namespace std;
+
+int main() {
+    int age;
+    cout << "Enter your age: ";
+    cin >> age;
+
+    if (age >= 18) {
+        cout << "You can vote" << endl;
+    } else {
+        cout << "You can't vote" << endl;
+    }
+    return 0;
+}
+```
+
+## 3. The `else-if` Ladder
+Used when checking multiple conditions sequentially. The code stops checking once a true condition is found.
+
+**Example:**
+```cpp
+#include <iostream>
+using namespace std;
+
+int main() {
+    int age;
+    cout << "Enter your age: ";
+    cin >> age;
+
+    if (age >= 18) {
+        cout << "You can vote" << endl;
+    } else if (age > 0 && age < 18) {
+        cout << "You can't vote yet" << endl;
+    } else {
+        cout << "Invalid age" << endl;
+    }
+    return 0;
+}
+```
+
+## 4. Nested `if` Statements
+An `if` statement inside another `if` statement. This allows for more complex decision logic.
+
+**Example:**
+```cpp
+#include <iostream>
+using namespace std;
+
+int main() {
+    int age;
+    bool hasVoterID;
+
+    cout << "Enter age: ";
+    cin >> age;
+    
+    if (age >= 18) {
+        cout << "Do you have a voter ID? (1 for Yes, 0 for No): ";
+        cin >> hasVoterID;
+
+        if (hasVoterID) {
+            cout << "You can vote!" << endl;
+        } else {
+            cout << "You need a voter ID to vote." << endl;
+        }
+    } else {
+        cout << "You are too young to vote." << endl;
+    }
+    return 0;
+}
+```
+
+## 5. Ternary Operator (Short Hand `if-else`)
+A one-line replacement for simple `if-else` statements.
+
+**Syntax:** `condition ? expression_if_true : expression_if_false;`
+
+**Example:**
+```cpp
+#include <iostream>
+using namespace std;
+
+int main() {
+    int age;
+    cout << "Enter your age: ";
+    cin >> age;
+
+    (age >= 18) ? cout << "You can vote" : cout << "You can't vote";
+    return 0;
+}
+```
+
+## 6. The `switch` Statement
+The `switch` statement is an alternative to the `else-if` ladder when comparing a variable against distinct values (constants).
+
+*   **`break`**: Stops execution inside the switch block. Without it, execution "falls through" to the next case.
+*   **`default`**: Executed if no cases match (like the final `else`).
+
+**Example:**
+```cpp
+#include <iostream>
+using namespace std;
+
+int main() {
+    int day = 3;
+    switch (day) {
+        case 1: cout << "Monday"; break;
+        case 2: cout << "Tuesday"; break;
+        case 3: cout << "Wednesday"; break;
+        default: cout << "Invalid Day";
+    }
+    return 0;
+}
+```
+
+---
+
+# Practice Programs
+
+### 1. Calculator using `if-else`
+```cpp
+#include <iostream>
+using namespace std;
+
+int main() {
+    float num1, num2;
+    char op;
+    cout << "Enter first number: ";
+    cin >> num1;
+    cout << "Enter second number: ";
+    cin >> num2;
+    cout << "Enter operator (+, -, *, /): ";
+    cin >> op;
+
+    if (op == '+') {
+        cout << "Result: " << num1 + num2;
+    } else if (op == '-') {
+        cout << "Result: " << num1 - num2;
+    } else if (op == '*') {
+        cout << "Result: " << num1 * num2;
+    } else if (op == '/') {
+        if (num2 != 0)
+            cout << "Result: " << num1 / num2;
+        else
+            cout << "Error: Division by zero";
+    } else {
+        cout << "Invalid operator";
+    }
+    return 0;
+}
+```
+
+### 2. Calculator using `switch`
+```cpp
+#include <iostream>
+using namespace std;
+
+int main() {
+    float num1, num2;
+    char op;
+    cout << "Enter two numbers: ";
+    cin >> num1 >> num2;
+    cout << "Enter operator: ";
+    cin >> op;
+
+    switch (op) {
+        case '+': cout << num1 + num2; break;
+        case '-': cout << num1 - num2; break;
+        case '*': cout << num1 * num2; break;
+        case '/': 
+            if(num2 != 0) cout << num1 / num2; 
+            else cout << "Error: Division by zero";
+            break;
+        default: cout << "Invalid operator"; break;
+    }
+    return 0;
+}
+```
+
+### 3. Check Leap Year
+A year is a leap year if:
+1. It is divisible by 4 AND not divisible by 100, OR
+2. It is divisible by 400.
+
+```cpp
+#include <iostream>
+using namespace std;
+
+int main() {
+    int year;
+    cout << "Enter year: ";
+    cin >> year;
+
+    if ((year % 4 == 0 && year % 100 != 0) || (year % 400 == 0)) {
+        cout << year << " is a Leap Year";
+    } else {
+        cout << year << " is Not a Leap Year";
+    }
+    return 0;
+}
+```
+
+### 4. Check Armstrong Number (3-Digit)
+An Armstrong number (or Narcissistic number) is a number that is equal to the sum of its own digits each raised to the power of the number of digits.
+*   Example: 153 = 1³ + 5³ + 3³ = 1 + 125 + 27 = 153.
+
+```cpp
+#include <iostream>
+using namespace std;
+
+int main() {
+    int n;
+    cout << "Enter a 3-digit number: ";
+    cin >> n;
+    
+    int original = n;
+    int sum = 0;
+    
+    // Extract digits and sum their cubes
+    while (n > 0) {
+        int digit = n % 10;
+        sum += digit * digit * digit;
+        n /= 10;
+    }
+
+    if (sum == original) {
+        cout << "Armstrong number";
+    } else {
+        cout << "Not an Armstrong number";
+    }
+    return 0;
+}
+```
+
+---
+
+# Important Keyword: `typedef`
+
+The `typedef` keyword is used to create an **alias** (a new name) for an existing data type. It does **not** create a new type, just a new name for convenience or readability.
+
+### Syntax
+`typedef existing_type new_name;`
+
+### Examples
+
+**1. Basic Types**
+```cpp
+typedef long long ll;
+ll number = 1234567890; // Same as long long number = ...
+```
+
+**2. Structures**
+```cpp
+typedef struct {
+    int id;
+    float salary;
+} Employee;
+
+Employee emp1; // Instead of 'struct Employee emp1'
+```
+
+**3. Pointers**
+```cpp
+typedef int* IntPtr;
+IntPtr p; // Same as int* p;
+```
