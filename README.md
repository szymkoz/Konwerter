# Konwerter
from tkinter import *
from tkinter import messagebox
root=Tk()
root.title("Konwerter")
root.geometry("1280x720")

num=IntVar()
lblbinary=StringVar()
lbloctal=StringVar()
lbldecimal=StringVar()
lblhexa=StringVar()

def convert():
    if num.get()==0:
        messagebox.showerror("Błąd","Musisz podać liczbę aby ją przeliczyć")
    else:
        lblbinary.set(str(bin(num.get())))
        lbloctal.set(str(oct(num.get())))
        lbldecimal.set(str(num.get()))
        lblhexa.set(str(hex(num.get())))
def clear():
    num.set(0)
    lblbinary.set("")
    lbloctal.set("")
    lbldecimal.set("")
    lblhexa.set("")

def exit():
    if messagebox.askyesno("Wyjście","Czy napewno chcesz wyjść?"):
        root.destroy()

Label(root,text="Konwerter systemów liczbowych",font=("times new rommon",60,"bold"),bg="orange",fg="cyan",relief=RIDGE).pack(pady=10)

n=Label(root,text="Podaj liczbę",font=("times new rommon",20,"bold"),fg="cyan")
n.place(x=300,y=150)

b=Label(root,text="Binarny",font=("times new rommon",20,"bold"),fg="cyan")
b.place(x=300,y=230)

d=Label(root,text="Ósemkowy",font=("times new rommon",20,"bold"),fg="cyan")
d.place(x=300,y=310)

h=Label(root,text="Dziesiętny",font=("times new rommon",20,"bold"),fg="cyan")
h.place(x=300,y=390)

o=Label(root,text="Szesnastkowy",font=("times new rommon",20,"bold"),fg="cyan")
o.place(x=300,y=470)

e1=Entry(root,font="arial 20",fg="blue",justify=CENTER,relief=GROOVE,textvariable=num)
e1.place(x=650,y=160)

e2=Entry(root,font="arial 20",fg="blue",justify=CENTER,relief=GROOVE,textvariable=lblbinary)
e2.place(x=650,y=240)

e3=Entry(root,font="arial 20",fg="blue",justify=CENTER,relief=GROOVE,textvariable=lbloctal)
e3.place(x=650,y=320)

e4=Entry(root,font="arial 20",fg="blue",justify=CENTER,relief=GROOVE,textvariable=lbldecimal)
e4.place(x=650,y=400)

e5=Entry(root,font="arial 20",fg="blue",justify=CENTER,relief=GROOVE,textvariable=lblhexa)
e5.place(x=650,y=480)

btn1=Button(root,text="Oblicz",font="arial 20 bold",fg="cyan",bg="orange",width=10,command=convert)
btn1.place(x=300,y=600)

btn2=Button(root,text="Wyczyść",font="arial 20 bold",fg="cyan",bg="orange",width=10,command=clear)
btn2.place(x=600,y=600)

btn3=Button(root,text="Wyjście",font="arial 20 bold",fg="cyan",bg="orange",width=10,command=exit)
btn3.place(x=900,y=600)

root.mainloop()
