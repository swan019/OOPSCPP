# OOPSCPP

#include <iostream>
using namespace std;

// Creating a class named Coordinate.
class Coordinate
{
private:
        // Make private data members, namely x coordinate and y coordinate.
    int x;
    int y;

public:
    // A member function to assign the private data member's values from the user.
    void set_values(int a, int b)
    {
        x = a;
        y = b;
    }
    
    // A member function to print the private data of members.
    void show()
    {
        cout << "x: " << x << endl;
        cout << "y: " << y << endl;
    }
    
    // Overloaded friend functions to demonstrate the ability of function overloading.
    friend void change_Values(Coordinate &); // Friend function 1
    friend void change_Values(Coordinate & , int v); // Friend function 2
};

// Implementing friend function 1 with an instance of the class as the parameter.
void change_Values(Coordinate & c)
{
    c.x = c.x + 5;
    c.y = c.y + 5;
}

// Implementing friend function 2 with an instance of the class and an integer v as the parameters.
void change_Values(Coordinate & c, int v)
{
    c.x = c.x + v;
    c.y = c.y + v;
}

// Main function
int main ()
{
    // Create two instances of the Coordinate class.
    Coordinate c1, c2;

    // Assign values to the instances c1 and c2.
    c1.set_values (8, 9);
    c2.set_values (8, 9);

    // Print the values of the instance c before changing the values.
    cout << "The values of Coordinate before changing are: " << endl;
    c1.show();
    cout << endl;

    // Call the function change_Values to change the values.
    change_Values(c1);

    // Print the values of the instance c after changing the values.
    cout << "The values of Coordinate after changing by the first friend function are: " << endl;
    c1.show();
    cout << endl;

    // Call the function change_Values to change the values.
    change_Values(c2 , 2);

    // Print the values of the instance c after changing the values.
    cout << "The values of Coordinate after changing by the second friend function are: " << endl;
    c2.show();
    cout << endl;

    return 0;

}

