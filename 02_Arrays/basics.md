---

# 📚 C++ Notes: Arrays and Decimal Numbers

## 🎯 Arrays in C++

An array is a fundamental data structure in C++ used to store a collection of elements of the same data type in contiguous memory locations. These elements are accessed using a single variable name and an index.

### 🔹 1. Why Arrays Are Used

*   **Store Multiple Values:** Allows storing a collection of related data items under a single name, reducing the need for many individual variables.
*   **Faster Access:** Elements can be accessed directly and quickly using their index (O(1) time complexity), making data retrieval very efficient.
*   **Simplifies Code:** Organizes homogeneous data efficiently, making code cleaner and easier to manage for large datasets.
*   **Efficient Memory Organization:** Data is stored contiguously, which can improve cache performance and overall program speed.

### 🔹 2. Basic Syntax

To declare an array, you specify the data type, the array name, and its size (number of elements) in square brackets.

```cpp
data_type array_name[size];
```

**Example:**

```cpp
int marks; // Declares an array named 'marks' that can hold 5 integer values.
```

### 🔹 3. Array Initialization

Arrays can be initialized at the time of declaration.

*   **Full Initialization:**
    ```cpp
    int a = {10, 20, 30, 40, 50};
    ```
*   **Partial Initialization:** If fewer elements are provided than the array size, the remaining elements are automatically initialized to `0` for global/static arrays. For local arrays, if at least one element is initialized, the rest are zero-initialized.
    ```cpp
    int b = {1, 2}; // b will be {1, 2, 0, 0, 0}
    ```
*   **Zero Initialization (All elements to 0):**
    ```cpp
    int c = {}; // All 5 elements will be initialized to 0.
    int d[] = {0}; // An array of size 1, with element 0.
    ```
*   **Uninitialized Local Arrays:** If a local array is declared without any initialization, its elements will contain **garbage values**. Accessing these values leads to **undefined behavior**.
    ```cpp
    int f; // 'f' contains garbage values.
    // cout << f; // ⚠️ Dangerous! Undefined behavior.
    ```

### 🔹 4. Accessing Array Elements

Array elements are accessed using their index, which starts from `0`.

```cpp
cout << a; // Accesses the first element (value: 10)
cout << a; // Accesses the fifth (and last) element (value: 50)
```

**⚠️ Important:** Index starts from `0`, not `1`. For an array of size `N`, valid indices range from `0` to `N-1`. Accessing `a[N]` or `a[-1]` is an **out-of-bounds access** and results in **undefined behavior**.

### 🔹 5. Types of Arrays in C++

*   **One-Dimensional Array:** A linear list of elements.
    ```cpp
    int arr;
    ```
*   **Two-Dimensional Array:** An array of arrays, often visualized as a matrix (rows and columns).
    ```cpp
    int matrix; // A 3x3 matrix
    ```
*   **Multi-Dimensional Array:** Arrays with more than two dimensions.
    ```cpp
    int data; // A 2x3x4 array
    ```

### 🔹 6. Traversing an Array (Using Loops)

To process each element in an array, loops are commonly used.

```cpp
// Using a traditional for loop
for(int i = 0; i < 5; i++) {
    cout << a[i] << " ";
}

// Using a range-based for loop (C++11 and later)
// This works for fixed-size arrays and std::vector
for (int element : a) { // 'a' must be a fixed-size array or std::vector
    cout << element << " ";
}
```

### 🔹 7. Memory Concept (Important)

Arrays are stored in **contiguous memory locations**. This means elements are placed one after another without any gaps.

**Address Formula:**
The address of an element can be calculated using the following formula:
`Address(element_at_index) = base_address + index × size_of_data_type`

**Example:** If `base_address` of an `int` array is `1000` and `sizeof(int)` is `4` bytes:
*   `Address(arr[0]) = 1000 + 0 * 4 = 1000`
*   `Address(arr[1]) = 1000 + 1 * 4 = 1004`
*   `Address(arr[2]) = 1000 + 2 * 4 = 1008`

### 🔹 8. `sizeof` Operator for Array Size

The `sizeof` operator can be used to determine the size of an array.

*   `sizeof(array)`: Returns the total size of the array in bytes.
*   `sizeof(array[0])` (or `sizeof(data_type)`): Returns the size of a single element in bytes.
*   **Trick:** `Number of elements = sizeof(array) / sizeof(array[0])`. This works reliably only for C-style arrays whose size is known at compile time (i.e., not when passed to a function where it decays to a pointer, or for `std::vector`).

**Example:**
```cpp
int arr[] = {2, 4, 14};
cout << "Total size in bytes: " << sizeof(arr) << endl; // Output: 12 (assuming int is 4 bytes)
cout << "Size of one element: " << sizeof(arr) << endl; // Output: 4
cout << "Number of elements: " << sizeof(arr) / sizeof(arr) << endl; // Output: 3
```

### 🔹 9. Advantages

*   **Easy Data Management:** Simple to declare and use for homogeneous data.
*   **Fast Access:** Direct access to any element using its index (O(1)).
*   **Code Cleaner:** Organizes related data efficiently.

### 🔹 10. Limitations

*   **Fixed Size:** Once declared, the size of a C-style array cannot be changed dynamically. This can lead to memory wastage if too much is allocated or overflow if too little.
*   **Cannot Store Mixed Data Types:** All elements must be of the same data type.
*   **No Bounds Checking:** C++ does not automatically check if an array access is within its valid bounds. This means `arr[100]` on an array of size 5 will compile but lead to **undefined behavior** at runtime, which is a critical source of bugs and security vulnerabilities.

