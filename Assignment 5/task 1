#include <iostream>
#include <iomanip>
#include <memory>
#include <string>
#include <vector>

class Bill {
protected:
    std::string patient;
public:
    explicit Bill(const std::string& p) : patient(p) {}
    virtual ~Bill() = default;
    virtual double total() const = 0;
    virtual std::string type() const { return "Bill"; }

    void print() const {
        std::cout << type() << " " << patient << ": "
                  << total() << '\n';
    }
};

class OutPatient : public Bill {
    double consultation, tests;
public:
    OutPatient(const std::string& p, double c, double t)
        : Bill(p), consultation(c), tests(t) {}
    double total() const override { return consultation + tests; }
    std::string type() const override { return "OP"; }
};

class InPatient : public Bill {
    int days;
    double perDay, surgery;
public:
    InPatient(const std::string& p, int d, double rate, double s)
        : Bill(p), days(d), perDay(rate), surgery(s) {}
    double total() const override { return days * perDay + surgery; }
    std::string type() const override { return "IP"; }
};

class DayCare : public Bill {
    double packagePrice;
public:
    DayCare(const std::string& p, double price)
        : Bill(p), packagePrice(price) {}
    double total() const override { return packagePrice; }
    std::string type() const override { return "DayCare"; }
};

class Emergency : public Bill {
    double base, timeCharge;
public:
    Emergency(const std::string& p, double b, double t)
        : Bill(p), base(b), timeCharge(t) {}
    double total() const override { return base + timeCharge; }
    std::string type() const override { return "Emergency"; }
};

int main() {
    std::vector<std::unique_ptr<Bill>> bills;
    bills.push_back(std::make_unique<OutPatient>("Ravi", 500, 1200));
    bills.push_back(std::make_unique<InPatient>("Meena", 3, 2500, 40000));
    bills.push_back(std::make_unique<DayCare>("Arun", 18000));
    bills.push_back(std::make_unique<Emergency>("Sara", 3000, 2500));

    double sum = 0;
    for (const auto& bill : bills) {
        bill->print();
        sum += bill->total();
    }
    std::cout << "Total " << sum << '\n';
    return 0;
}
