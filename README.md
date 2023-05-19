from tkinter import *
import speedtest

sp = Tk()
sp.title(" Internet Speed test")
sp.geometry("500x700")
sp.config(bg="black")

def speedcheck():
    sp=speedtest.Speedtest()
    sp.get_servers()
    down =str(round(sp.download()/(10**6),3))+" mbps"
    up =str(round(sp.upload()/(10**6),3))+" mbps"
    lab_down.config(text=down)
    lab_up.config(text=up)


lab=Label(sp,text="Internet Speed test",font=("Time new roman ",30,"bold"),
                 bg="Black",fg="yellow")
lab.place(x=60,y=40,height=50,width=380)

lab=Label(sp,text="Download speed",font=("Time new roman ",30,"bold"))
lab.place(x=60,y=130,height=50,width=380)

lab_down=Label(sp,text="00",font=("Time new roman ",30,"bold"))
lab_down.place(x=60,y=200,height=50,width=380)

lab=Label(sp,text="Upload speed",font=("Time new roman ",30,"bold"))
lab.place(x=60,y=290,height=50,width=380)

lab_up=Label(sp,text="00",font=("Time new roman ",30,"bold"))
lab_up.place(x=60,y=360,height=50,width=380)

button = Button(sp,text="check Speed",font=("Time new roman ",30,"bold"),
                relief=RAISED,bg="Red",command=speedcheck)
button.place(x=60,y=460,height=50,width=380)

sp.mainloop()
