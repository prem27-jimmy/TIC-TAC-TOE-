# # tic_tac_toe_gui.py
import tkinter as tk
from tkinter import messagebox

# Initialize main window
root = tk.Tk()
root.title("Tic Tac Toe")

# Variables
player = "X"
buttons = [[None for _ in range(3)] for _ in range(3)]

# Function to check winner
def check_winner():
    for i in range(3):
        # Check rows
        if buttons[i][0]["text"] == buttons[i][1]["text"] == buttons[i][2]["text"] != "":
            return buttons[i][0]["text"]
        # Check columns
        if buttons[0][i]["text"] == buttons[1][i]["text"] == buttons[2][i]["text"] != "":
            return buttons[0][i]["text"]
    # Check diagonals
    if buttons[0][0]["text"] == buttons[1][1]["text"] == buttons[2][2]["text"] != "":
        return buttons[0][0]["text"]
    if buttons[0][2]["text"] == buttons[1][1]["text"] == buttons[2][0]["text"] != "":
        return buttons[0][2]["text"]
    return None

# Button click function
def click(row, col):
    global player
    if buttons[row][col]["text"] == "":
        buttons[row][col]["text"] = player
        winner = check_winner()
        if winner:
            messagebox.showinfo("Game Over", f"Player {winner} wins!")
            root.destroy()
        else:
            player = "O" if player == "X" else "X"

# Create buttons
for i in range(3):
    for j in range(3):
        buttons[i][j] = tk.Button(root, text="", font=("Arial", 40), width=5, height=2,
                                  command=lambda r=i, c=j: click(r, c))
        buttons[i][j].grid(row=i, column=j)

root.mainloop()

import tkinter as tk
from tkinter import messagebox

# Initialize main window
root = tk.Tk()
root.title("Tic Tac Toe")

# Variables
player = "X"
buttons = [[None for _ in range(3)] for _ in range(3)]

# Function to check winner
def check_winner():
    for i in range(3):
        # Check rows
        if buttons[i][0]["text"] == buttons[i][1]["text"] == buttons[i][2]["text"] != "":
            return buttons[i][0]["text"]
        # Check columns
        if buttons[0][i]["text"] == buttons[1][i]["text"] == buttons[2][i]["text"] != "":
            return buttons[0][i]["text"]
    # Check diagonals
    if buttons[0][0]["text"] == buttons[1][1]["text"] == buttons[2][2]["text"] != "":
        return buttons[0][0]["text"]
    if buttons[0][2]["text"] == buttons[1][1]["text"] == buttons[2][0]["text"] != "":
        return buttons[0][2]["text"]
    return None

# Button click function
def click(row, col):
    global player
    if buttons[row][col]["text"] == "":
        buttons[row][col]["text"] = player
        winner = check_winner()
        if winner:
            messagebox.showinfo("Game Over", f"Player {winner} wins!")
            root.destroy()
        else:
            player = "O" if player == "X" else "X"

# Create buttons
for i in range(3):
    for j in range(3):
        buttons[i][j] = tk.Button(root, text="", font=("Arial", 40), width=5, height=2,
                                  command=lambda r=i, c=j: click(r, c))
        buttons[i][j].grid(row=i, column=j)

root.mainloop()
