# C-
C++ repository with Matrix Effect
#include <iostream>
#include <cstdlib>
#include <ctime>
#include <windows.h> // for sleep function

using namespace std;

void matrixEffect() {
    const int screenWidth = 80;
    const int screenHeight = 25;
    
    char screen[screenWidth][screenHeight];
    
    for (int y = 0; y < screenHeight; ++y) {
        for (int x = 0; x < screenWidth; ++x) {
            screen[x][y] = ' ';
        }
    }
    
    const string message = "You are hacked!";
    const int messageLength = message.length();
    
    for (int i = 0; i < 200; ++i) { // number of iterations for the effect
        for (int y = 0; y < screenHeight; ++y) {
            for (int x = 0; x < screenWidth; ++x) {
                if (y >= i && y < i + messageLength) {
                    screen[x][y - i] = message[y - i];
                }
                
                cout << screen[x][y];
            }
            cout << endl;
        }
        
        Sleep(50); // sleep for 50 milliseconds
        system("cls"); // clear screen
    }
}

int main() {
    matrixEffect();
    return 0;
} 
