#include <iostream>
#include <limits>
using namespace std;

int main() {
    int hour;
    cout << "Enter hour (0-23): ";
    if (!(cin >> hour)) {
        cin.clear();
        cin.ignore(numeric_limits<streamsize>::max(), '\n');
        cout << "Invalid numeric input\n";
        return 1;
    }
    if (hour < 0 || hour > 23) {
        cout << "Hour out of range\n";
        return 1;
    }
    cout << "Hour accepted: " << hour << '\n';
    return 0;
}
