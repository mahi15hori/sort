#include <iostream>
using namespace std;

void simpleSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        for (int j = i + 1; j < n; j++) {
            if (arr[j] < arr[i]) swap(arr[i], arr[j]);
        }
    }
}

void bubbleSort(int arr[], int n) {
    bool swapped;
    for (int i = 0; i < n - 1; i++) {
        swapped = false;
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                swap(arr[j], arr[j + 1]);
                swapped = true;
            }
        }
        if (!swapped) break;
    }
}

void insertionSort(int arr[], int n) {
    for (int i = 1; i < n; i++) {
        int temp = arr[i], j = i - 1;
        while (j >= 0 && arr[j] > temp) {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = temp;
    }
}

void selectionSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        int minIndex = i;
        for (int j = i + 1; j < n; j++) {
            if (arr[j] < arr[minIndex]) minIndex = j;
        }
        swap(arr[i], arr[minIndex]);
    }
}

void printArray(int arr[], int n) {
    for (int i = 0; i < n; i++) cout << arr[i] << " ";
    cout << endl;
}

int main() {
    int n;
    cout << "Enter number of elements: ";
    cin >> n;

    int arr[100], temp[100];
    cout << "Enter elements: ";
    for (int i = 0; i < n; i++) cin >> arr[i];

    for (int i = 0; i < n; i++) temp[i] = arr[i];
    cout << "Simple Sort: "; simpleSort(temp, n); printArray(temp, n);

    for (int i = 0; i < n; i++) temp[i] = arr[i];
    cout << "Bubble Sort: "; bubbleSort(temp, n); printArray(temp, n);

    for (int i = 0; i < n; i++) temp[i] = arr[i];
    cout << "Insertion Sort: "; insertionSort(temp, n); printArray(temp, n);

    for (int i = 0; i < n; i++) temp[i] = arr[i];
    cout << "Selection Sort: "; selectionSort(temp, n); printArray(temp, n);

    return 0;
}
