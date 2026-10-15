# bai-tap-15-10
#include <iostream>
#include <fstream>
#include <iomanip>

using namespace std;

const int MAX = 100;

void Nhap(string filename, int A[][MAX], int &n) {
    ifstream file(filename);
    if (!file.is_open()) {
        cout << "Khong the mo file " << filename << "! Vui long kiem tra lai.\n";
        return;
    }
    
    file >> n;
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            file >> A[i][j];
        }
    }
    
    file.close();
}

void HienThi(int A[][MAX], int n) {
    cout << "So dinh cua do thi: " << n << "\n";
    cout << "Ma tran trong so cua do thi:\n\n";
    
    cout << setw(6) << "";
    for (int i = 0; i < n; i++) {
        cout << setw(6) << (char)('A' + i);
    }
    cout << "\n";
    
    cout << setw(6) << "";
    for (int i = 0; i <= n; i++) {
        cout << "------";
    }
    cout << "\n";
    
    for (int i = 0; i < n; i++) {
        cout << setw(6) << (char)('A' + i);
        for (int j = 0; j < n; j++) {
            cout << setw(6) << A[i][j];
        }
        cout << "\n";
    }
}

int main() {
    int A[MAX][MAX];
    int n = 0;
    
    Nhap("Grap.txt", A, n);
    
    HienThi(A, n);
    
    return 0;
}
