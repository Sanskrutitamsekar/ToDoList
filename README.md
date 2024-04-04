# ToDoList
class TodoList:
    def __init__(self):
        self.tasks = []

    def add_task(self, task):
        self.tasks.append({"task": task, "completed": False})

    def complete_task(self, index):
        if 0 <= index < len(self.tasks):
            self.tasks[index]["completed"] = True
            print("Task completed:", self.tasks[index]["task"])
        else:
            print("Invalid task index")

    def remove_task(self, index):
        if 0 <= index < len(self.tasks):
            del self.tasks[index]
            print("Task removed")
        else:
            print("Invalid task index")

    def display_tasks(self):
        print("To-Do List:")
        for i, task in enumerate(self.tasks):
            status = "Completed" if task["completed"] else "Pending"
            print(f"{i + 1}. {task['task']} - {status}")


def main():
    todo_list = TodoList()

    while True:
        print("\n1. Add Task")
        print("2. Complete Task")
        print("3. Remove Task")
        print("4. Display Tasks")
        print("5. Exit")

        choice = input("Please enter your choice: ")

        if choice == '1':
            task = input("Please enter task: ")
            todo_list.add_task(task)
        elif choice == '2':
            index = int(input("Please enter task index to mark as completed: ")) - 1
            todo_list.complete_task(index)
        elif choice == '3':
            index = int(input("Please enter task index to remove: ")) - 1
            todo_list.remove_task(index)
        elif choice == '4':
            todo_list.display_tasks()
        elif choice == '5':
            print("Exiting")
            break
        else:
            print("Choice is Invaid")


if __name__ == "__main__":
    main()
