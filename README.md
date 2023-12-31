# Calculator-Generator
import tkinter as tk

root = tk.Tk()
root.title(" Calculator")

frame = tk.Frame(root)
frame.pack(padx=15,pady=15)

for i in range(5):
    frame.rowconfigure(i,pad=10)
    
def click(value):
    entry.insert(tk.END,value)
def clear():
    entry.delete(0,tk.END)
def calculate():
    Ans = eval(entry.get())
    entry.delete(0,tk.END)
    entry.insert(tk.END,str(Ans))
    
    
    
entry = tk.Entry(frame,width=50)
entry.grid(row=0,column=0,columnspan=4)

buttons = [
           ("7",1,0),("8",1,1),("9",1,2),("+",1,3),
           ("4",2,0),("5",2,1),("6",2,2),("-",2,3),
           ("1",3,0),("2",3,1),("3",3,2),("*",3,3),
           ("0",4,0),("00",4,1),(".",4,2),("/",4,3)
          ]
    

for text,row,column in buttons:
    button = tk.Button(frame,text=text,padx=20,pady=15,command=lambda t=text:click(t),bg='black',fg='white')
    button.grid(row=row,column=column)
    
    
    
    
clear_display = tk.Button(frame,text="C",padx=20,pady=15,command=clear)
clear_display .grid(row=5,column=3)




equal_button = tk.Button(frame,text="=",padx=20,pady=15,command=calculate)
equal_button.grid(row=5,column=3)




clear_button = tk.Button(frame,text="AC",padx=20,pady=15,command=clear,fg='black')
clear_button.grid(row=5,column=0)
root.mainloop()
