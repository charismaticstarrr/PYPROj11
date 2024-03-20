# PYPROj11
class ToDoListManager:
    def __init__(self):
        self.tasks = []

    def add_task(self, task):
        self.tasks.append(task)
        print("New task added successfully!")

    def view_tasks(self):
        if not self.tasks:
            print("No tasks found. Your ToDo list is empty.")
        else:
            print("Your ToDo List:")
            for index, task in enumerate(self.tasks, start=1):
                print(f"{index}. {task}")

    def update_task(self, index, new_task):
        if 1 <= index <= len(self.tasks):
            self.tasks[index - 1] = new_task
            print("Task updated successfully!")
        else:
            print("Invalid task index. Please try again.")

    def delete_task(self, index):
        if 1 <= index <= len(self.tasks):
            del self.tasks[index - 1]
            print("Task deleted successfully!")
        else:
            print("Invalid task index. Please try again.")

def main():
    todo_manager = ToDoListManager()
    
    while True:
        print("\nWelcome to the ToDo List Manager")
        print("1. Add a New Task")
        print("2. View Your Tasks")
        print("3. Update a Task")
        print("4. Delete a Task")
        print("5. Exit")

        choice = input("Enter your choice (1-5): ")

        if choice == '1':
            task = input("Enter the new task: ")
            todo_manager.add_task(task)
        elif choice == '2':
            todo_manager.view_tasks()
        elif choice == '3':
            index = int(input("Enter the index of the task to update: "))
            new_task = input("Enter the updated task: ")
            todo_manager.update_task(index, new_task)
        elif choice == '4':
            index = int(input("Enter the index of the task to delete: "))
            todo_manager.delete_task(index)
        elif choice == '5':
            print("Thank you for using ToDo List Manager. Have a great day!")
            break
        else:
            print("Invalid choice. Please enter a number between 1 and 5.")

if __name__ == "__main__":
    main()
