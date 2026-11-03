

**# Text Editor App in Python**



**import tkinter as tk**

**from tkinter import filedialog, messagebox**





**def new\_file():**

&#x20;   **text.delete(1.0, tk.END)**





**def open\_file():**

&#x20;   **file\_path = filedialog.askopenfilename(**

&#x20;       **defaultextension=".txt",**

&#x20;       **filetypes=\[("Text Files", "\*.txt")]**

&#x20;   **)**



&#x20;   **if file\_path:**

&#x20;       **with open(file\_path, 'r') as file:**

&#x20;           **text.delete(1.0, tk.END)**

&#x20;           **text.insert(tk.END, file.read())**





**def save\_file():**

&#x20;   **file\_path = filedialog.asksaveasfilename(**

&#x20;       **defaultextension=".txt",**

&#x20;       **filetypes=\[("Text Files", "\*.txt")]**

&#x20;   **)**



&#x20;   **if file\_path:**

&#x20;       **with open(file\_path, 'w') as file:**

&#x20;           **file.write(text.get(1.0, tk.END))**



&#x20;       **messagebox.showinfo("Info", "File Saved Successfully!")**





**root = tk.Tk()**

**root.title("Simple Text Editor")**

**root.geometry("800x600")**



**menu = tk.Menu(root)**

**root.config(menu=menu)**



**file\_menu = tk.Menu(menu, tearoff=0)**



**menu.add\_cascade(label="File", menu=file\_menu)**

**file\_menu.add\_command(label="New", command=new\_file)**

**file\_menu.add\_command(label="Open", command=open\_file)**

**file\_menu.add\_command(label="Save", command=save\_file)**

**file\_menu.add\_separator()**

**file\_menu.add\_command(label="Exit", command=root.quit)**



**text = tk.Text(**

&#x20;   **root,**

&#x20;   **wrap=tk.WORD,**

&#x20;   **font=("Helvetica", 12),**

&#x20;   **fg="blue"**

**)**

**text.pack(expand=tk.YES, fill=tk.BOTH)**



**root.mainloop()**



