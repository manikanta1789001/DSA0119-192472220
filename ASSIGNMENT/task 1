#include <iostream>
#include <string>
using namespace std;

class SmartCard {
private:
    string cardId;
    int balance;
public:
    SmartCard(string id, int amount) : cardId(id), balance(amount) {}
    void display() const {
        cout << "Card ID: " << cardId << '\n';
        cout << "Balance: Rs " << balance << '\n';
    }
};

int main() {
    SmartCard card("MC101", 100);
    card.display();
    cout << "Objects represent passengers, cards, journeys and fare tables.\n";
    return 0;
}
