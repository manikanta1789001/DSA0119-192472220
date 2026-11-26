#include <iostream>
using namespace std;
constexpr long long MIN_BALANCE = 5000;

// Procedural approach
bool canTravelProcedural(long long balance, long long fare) {
    return fare >= 0 && balance - fare >= MIN_BALANCE;
}
bool deductProcedural(long long& balance, long long fare) {
    if (!canTravelProcedural(balance, fare)) return false;
    balance -= fare;
    return true;
}

// Object-oriented approach
class SmartCard {
private:
    long long balancePaise;
public:
    SmartCard(long long initial) : balancePaise(initial) {}
    bool deduct(long long fare) {
        if (fare < 0 || balancePaise - fare < MIN_BALANCE) return false;
        balancePaise -= fare;
        return true;
    }
    long long balance() const { return balancePaise; }
};
int main() {
    long long proceduralBalance = 10000;
    cout << "Procedural accepted: " << boolalpha << deductProcedural(proceduralBalance, 2000) << '\n';
    cout << "Procedural balance (paise): " << proceduralBalance << '\n';
    SmartCard card(10000);
    cout << "OOP accepted: " << card.deduct(2000) << '\n';
    cout << "OOP balance (paise): " << card.balance() << '\n';
    return 0;
}
