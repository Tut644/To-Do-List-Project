tasks = []  # Global list to store tasks

def addTask():
    #Function for adding new tasks.
    newTask = input("Please enter a task: ") #Takes user input
    tasks.append(newTask) #Adding new task to the global list
    print(f'Task "{newTask}" added to the list.') #Confirmation of task addition

def listTasks():
    #Function to list all tasks.
    if not tasks:
        print("There are no tasks in the list.") # this is if the list is empty
    else:
        print("\nCurrent Tasks:")
        for index, task in enumerate(tasks):  # Loop through tasks with index
            print(f'Task #{index}: {task}')  # Display task number and content
        print()  # Adds a blank line for better readability

def deleteTask():
    #Function to delete a task based on index.
    listTasks()  # Show tasks before deletion
    if tasks:   # Ensure list is not empty
        try:
            index = int(input("Enter the task number to delete: "))  # User inputs index
            if 0 <= index < len(tasks):  # Validate index range
                removeTask = tasks.pop(index)  # Remove task from list
                print(f'Task "{removeTask}" has been removed.')   # Confirm deletion
            else:
                print("Invalid task number. Please try again.")  # Invalid index error
        except ValueError:
            print("Invalid input. Please enter a valid number.")   # Non-numeric input error

def main():
    #Main function to display the menu and take user input.
    while True:
        print("\nTo-Do List Menu:")
        print("1. Add Task")
        print("2. List Tasks")
        print("3. Delete Task")
        print("4. Exit")

        choice = input("Enter your choice (1-4): ")

        if choice == "1":
            addTask()    # Call add task function
        elif choice == "2":
            listTasks()    # Call list tasks function
        elif choice == "3":
            deleteTask()  # Call delete task function
        elif choice == "4":
            print("Exiting program. Goodbye!")  # Exit message
            break    # Break loop to exit
        else:
            print("Invalid choice. Please enter a number between 1 and 4.")   # Handle invalid input

# Run the program
if __name__ == "__main__":
     main()
