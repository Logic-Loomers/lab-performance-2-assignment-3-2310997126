[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/Fmb6W2KK)
Design a C++ program for an employee payroll system. Create classes for Employee and Payroll. Users can add employees, enter hours worked, calculate salaries, and generate payroll reports.
#include <iostream>
#include <string>
#include <vector>

using namespace std;

class Employee {
public:
    string name;
    double hourlyRate;
    double hoursWorked;

    Employee(string _name, double _hourlyRate) : name(_name), hourlyRate(_hourlyRate), hoursWorked(0) {}

    double calculateSalary() {
        return hourlyRate * hoursWorked;
    }
};

class Payroll {
public:
    vector<Employee> employees;

    void addEmployee(const Employee& emp) {
        employees.push_back(emp);
    }

    void enterHoursWorked(const string& name, double hours) {
        for (auto& emp : employees) {
            if (emp.name == name) {
                emp.hoursWorked = hours;
                return;
            }
        }
        cout << "Employee not found." << endl;
    }

    void generatePayrollReport() {
        cout << "Payroll Report:" << endl;
        for ( auto& emp : employees) {
            cout << "Employee Name: " << emp.name << endl;
            cout << "Hours Worked: " << emp.hoursWorked << endl;
            cout << "Salary: " << emp.calculateSalary() << endl;
            cout << endl;
        }
    }
};

int main() {
    Payroll payroll;
    payroll.addEmployee(Employee("JASLEEN", 20.0));
    payroll.addEmployee(Employee("NANCY", 25.0));


    payroll.enterHoursWorked("JASLEEN", 40);
    payroll.enterHoursWorked("NANCY", 35);


    payroll.generatePayrollReport();

    return 0;
}
