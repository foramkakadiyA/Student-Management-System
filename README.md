#include <iostream>
using namespace std;

class Student {
public:
    int id;
    string name;

    void input() {
        cout << "Enter ID: ";
        cin >> id;
        cout << "Enter Name: ";
        cin >> name;
    }

    void display() {
        cout << "ID: " << id << " Name: " << name << endl;
    }
};

int main() {
    Student s[100];
    int count = 0, choice, searchId;

    while (true) {
        cout << "\n1. Add Student\n2. Display\n3. Search\n4. Exit\n";
        cin >> choice;

        switch (choice) {
        case 1:
            s[count].input();
            count++;
            break;

        case 2:
            for (int i = 0; i < count; i++) {
                s[i].display();
            }
            break;

        case 3:
            cout << "Enter ID to search: ";
            cin >> searchId;
            for (int i = 0; i < count; i++) {
                if (s[i].id == searchId) {
                    s[i].display();
                }
            }
            break;

        case 4:
            return 0;
        }
    }
}
