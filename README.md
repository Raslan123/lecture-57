# lecture-57
#include <iostream>
using namespace std;

// Define the Node class
class Node {
public:
    int data;
    Node* next;

    Node(int data) {
        this->data = data;
        this->next = nullptr;
    }
};

// Define the LinkedList class
class LinkedList {
private:
    Node* head;

public:
    LinkedList() {
        head = nullptr;
    }

    // Function to insert a node at the start
    void insertAtStart(int data) {
        Node* newNode = new Node(data);
        newNode->next = head;
        head = newNode;
    }

    // Function to insert a node at the end
    void insertAtEnd(int data) {
        Node* newNode = new Node(data);
        if (head == nullptr) {
            head = newNode;
        } else {
            Node* temp = head;
            while (temp->next != nullptr) {
                temp = temp->next;
            }
            temp->next = newNode;
        }
    }

   

    // Function to display the linked list
    void displayList() {
        Node* temp = head;
        while (temp != nullptr) {
            cout << temp->data << " -> ";
            temp = temp->next;
        }
        cout << "NULL" << endl;
    }
};

int main() {
    LinkedList list;

    // Insert elements at the start
    list.insertAtStart(10);
    list.insertAtStart(20);
    list.insertAtStart(30);
    list.displayList();


    // Insert elements at the end
    list.insertAtEnd(40);
    list.insertAtEnd(50);
    list.displayList();


    

    return 0;
}
