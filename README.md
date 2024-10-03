# Bank-account-management
#include<iostream>
using namespace std;

class BankAccount {
    int accountNumber;
    string name;
    float balance;

public:
    void createAccount() {
        cout << "Enter Account Number: ";
        cin >> accountNumber;
        cout << "Enter Name: ";
        cin >> name;
        cout << "Enter Initial Balance: ";
        cin >> balance;
        cout << "\nAccount Created Successfully!\n";
    }

    void showAccountDetails() {
        cout << "\nAccount Number: " << accountNumber;
        cout << "\nName: " << name;
        cout << "\nBalance: " << balance << endl;
    }

    void depositMoney() {
        float amount;
        cout << "Enter Amount to Deposit: ";
        cin >> amount;
        balance += amount;
        cout << "\nAmount Deposited Successfully!\n";
    }

    void withdrawMoney() {
        float amount;
        cout << "Enter Amount to Withdraw: ";
        cin >> amount;
        if (amount <= balance) {
            balance -= amount;
            cout << "\nAmount Withdrawn Successfully!\n";
        } else {
            cout << "\nInsufficient Balance!\n";
        }
    }
};

int main() {
    BankAccount account;
    int choice;

    do {
        cout << "\n--- Bank Management System ---\n";
        cout << "1. Create Account\n";
        cout << "2. View Account Details\n";
        cout << "3. Deposit Money\n";
        cout << "4. Withdraw Money\n";
        cout << "5. Exit\n";
        cout << "Enter Your Choice: ";
        cin >> choice;

        switch (choice) {
        case 1:
            account.createAccount();
            break;
        case 2:
            account.showAccountDetails();
            break;
        case 3:
            account.depositMoney();
            break;
        case 4:
            account.withdrawMoney();
            break;
        case 5:
            cout << "Exiting...\n";
            break;
        default:
            cout << "Invalid choice! Please try again.\n";
        }
    } while (choice != 5);

    return 0;
}
