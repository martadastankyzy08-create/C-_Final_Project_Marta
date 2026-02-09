# C-_Final_Project_Marta
This is the final c++ project
#include <iostream>
#include <cstdlib>
#include <ctime>

using namespace std;

int main() {
    srand(time(0));

    int score = 0;
    int totalQuestions = 10;
    int level;

    cout << "🎮 Welcome to the Kids Math Game!\n";
    cout << "Choose Difficulty Level:\n";
    cout << "1. Easy\n2. Medium\n3. Hard\n";
    cout << "Enter your choice: ";
    cin >> level;

    int maxAddSub, maxMul;

    // Set difficulty ranges
    if (level == 1) {
        maxAddSub = 10;
        maxMul = 5;
        cout << "\n✅ Easy Mode Selected!\n\n";
    }
    else if (level == 2) {
        maxAddSub = 50;
        maxMul = 10;
        cout << "\n⚡ Medium Mode Selected!\n\n";
    }
    else {
        maxAddSub = 200;
        maxMul = 15;
        cout << "\n🔥 Hard Mode Selected!\n\n";
    }

    for (int i = 1; i <= totalQuestions; i++) {

        int num1, num2;
        int operation = rand() % 4;
        int correctAnswer;
        char opSymbol;

        // Addition
        if (operation == 0) {
            num1 = rand() % maxAddSub + 1;
            num2 = rand() % maxAddSub + 1;
            correctAnswer = num1 + num2;
            opSymbol = '+';
        }

        // Subtraction
        else if (operation == 1) {
            num1 = rand() % maxAddSub + 1;
            num2 = rand() % maxAddSub + 1;
            if (num2 > num1) swap(num1, num2);
            correctAnswer = num1 - num2;
            opSymbol = '-';
        }

        // Multiplication
        else if (operation == 2) {
            num1 = rand() % maxMul + 1;
            num2 = rand() % maxMul + 1;
            correctAnswer = num1 * num2;
            opSymbol = '*';
        }

        // Division (whole number only)
        else {
            num2 = rand() % maxMul + 1;
            correctAnswer = rand() % maxMul + 1;
            num1 = num2 * correctAnswer;
            opSymbol = '/';
        }

        int userAnswer;
        cout << "Question " << i << ": "
             << num1 << " " << opSymbol << " " << num2 << " = ";
        cin >> userAnswer;

        if (userAnswer == correctAnswer) {
            cout << "✅ Correct!\n\n";
            score++;
        } else {
            cout << "❌ Wrong! Correct answer: "
                 << correctAnswer << "\n\n";
        }
    }

    cout << "🎯 Game Over!\n";
    cout << "Final Score: " << score << " / " << totalQuestions << endl;

    return 0;
}
✦✦✦✦✦✦✦✦✦✦✦

