#include <iostream>

int main() {
    int temp1, temp2, temp3;
#implemented temperature input validation
    // Get the first temperature reading
    std::cout << "Enter first temperature reading: ";
    std::cin >> temp1;

    // Get the second temperature reading
    std::cout << "Enter second temperature reading: ";
    std::cin >> temp2;
#added checks for gradual heating adjustments
    // Check the difference between first and second reading
    if (temp2 - temp1 > 50) {
        std::cout << "Reduce fryer heat before taking the third reading.\n";
    } else if (temp2 - temp1 < 10) {
        std::cout << "Increase the Fryer heat before taking the third reading.\n";
    }
#optimized user prompts for better clarity
    // Get the third temperature reading
    std::cout << "Enter third temperature reading: ";
    std::cin >> temp3;
# included final temperature range verification for fring readiness
    // Check if the final temperature is within the correct frying range
    if (temp3 >= 150 && temp3 <= 190) {
        std::cout << "You may start frying the Magwinyas.\n";
    } else {
        std::cout << "Oil is not ready for frying!\n";
    }

    return 0;
}

#include <iostream>
#include <string>
#include <cctype>
using namespace std;

// Morse code for A-Z using '.' (ASCII 46) and '-' (ASCII 45)
string morse[] = {
    ".-", "-...", "-.-.", "-..", ".", "..-.", "--.", "....", "..", ".---",
    "-.-", ".-..", "--", "-.", "---", ".--.", "--.-", ".-.", "...", "-",
    "..-", "...-", ".--", "-..-", "-.--", "--.."
};

int main() {
    string msg;
    cout << "Enter a short message in English: ";
    getline(cin, msg);

    string fullMorse = "";

    for (char c : msg) {
        if (isalpha(c)) {
            c = toupper(c);
            string code = morse[c - 'A'];
            cout << c << ": " << code << endl;
            fullMorse += code + "   "; // 3 spaces between letters
        }
    }

    cout << "\nFull Morse code with spaces:\n" << fullMorse << endl;
    return 0;
}

#include <iostream>
using namespace std;

const int NUM_EXPERIMENTS = 4;
const int NUM_READINGS = 3;

int main() {
    float readingValue, total, average;

    for (int experiment = 1; experiment <= NUM_EXPERIMENTS; ++experiment) {
        cout << "\nEXPERIMENT " << experiment << endl;
        total = 0;

        for (int reading = 1; reading <= NUM_READINGS; ++reading) {
            cout << " Enter reading " << reading << " value: ";
            cin >> readingValue;
            total += readingValue;
        }

        average = total / NUM_READINGS;

        // Display average
        cout << " Average for Experiment " << experiment << ": " << average << endl;

        // Evaluation logic
        if (average < 100) {
            cout << " Result: Below acceptable range" << endl;
        } else if (average <= 300) {
            cout << " Result: Within acceptable range" << endl;
        } else {
            cout << " Result: Above acceptable range" << endl;
        }
    }

    cout << "\nAll experiments completed." << endl;
    return 0;
}