### 🔹 11. Key Points to Remember & Tricks (Exam-Friendly)

*   **Homogeneous Data:** Arrays can only store elements of a single data type.
*   **Zero-Based Indexing:** Always remember that array indices start from `0`.
*   **Constant Size:** For C-style arrays, the size must be a compile-time constant. Using a variable for size (Variable Length Arrays - VLAs) is a C99 feature and not standard C++. For dynamic sizing, use `std::vector`.
*   **Out-of-Bounds Access:** Accessing an array element outside its declared range (e.g., `arr[size]` or `arr[-1]`) results in **undefined behavior**. This is a critical source of bugs and security vulnerabilities.
*   **Uninitialized Elements Behavior:**
    *   Global or static arrays are zero-initialized by default.
    *   Local arrays, if partially initialized, have their remaining elements zero-initialized.
    *   Local arrays, if not initialized at all, contain **garbage values**.
*   **Arrays Decay to Pointers:** When a C-style array is passed to a function, it "decays" into a pointer to its first element. This means the function loses information about the array's original size. You typically pass the size as a separate argument.
*   **Modern C++ Alternatives:**
    *   `std::array` (C++11): A fixed-size array wrapper that provides container-like features and doesn't decay to a pointer. It offers compile-time size checking and is safer than raw C-style arrays.
    *   `std::vector`: A dynamic array that can grow and shrink in size at runtime. It's generally preferred over raw C-style arrays for most use cases due to its flexibility, safety features (like bounds checking with `at()`), and automatic memory management.

### 🔹 12. Real-Life Example

```cpp
int temperature;   // Storing temperature of 7 days
string weekdays = {"Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"}; // Storing names of weekdays
```

---

## 🔢 Decimal Numbers in C++

Decimal numbers, also known as floating-point numbers, are used to represent real numbers (numbers with fractional parts). C++ provides several data types for this purpose, differing in precision and range.

### 🔹 1. Data Types for Decimal Numbers

*   **`float`**: Represents a single-precision floating-point number.
    *   Typically occupies 4 bytes.
    *   Offers about 6-7 decimal digits of precision.
    *   **Example:** `float pi = 3.14159f;` (Note the `f` suffix for float literals; without it, `3.14159` is treated as a `double`).
*   **`double`**: Represents a double-precision floating-point number.
    *   Typically occupies 8 bytes.
    *   Offers about 15-17 decimal digits of precision. This is the most commonly used floating-point type and is the default for floating-point literals.
    *   **Example:** `double gravity = 9.80665;`
*   **`long double`**: Represents an extended-precision floating-point number.
    *   Size varies by compiler and platform (often 10 or 16 bytes).
    *   Offers even greater precision than `double`.
    *   **Example:** `long double very_precise_val = 1.234567890123456789L;` (Note the `L` suffix).

### 🔹 2. Usage in Arrays

Arrays can store decimal numbers just like integers, by specifying the appropriate floating-point data type.

**Examples:**

```cpp
// Storing daily temperatures (float array)
float dailyTemperatures = {25.5f, 26.1f, 24.9f, 27.0f, 28.2f, 26.8f, 25.0f};

// Storing product prices (double array)
double productPrices = {19.99, 45.50, 12.75, 99.00, 5.25};

// Accessing elements
cout << "Today's temperature: " << dailyTemperatures << " degrees Celsius." << endl;
cout << "Price of item 3: $" << productPrices << endl;
```

### 🔹 3. Key Points & Tricks for Decimal Numbers

*   **Precision Limitations:** Floating-point numbers have finite precision. This means they cannot represent all real numbers exactly, leading to potential rounding errors. For example, `0.1` cannot be represented exactly in binary floating-point.
*   **Avoid Direct Equality Comparisons (`==`):** Due to precision issues, comparing two floating-point numbers directly for equality (`a == b`) is generally unreliable. Instead, check if their absolute difference is very small (within a defined epsilon).
    ```cpp
    // Bad:
    // if (a == b)

    // Good:
    // #include <cmath> // For std::abs
    // const double EPSILON = 1e-9; // A small tolerance value
    // if (std::abs(a - b) < EPSILON) {
    //     // Numbers are considered equal
    // }
    ```
*   **Performance:** `float` operations can sometimes be faster than `double` operations, but modern CPUs are highly optimized for `double`. Use `double` by default unless memory or specific performance constraints dictate `float`.
*   **Input/Output Formatting:** Use `std::fixed` and `std::setprecision` from the `<iomanip>` header to control the display format of floating-point numbers.
    ```cpp
    #include <iomanip> // For std::fixed, std::setprecision
    // ...
    double val = 123.456789;
    cout << std::fixed << std::setprecision(2) << val << endl; // Output: 123.46
    cout << std::setprecision(5) << val << endl; // Output: 123.46000 (still fixed due to previous std::fixed)
    cout << std::defaultfloat << std::setprecision(5) << val << endl; // Output: 123.46 (defaultfloat removes fixed)
    ```
*   **Integer vs. Floating-Point Division:** Be mindful of integer division. `5 / 2` results in `2` (integer), while `5.0 / 2.0` or `5 / 2.0` results in `2.5` (floating-point).