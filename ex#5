#include <iostream>
#include <fstream>
#include <string>
#include <vector>
#include <regex>

using namespace std;

class myString {
private:
    string m_str;
public:
    myString(string s) {
        m_str = s;
    }
};

class ReadClass {
public:
    void showClass() {
        ifstream file("main.cpp");
        if (!file.is_open()) {
            cerr << "Unable to open file main.cpp" << endl;
            return;
        }

        string line;
        regex class_regex(R"(\bclass\s+(\w+))");
        smatch match;
        vector<string> class_names;

        while (getline(file, line)) {
            if (regex_search(line, match, class_regex)) {
                class_names.push_back(match[1]);
            }
        }

        file.close();

        cout << "Number of classes: " << class_names.size() << endl;
        for (const auto& name : class_names) {
            cout << "Class name: " << name << endl;
        }
    }
};

int main() {
    ReadClass rfile;
    rfile.showClass();
    return 0;
}
