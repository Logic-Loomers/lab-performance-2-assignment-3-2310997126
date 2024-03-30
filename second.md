On a specific day, the exchange rates were as follows: the British pound was valued at $1.487 U.S., the French franc at $0.172, the German deutschemark at $0.584, and the Japanese yen at $0.00955. Write a program that prompts the user to input an amount in U.S. dollars. The program should then display this amount converted into these four other currencies. Test the program by inputting various dollar amounts and ensuring that the conversions to British pounds, French francs, German deutschemarks, and Japanese yen are accurate. Additionally, test the program with negative dollar amounts to verify that it handles invalid input appropriately.
#include <iostream>
using namespace std;

int main() {
    double us_dollars;


    cout << "Enter the amount in U.S. dollars: ";
    cin >> us_dollars;

    if (us_dollars < 0) {
        cout << "Invalid input. Please enter a positive amount." << endl;
        return 1;
    }

    double pound_rate = 1.487;
    double franc_rate = 0.172;
    double deutschemark_rate = 0.584;
    double yen_rate = 0.00955;


    double pounds = us_dollars * pound_rate;
    double francs = us_dollars * franc_rate;
    double deutschemarks = us_dollars * deutschemark_rate;
    double yen = us_dollars * yen_rate;

    cout << "Amount in British pounds: £" << pounds << endl;
    cout << "Amount in French francs: " << francs << " francs" << endl;
    cout << "Amount in German deutschemarks: " << deutschemarks << " DM" << endl;
    cout << "Amount in Japanese yen: ¥" << yen << endl;

    return 0;
}
