# OOPSCPP

#include <iostream>
using namespace std;

// Creating a class named Complex.
class Complex
{
private:
    // Make private data members, namely real and imaginary.
    int real;
    int imaginary;

public:
    // A member function to assign the private data member's values from the user.
    void set_values(int a, int b)
    {
        real = a;
        imaginary = b;
    }

    // A member function to print the private data of members.
    void show()
    {
        cout << "The complex number is " << real << " + " << imaginary << "i" << endl;
    }

    // Overloaded operator to perform custom addition.
    friend Complex operator+(Complex&, Complex&); // Friend function operator overloading.

};

// Implementing friend function with two parameters as of the class Complex.
Complex operator+(Complex& c1, Complex& c2) // Call by reference
{
    // Create an object to return.
    Complex c3;

    // Perform the addition of real and imaginary parts.
    c3.real = c1.real + c2.real;
    c3.imaginary = c1.imaginary + c2.imaginary;

    // Return the resulting object.
    return c3;
}

// Main function
int main ()
{
    // Create two instances of the Complex class.
    Complex c1, c2;

    // Assign values to the instances c1 and c2.
    c1.set_values (8, 9);
    c2.set_values (5, 11);

    // Create an instance to store the sum of c1 and c2.
    Complex c3;

    // Using the overloaded operator.
    c3 = c2 + c1;

    // Print the values of the instance c3.
    c3.show();

    return 0;

}

