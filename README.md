# To-Do-List
class TodoList:
    def _init_(self):
        self.tasks = []

    def add_task(self, task):
        self.tasks.append(task)

    def remove_task(self, task_index):
        del self.tasks[task_index]

    def display_tasks(self):
        if not self.tasks:
            print("No tasks found.")
        else:
            for index, task in enumerate(self.tasks):
                print(f"{index + 1}. {task}")

def main():
    todo_list = TodoList()

    while True:
        print("\n1. Add Task")
        print("2. Remove Task")
        print("3. View Tasks")
        print("4. Exit")
        choice = input("Enter your choice: ")

        if choice == '1':
            task = input("Enter task: ")
            todo_list.add_task(task)
        elif choice == '2':
            if todo_list.tasks:
                print("Tasks:")
                todo_list.display_tasks()
                index = int(input("Enter task number to remove: ")) - 1
                if 0 <= index < len(todo_list.tasks):
                    todo_list.remove_task(index)
                else:
                    print("Invalid task number.")
            else:
                print("No tasks to remove.")
        elif choice == '3':
            print("Tasks:")
            todo_list.display_tasks()
        elif choice == '4':
            print("Exiting...")
            break
        else:
            print("Invalid choice. Please try again.")

if _name_ == "_main_":
    main()
