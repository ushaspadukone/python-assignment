import tkinter as tk
from tkinter import messagebox

def sort_words():
    input_text = entry.get()
    if not input_text:
        messagebox.showerror("Error", "Please enter a hyphen-separated sequence of words.")
        return

    words = input_text.split("-")
    words.sort()
    sorted_text = "-".join(words)

    result_label.config(
        text=f"Sorted Sequence:\n\n{sorted_text}",
        bg="#d1f7d1",  # Light green background for the result
        fg="#005500",  # Dark green font color
        font=("Courier", 14, "bold"),  # Bold font for the result text
    )
    result_label.place(relx=0.5, rely=0.6, anchor="center")  # Center the result in the window
root = tk.Tk()
root.title("Hyphen-Separated Word Sorter")
root.geometry("600x400")
root.configure(bg="#f2f2f2")
entry_label = tk.Label(
    root, text="Enter hyphen-separated words:", font=("Arial", 14), bg="#f2f2f2", fg="#333333"
)
entry_label.pack(pady=15)
entry = tk.Entry(root, font=("Arial", 16), width=40, relief="solid", justify="center")
entry.pack(pady=10)
sort_button = tk.Button(
    root,
    text="Sort Words",
    font=("Arial", 14, "bold"),
    bg="#4CAF50",  # Green button
    fg="white",
    command=sort_words,
    padx=20,
    pady=10,
)
sort_button.pack(pady=20)
result_label = tk.Label(
    root,
    text="",
    font=("Arial", 14),
    bg="#e6f7ff",  # Light blue background
    fg="#333333",
    relief="solid",
    wraplength=500,
    justify="center",
    width=40,
    height=5,
)
result_label.place(relx=0.5, rely=0.6, anchor="center")  # Centered output
footer_label = tk.Label(
    root,
    text="Developed using Tkinter",
    font=("Arial", 12, "italic"),
    bg="#f2f2f2",
    fg="#666666",
)
footer_label.pack(side="bottom", pady=10)
root.mainloop()
