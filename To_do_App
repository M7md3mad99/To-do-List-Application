#include <iostream>
#include <vector>
#include <string>

// Task class to represent a single task
class Task {
public:
    std::string description;
    bool isCompleted;

    Task(const std::string& desc) : description(desc), isCompleted(false) {}
};

// ToDoList class to manage multiple tasks
class ToDoList {
private:
    std::vector<Task> tasks;

public:
    void addTask(const std::string& description) {
        tasks.emplace_back(description);
    }

    void markTaskAsCompleted(int index) {
        if (index >= 0 && index < tasks.size()) {
            tasks[index].isCompleted = true;
        } else {
            std::cout << "Invalid task index.\n";
        }
    }

    void viewTasks() const {
        if (tasks.empty()) {
            std::cout << "No tasks in the list.\n";
            return;
        }

        for (size_t i = 0; i < tasks.size(); ++i) {
            std::cout << i + 1 << ". [" << (tasks[i].isCompleted ? "x" : " ") << "] " 
                      << tasks[i].description << '\n';
        }
    }
};

// Function to display the menu and get user choice
int displayMenu() {
    int choice;
    std::cout << "\nTo-Do List Application\n";
    std::cout << "1. Add Task\n";
    std::cout << "2. Mark Task as Completed\n";
    std::cout << "3. View Tasks\n";
    std::cout << "4. Exit\n";
    std::cout << "Enter your choice: ";
    std::cin >> choice;
    std::cin.ignore();  // Ignore the newline character left in the buffer
    return choice;
}

int main() {
    ToDoList todoList;
    int choice;

    do {
        choice = displayMenu();
        switch (choice) {
            case 1: {
                std::string description;
                std::cout << "Enter task description: ";
                std::getline(std::cin, description);
                todoList.addTask(description);
                break;
            }
            case 2: {
                int taskIndex;
                std::cout << "Enter task index to mark as completed: ";
                std::cin >> taskIndex;
                todoList.markTaskAsCompleted(taskIndex - 1);
                break;
            }
            case 3: {
                todoList.viewTasks();
                break;

            }
            case 4: {
                std::cout << "Exiting...\n";
                break;
            }
            default: {
                std::cout << "Invalid choice. Please try again.\n";
                break;
            }
        }
    } while (choice != 4);

    return 0;
}
