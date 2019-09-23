# calceulatro
# project-calculator
#bach thsbli lar9am
# now project calculator 
import tkinter
from tkinter import ttk
from tkinter import *

met = tkinter.Tk()
met.title('calculator :)')  # title de forme
met.geometry('600x300')  # size the forme
met.config(background='light blue')  # color de bg
#######################################################################

###########################################################################
sv1 = tkinter.StringVar()
sv2 = tkinter.StringVar()
#lbele1 and 2
fnt = ('tahoma',16)
lbl1 = Label(met,text ='enter yor number 1 : ',bg = 'light blue',font = fnt)
lbl2 = Label(met,text ='enter yor number 2 : ',bg = 'light blue',font = fnt)
sv1.set('0')
sv2.set('0')
#enter 1 and 2
tx1 = Entry(met,font = fnt,textvariable = sv1)
tx2 = Entry(met,font = fnt,textvariable = sv2)
#######################################################
lbl1.grid(row = 0,column = 0,pady = 10,padx = 10)
lbl2.grid(row = 1,column = 0,pady = 10,padx = 10)
#####################################################
tx1.grid(row = 0,column = 1)
tx2.grid(row = 1,column = 1)
#####################################################
def calc(ope):
    strn1 = str(tx1.get())
    strn2 = str(tx2.get())
    n1 = int(strn1)
    n2 = int(strn2)
    r = 0
    if ope == '+': r = n1 + n2
    elif ope == '-': r = n1 - n2
    elif ope == '*': r = n1 * n2
    else:
        if n2 == 0: n2 = 1
        r = n1 / n2
    lb['text']=('resolte : %s %s %s = %s' %(n1,ope,n2,r))





#######################################################################
bton = ttk.Style()
bton.configure('TButton',font = fnt,padding = 10)
frem = tkinter.Frame(met)

buttonadd = ttk.Button(frem,text = '+',command = lambda :(calc('+')))
buttonnaks = ttk.Button(frem,text = '-',command = lambda :(calc('-')))
buttondarb= ttk.Button(frem,text = '*',command = lambda :(calc('*')))
buttonkisma = ttk.Button(frem,text = '/',command = lambda :(calc('/')))

frem.grid(row = 2,column = 0,columnspan = 2)
buttonadd.grid(row = 0,column = 0)
buttonnaks.grid(row = 0,column = 1)
buttondarb.grid(row = 0,column = 2)
buttonkisma.grid(row = 0,column = 3)

lb = ttk.Label(met,text = 'resolte : ',font = fnt)
lb.grid(row = 3,column = 0,columnspan = 1,pady = 10,padx = 10)

met.mainloop() # fien de programe

