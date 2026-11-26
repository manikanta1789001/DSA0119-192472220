#include <iostream>
#include <iomanip>
using namespace std;

enum class Zone { Inner, Middle, Outer };
constexpr long long BASE_PAISE[] = {1000, 2000, 3000};
constexpr int PEAK_SURCHARGE_PERCENT = 20;
constexpr long long MIN_BALANCE_PAISE = 5000;

long long fare(Zone zone, bool peak) {
    long long amount = 0;
    switch (zone) {
        case Zone::Inner: amount = BASE_PAISE[0]; break;
        case Zone::Middle: amount = BASE_PAISE[1]; break;
        case Zone::Outer: amount = BASE_PAISE[2]; break;
    }
    if (peak) amount += amount * PEAK_SURCHARGE_PERCENT / 100;
    return amount;
}
bool canTravel(long long balance, long long amount) {
    return amount >= 0 && balance - amount >= MIN_BALANCE_PAISE;
}
void printRupees(long long paise) {
    cout << "Rs " << paise / 100 << '.' << setw(2) << setfill('0') << paise % 100 << setfill(' ');
}
int main() {
    long long balance = 10000;
    struct Trip { Zone zone; bool peak; };
    Trip trips[] = {{Zone::Inner, false}, {Zone::Outer, true}, {Zone::Middle, false}};
    for (const Trip& trip : trips) {
        long long amount = fare(trip.zone, trip.peak);
        if (canTravel(balance, amount)) {
            balance -= amount;
            cout << "Fare "; printRupees(amount);
        } else cout << "Denied (low balance)";
        cout << " balance Rs " << balance / 100 << '\n';
    }
    return 0;
}
