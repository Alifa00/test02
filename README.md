#include <iostream>
#include <sstream>
using namespace std;
int main() {
    unsigned int n;
    string ln;
    getline(cin, ln);
    istringstream numstrm(ln);
    if (!(numstrm >> n)) {
        cout << "An error has occuried while reading input data.";
        exit(0);
    }
    getline(cin, ln);
    istringstream massstrm(ln);
    int * mass = new int[n];
    for (int i = 0; i < n; i++) {
        if (!(massstrm >> mass[i])) {
            cout << "An error has occuried while reading input data.";
            exit(0);
        }
    }
    for (int j = 0; j < n / 2; j++) {
        swap(mass[j], mass[n - j - 1]);
    }
    for (int i = 0; i < n; i++) {
        cout << mass[i] << " ";
    }
    return 0;
}


