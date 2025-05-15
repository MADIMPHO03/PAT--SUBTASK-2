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

    // Get the third temperature reading
    std::cout << "Enter third temperature reading: ";
    std::cin >> temp3;

    // Check if the final temperature is within the correct frying range
    if (temp3 >= 150 && temp3 <= 190) {
        std::cout << "You may start frying the Magwinyas.\n";
    } else {
        std::cout << "Oil is not ready for frying!\n";
    }

    return 0;
}

