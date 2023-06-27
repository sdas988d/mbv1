# mbv1
mbv one
class Task:
    def __init__(self, title, description):
        self.title = title
        self.description = description
        self.completed = False

class TaskManager:
    def __init__(self):
        self.tasks = []

    def add_task(self, title, description):
        task = Task(title, description)
        self.tasks.append(task)
        print("Task added successfully.")

    def complete_task(self, title):
        for task in self.tasks:
            if task.title == title:
                task.completed = True
                print("Task completed.")
                return
        print("Task not found.")

    def display_tasks(self):
        print("Task List:")
        for task in self.tasks:
            status = "Completed" if task.completed else "Incomplete"
            print("Title:", task.title)
            print("Description:", task.description)
            print("Status:", status)
            print()

# 示例用法
manager = TaskManager()
manager.add_task("Task 1", "Finish project report")
manager.add_task("Task 2", "Buy groceries")
manager.display_tasks()
manager.complete_task("Task 1")
manager.complete_task("Task 3")
manager.display_tasks()
