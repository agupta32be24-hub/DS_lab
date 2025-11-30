#include <iostream>
using namespace std;

// Q1. Implement Heap Sort (Increasing/Decreasing Order)
class HeapSort {
public:
    void heapify(int arr[], int n, int i, bool increasing) {
        int extreme = i;
        int left = 2 * i + 1;
        int right = 2 * i + 2;

        if (increasing) {
            if (left < n && arr[left] > arr[extreme]) extreme = left;
            if (right < n && arr[right] > arr[extreme]) extreme = right;
        } else {
            if (left < n && arr[left] < arr[extreme]) extreme = left;
            if (right < n && arr[right] < arr[extreme]) extreme = right;
        }

        if (extreme != i) {
            int temp = arr[i];
            arr[i] = arr[extreme];
            arr[extreme] = temp;
            heapify(arr, n, extreme, increasing);
        }
    }

    void heapSort(int arr[], int n, bool increasing) {
        for (int i = n / 2 - 1; i >= 0; i--) heapify(arr, n, i, increasing);
        for (int i = n - 1; i >= 0; i--) {
            int temp = arr[0];
            arr[0] = arr[i];
            arr[i] = temp;
            heapify(arr, i, 0, increasing);
        }
    }

    void display(int arr[], int n) {
        for (int i = 0; i < n; i++) cout << arr[i] << " ";
        cout << "\n";
    }
};

int main() {
    HeapSort hs;
    int arr[100], n, order;
    cout << "Enter size: ";
    cin >> n;
    cout << "Enter elements: ";
    for (int i = 0; i < n; i++) cin >> arr[i];
    cout << "1. Increasing Order\n2. Decreasing Order: ";
    cin >> order;
    bool inc = (order == 1);
    hs.heapSort(arr, n, inc);
    hs.display(arr, n);
    return 0;
}

------------------------------------------------------------

// Q2. Implement Priority Queue using Heap
#include <iostream>
using namespace std;

class PriorityQueueHeap {
    int arr[100];
    int size;

    void heapifyUp(int index) {
        while (index > 0) {
            int parent = (index - 1) / 2;
            if (arr[index] > arr[parent]) {
                int temp = arr[index];
                arr[index] = arr[parent];
                arr[parent] = temp;
                index = parent;
            } else break;
        }
    }

    void heapifyDown(int index) {
        int largest = index;
        int left = 2 * index + 1;
        int right = 2 * index + 2;

        if (left < size && arr[left] > arr[largest]) largest = left;
        if (right < size && arr[right] > arr[largest]) largest = right;

        if (largest != index) {
            int temp = arr[index];
            arr[index] = arr[largest];
            arr[largest] = temp;
            heapifyDown(largest);
        }
    }

public:
    PriorityQueueHeap() { size = 0; }

    void insert(int val) {
        arr[size] = val;
        size++;
        heapifyUp(size - 1);
    }

    int extractMax() {
        if (size == 0) {
            cout << "Queue Empty\n";
            return -1;
        }
        int maxVal = arr[0];
        arr[0] = arr[size - 1];
        size--;
        heapifyDown(0);
        return maxVal;
    }

    int peek() {
        if (size == 0) {
            cout << "Queue Empty\n";
            return -1;
        }
        return arr[0];
    }

    void display() {
        for (int i = 0; i < size; i++) cout << arr[i] << " ";
        cout << "\n";
    }
};

int main() {
    PriorityQueueHeap pq;
    int choice, val;
    do {
        cout << "\n1.Insert\n2.Extract Max\n3.Peek\n4.Display\n0.Exit\nEnter choice: ";
        cin >> choice;
        switch (choice) {
        case 1:
            cout << "Enter value: ";
            cin >> val;
            pq.insert(val);
            break;
        case 2:
            cout << "Removed: " << pq.extractMax() << "\n";
            break;
        case 3:
            cout << "Top: " << pq.peek() << "\n";
            break;
        case 4:
            pq.display();
            break;
        }
    } while (choice != 0);
    return 0;
}
