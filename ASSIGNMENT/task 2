#include <iostream>
using namespace std;

#define INNER_FARE 1000
constexpr int PEAK_SURCHARGE_PERCENT = 20;
enum class Zone { Inner, Middle, Outer };

int main() {
    int farePaise = INNER_FARE;
    bool peak = true;
    farePaise += farePaise * PEAK_SURCHARGE_PERCENT / 100;
    Zone zone = Zone::Inner;
    cout << "Fare in paise: " << farePaise << '\n';
    cout << "Peak status: " << boolalpha << peak << '\n';
    cout << "Zone: " << (zone == Zone::Inner ? "Inner" : "Other") << '\n';
    return 0;
}
