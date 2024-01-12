# Bharat_Intern
#App development 
from tkinter import *

# Create the main window
root = Tk()
root.title("Floral To-Do List")
root.configure(bg="#F5EFE8")

# Create the task list
tasks = []

# Define functions for adding, editing, and deleting tasks
def add_task():
    task = entry.get()
    if task != "":
        tasks.append(task)
        update_listbox()

def edit_task():
    selected_task = listbox.curselection()
    if selected_task:
        task = entry.get()
        tasks[selected_task[0]] = task
        update_listbox()

def delete_task():
    selected_task = listbox.curselection()
    if selected_task:
        tasks.pop(selected_task[0])
        update_listbox()

# Define function for updating the listbox
def update_listbox():
    listbox.delete(0, END)
    for task in tasks:
        listbox.insert(END, task)

# Create the user interface
frame1 = Frame(root, bg="#F5EFE8")
frame1.pack(pady=10)

label = Label(frame1, text="Add a task:", bg="#F5EFE8", font=("Arial", 12))
label.pack(side=LEFT, padx=10)

entry = Entry(frame1, width=30, font=("Arial", 12))
entry.pack(side=LEFT)

button1 = Button(frame1, text="Add", bg="#F5EFE8", font=("Arial", 12), command=add_task)
button1.pack(side=LEFT, padx=10)

button2 = Button(frame1, text="Edit", bg="#F5EFE8", font=("Arial", 12), command=edit_task)
button2.pack(side=LEFT)

button3 = Button(frame1, text="Delete", bg="#F5EFE8", font=("Arial", 12), command=delete_task)
button3.pack(side=LEFT, padx=10)

frame2 = Frame(root, bg="#F5EFE8")
frame2.pack(pady=10)

label2 = Label(frame2, text="To-Do List:", bg="#F5EFE8", font=("Arial", 12))
label2.pack(side=LEFT, padx=10)

scrollbar = Scrollbar(frame2)
scrollbar.pack(side=RIGHT, fill=Y)

listbox = Listbox(frame2, width=50, height=10, font=("Arial", 12), yscrollcommand=scrollbar.set)
listbox.pack(side=LEFT)

scrollbar.config(command=listbox.yview)

root.mainloop()
