from plyer import notification 
from tkinter import messagebox 
from tkinter import *

window = Tk()
window.geometry("300x200")
window.title("ODA-CountDown")
#Remove the placeholders for every entry field based on click
def h_click(event):
    hour_entry.delete(0,'end')
def m_click(event):
    min_entry.delete(0,'end')
def s_click(event):
    sec_entry.delete(0,'end')


#Function to activate python countdown timer and show 
#notifications once timer is up
def timer():
    #Since we use placeholders, me chec if user entered an integer
    try:
        timer_time=int(hour_entry.get())*3600 + int(min_entry.get())*60 + int(sec_entryet())
    except:
        messagebox.showerror(message="Enter Valid Time")
    #The user cannot activate a timer with no time set
    #to update the timer wuth every decreasing second and display a notification
    if timer_time > 0:
        hour=0
        min=0
        sec=0
        #If minutes is more than 60, it has to be set to the next hour
        while timer_time >=0:
            min,sec = divmod(timer_time,60)
            if min > 60:
                hour, min = divmod(timer_time,60)
            #set the declared variable with the new values to display
            hours.set(hour)
            mins.set(min)
            secs.set(min)
            #Sleep for 1 creates a diplay of 1 second
            time.sleep(1)
            #Update the changes on the window for every second
            windowx.update()
            #Decrement the timer value by 1
            timer_time -=1
        #create a desktop notification
        notification.notify(
            #title of our notification
            title="Timer ALERT"
            #body 
            message= "Hey is my new Timer",
            timer = 30,
        )
        #this notification stays for 30 seconds
        message.showinfo(message="Timer complete !")

#Creating the user input interface


#LAbel for displaying the title of the app

title_label_1=Label(window,text="Dataflair Countdown timer with notification",font=("Arial",12)).pack()
title_label_2=Label(window,text="Put 0 in fields not of use",font=("Gayathri",10)).pack()
#Variables using which the timer is updates in the function
hours=IntVar()
mins=IntVar()
secs=IntVar()


#To read user input for hours, mins and secs
hour_entry=Entry(window,with=3,textvariable=hours,font(" Arial",18))
min_entry=Entry(window,with=3,textvariable=mins,font("Arial",18))
sec_entry=Entry(window,with=3,textvariable=secs,font("Arial",18))

#Placeholders for the entry widgets
hour_entry.insert(0,00)
min_entry.insert(0,00)
sec_entry.insert(0,00)

#Positioning the entry widgets
hour_entry.place(x=80,y=40)
min_entry.place(x=130,y=40)
sec_entry.place(x=180,y=40)

#To link the defined placholder removal functions on mouse click
hour_entry.bind("<1>",h_click)
min_entry.bind("<1>",m_click)
sec_entry.bind("<1>",s_click)

#Add of a button to activate the timer
#Active
button=Button(window, text="Activate Timer", bg"Red", command=timer).pack(pady=40)
#Close the window and exit the app
window.mainloop()
