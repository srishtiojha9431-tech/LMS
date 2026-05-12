#include <iostream>
#include <cstring>

using namespace std;

class Book
{
private:
    int bookID;
    char title[50];
    char author[50];
    bool issued;

    // Issuer Details
    char issuedTo[50];
    int memberID;

public:
    void addBook()
    {
        cout << "\nEnter Book ID     : ";
        cin >> bookID;

        cin.ignore();

        cout << "Enter Book Title  : ";
        cin.getline(title, 50);

        cout << "Enter Author Name : ";
        cin.getline(author, 50);

        issued = false;

        strcpy(issuedTo, "None");
        memberID = 0;
    }

    void displayBook()
    {
        cout << "\n================================";
        cout << "\nBook ID      : " << bookID;
        cout << "\nTitle        : " << title;
        cout << "\nAuthor       : " << author;

        cout << "\nStatus       : ";

        if (issued)
            cout << "Issued";
        else
            cout << "Available";

        // Show issuer details if issued
        if (issued)
        {
            cout << "\nIssued To    : " << issuedTo;
            cout << "\nMember ID    : " << memberID;
        }

        cout << "\n================================\n";
    }

    int getBookID()
    {
        return bookID;
    }

    char* getTitle()
    {
        return title;
    }

    char* getAuthor()
    {
        return author;
    }

    bool isIssued()
    {
        return issued;
    }

    void issueBook(char name[], int id)
    {
        issued = true;

        strcpy(issuedTo, name);

        memberID = id;
    }

    void returnBook()
    {
        issued = false;

        strcpy(issuedTo, "None");

        memberID = 0;
    }
};


// GLOBAL ARRAY
Book books[100];

int totalBooks = 0;


// ADD BOOK
void addNewBook()
{
    books[totalBooks].addBook();

    totalBooks++;

    cout << "\nBook Added Successfully!\n";
}


// DISPLAY ALL BOOKS
void displayAllBooks()
{
    if (totalBooks == 0)
    {
        cout << "\nNo Books Available!\n";
        return;
    }

    cout << "\n========== BOOK DETAILS ==========\n";

    for (int i = 0; i < totalBooks; i++)
    {
        books[i].displayBook();
    }
}


// SEARCH BY TITLE
void searchByTitle()
{
    char searchTitle[50];

    bool found = false;

    cin.ignore();

    cout << "\nEnter Book Title : ";

    cin.getline(searchTitle, 50);

    for (int i = 0; i < totalBooks; i++)
    {
        if (strcmp(books[i].getTitle(), searchTitle) == 0)
        {
            cout << "\nBook Found!\n";

            books[i].displayBook();

            found = true;
        }
    }

    if (!found)
    {
        cout << "\nBook Not Found!\n";
    }
}


// SEARCH BY AUTHOR
void searchByAuthor()
{
    char searchAuthor[50];

    bool found = false;

    cin.ignore();

    cout << "\nEnter Author Name : ";

    cin.getline(searchAuthor, 50);

    for (int i = 0; i < totalBooks; i++)
    {
        if (strcmp(books[i].getAuthor(), searchAuthor) == 0)
        {
            cout << "\nBook Found!\n";

            books[i].displayBook();

            found = true;
        }
    }

    if (!found)
    {
        cout << "\nNo Books Found By This Author!\n";
    }
}


// ISSUE BOOK
void issueBook()
{
    int id;

    bool found = false;

    cout << "\nEnter Book ID : ";

    cin >> id;

    for (int i = 0; i < totalBooks; i++)
    {
        if (books[i].getBookID() == id)
        {
            if (!books[i].isIssued())
            {
                char memberName[50];

                int memID;

                cin.ignore();

                cout << "Enter Member Name : ";

                cin.getline(memberName, 50);

                cout << "Enter Member ID   : ";

                cin >> memID;

                books[i].issueBook(memberName, memID);

                cout << "\nBook Issued Successfully!\n";
            }
            else
            {
                cout << "\nBook Already Issued!\n";
            }

            found = true;

            break;
        }
    }

    if (!found)
    {
        cout << "\nBook Not Found!\n";
    }
}


// RETURN BOOK
void returnBook()
{
    int id;

    bool found = false;

    cout << "\nEnter Book ID : ";

    cin >> id;

    for (int i = 0; i < totalBooks; i++)
    {
        if (books[i].getBookID() == id)
        {
            if (books[i].isIssued())
            {
                books[i].returnBook();

                cout << "\nBook Returned Successfully!\n";
            }
            else
            {
                cout << "\nBook Was Not Issued!\n";
            }

            found = true;

            break;
        }
    }

    if (!found)
    {
        cout << "\nBook Not Found!\n";
    }
}


// MAIN FUNCTION
int main()
{
    int choice;

    do
    {
        cout << "\n========== LIBRARY MANAGEMENT SYSTEM ==========\n";

        cout << "1. Add Book\n";

        cout << "2. Display All Books\n";

        cout << "3. Search Book By Title\n";

        cout << "4. Search Book By Author\n";

        cout << "5. Issue Book\n";

        cout << "6. Return Book\n";

        cout << "7. Exit\n";

        cout << "===============================================\n";

        cout << "Enter Your Choice : ";

        cin >> choice;

        switch (choice)
        {
        case 1:
            addNewBook();
            break;

        case 2:
            displayAllBooks();
            break;

        case 3:
            searchByTitle();
            break;

        case 4:
            searchByAuthor();
            break;

        case 5:
            issueBook();
            break;

        case 6:
            returnBook();
            break;

        case 7:
            cout << "\nThank You For Using Library Management System!\n";
            break;

        default:
            cout << "\nInvalid Choice! Please Try Again.\n";
        }

    } while (choice != 7);

    return 0;
}
