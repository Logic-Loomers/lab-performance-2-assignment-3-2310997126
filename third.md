Assume you oversee a small library and would like to develop a program that looks up books using their ISBNs. A list of books with their corresponding ISBN digits is in front of you. After the librarian inputs an ISBN, your software will look through the list to locate the relevant book.  The book's title and other details will be shown if the book is located. A notice stating that the book is not available in the library will appear if it cannot be located.
#include <iostream>
#include <string>
#include <unordered_map>

using namespace std;

int main() {

    unordered_map<string, string> library = {
        {"978-0131103627", "The C++ Programming Language"},
        {"978-0321563842", "Effective C++"},
        {"978-0201633610", "Design Patterns"}
    };


    cout << "Enter the ISBN: ";
    string isbn;
    cin >> isbn;


    auto it = library.find(isbn);
    if (it != library.end()) {

        cout << "Book Title: " << it->second << endl;
    } else {
        
        cout << "The book with ISBN " << isbn << " is not available in the library." << endl;
    }

    return 0;
}
