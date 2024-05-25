# Library Management System

## Developed by: Henrik Sachdeva

## Overview
The Library Management System is a comprehensive solution designed to manage the various tasks and operations of a library. It includes functionalities for recording owned books, issued books, returned books, and maintaining records of students who have borrowed books. The system ensures secure access through a login mechanism and offers an extensive set of features for library administration.

## Features
1. **Login System**:
   - A predefined password is required to access the system (Password: `0000`).
   - The password can be changed through the source code.

2. **Book Management**:
   - **Add Books**: Allows the addition of new books with details such as book name, author, publication, and quantity.
   - **View Books**: Display a list of all books available in the library.
   - **Search Books**: Search for a specific book by its book number.
   - **Modify Books**: Update details of existing books.
   - **Delete Books**: Remove books from the library records.

3. **Student Management**:
   - **Add Students**: Register new students with their admission number and name.
   - **View Students**: Display a list of all students.
   - **Search Students**: Search for a specific student by their admission number.
   - **Modify Students**: Update details of existing students.
   - **Delete Students**: Remove student records from the system.

4. **Book Issue and Return**:
   - **Issue Books**: Issue books to students by recording their admission number and book number.
   - **Return Books**: Record the return of books and update the system accordingly.
   - **Fine Calculation**: Basic fine calculation for late returns (Rs. 1 per day after a 15-day period).

## Usage Instructions
1. **Login**: Run the program and enter the password `0000` to gain access.
2. **Main Menu**: Choose from the following options:
   - **Book Issue**
   - **Book Deposit**
   - **Administrator Menu**
   - **Exit**
3. **Administrator Menu**: Access the following administrative functions:
   - Create Student Record
   - Display All Students Record
   - Display Specific Student Record
   - Modify Student Record
   - Delete Student Record
   - Create Book
   - Display All Books
   - Display Specific Book
   - Modify Book
   - Delete Book
   - Back to Main Menu

## Technical Details
- **Language**: C++ Programming Language
- **Development Environment**: Standard C++ library functions and features are utilized.
- **File Handling**: Data is stored and managed using binary files (`student.bin` and `book1.bin`).

## Notes
- Ensure that the `student.bin` and `book1.bin` files are present in the same directory as the executable.
- Modify the source code to change the predefined password.

## Example Usage
```cpp
int main() {
    cout << "\n\n\t\t\t*******************************************";
    cout << "\n\t\t\t------------------------------------------";
    cout << "\n\t\t\t\tLIBRARY MANAGEMENT SYSTEM";
    cout << "\n\t\t\t------------------------------------------";
    cout << "\n\t\t\t*******************************************";
    bool a = passwords();
    if (!a) {
        for (int i = 0; i < 2; i++) {
            cout << "\nWrong password";
            cout << "\nYou have " << 2 - i << " attempts left";
            if (passwords())
                goto last;
            if (i == 1) {
                cout << "\n\n\n\t\t\t All attempts failed........";
                cout << "\n\n\t\t\t Sorry, but you can't login";
                exit(0);
            }
        }
    }
    last:
        cout << "\n\n";
    start:
        system("PAUSE");
        system("CLS");
        int opt;
        cout << "\n\n\t\t\t------------------------------------------";
        cout << "\n\t\t\t\tLIBRARY MANAGEMENT SYSTEM";
        cout << "\n\t\t\t------------------------------------------";
        cout << "\n\n\t\t\tWhat do you want to do?";
        cout << "\n\t\t\t1.\tBOOK ISSUE";
        cout << "\n\t\t\t2.\tBOOK DEPOSIT";
        cout << "\n\t\t\t3.\tADMINISTRATOR MENU";
        cout << "\n\t\t\t4.\tExit";
        cout << "\n\n Choose your option: ";
        cin >> opt;
        if (opt == 1) {
            system("CLS");
            book_issue();
            goto start;
        } else if (opt == 2) {
            system("CLS");
            book_deposit();
            goto start;    
        } else if (opt == 3) {
            admin_menu();
            goto start;
        } else if (opt == 4)
            exit(0);
        else {
            cout << "\n\t\tEnter correct option";
            goto start;
        }
}
