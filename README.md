//GPACalculator

#include <iostream>
#include <string>
using namespace std;






float getGradePoint(int score) {
    if (score >= 80 && score <= 100) return 4.0;
    else if (score >= 75) return 3.5;
    else if (score >= 70) return 3.0;
    else if (score >= 65) return 2.5;
    else if (score >= 60) return 2.0;
    else if (score >= 55) return 1.5;
    else if (score >= 50) return 1.0;
    else if (score >= 45) return 0.5;
    else return 0.0;
}

string getGradeLetter(int score) {
    if (score >= 80 && score <= 100) return "A";
    else if (score >= 75) return "B+";
    else if (score >= 70) return "B";
    else if (score >= 65) return "C+";
    else if (score >= 60) return "C";
    else if (score >= 55) return "D+";
    else if (score >= 50) return "D";
    else if (score >= 45) return "E";
    else return "F";
}

int main() {
    const int numCourses = 8;
    string studentname;
    int score;
    float creditHours, totalPoints = 0, totalCredits = 0;

    for (int i = 1; i <= numCourses; i++) {
        cout << "Enter score for Course : ";
        cin >> score;

        cout << "Enter credit hours for Course " << i << ": ";
        cin >> creditHours;

        float gradePoint = getGradePoint(score);
        string gradeLetter = getGradeLetter(score);

        totalPoints += gradePoint * creditHours;
        totalCredits += creditHours;

        cout << "Grade: " << gradeLetter << " (Grade Point: " << gradePoint << ")" << endl << endl;
    }

    float GPA = totalPoints / totalCredits;

    cout<< "Student name"<< studentname;
    cout << "Your GPA is: " << GPA << endl;

    return 0;
}