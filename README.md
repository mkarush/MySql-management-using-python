# MySql-management-using-python
MySql database imported and edited busing Python
import mysql.connector
#IT connect mysql to Python
conn=mysql.connector.connect(user="root",password="network",host="localhost",database="ee281")
mycursor=conn.cursor()
W=input("What you wanted to do Search 's' and input 'i'::")
#Asked user what he wanted to do search or input value in table
class search:
    #It uses in search of the data
    def __init__(self,n):
        mycursor.execute("""SELECT * FROM WWW WHERE id=%s"""%(n))
        cd=mycursor.fetchall()
        #It will fetch all value from the tables
        if not cd:
            print("Not Available")
        #not Cd will work as null if null it will print "not available"
        else:
            print (cd)
            ac=input("You wanted to extract data from the database press y(yes) or n(No)::")
            if ac=="y":
                #If user want that data it will get extracted from the data-base
                ab=delete(b)
            else:
                pass
class input1:
    #It input value in table
    def __init__(self,i):
        mycursor.execute("""INSERT INTO WWW(name) VALUES('%s')"""%(i))
        conn.commit()
        mycursor.execute("""SELECT * FROM WWW """)
        #It will display all value of table www
        b=mycursor.fetchall()
        for ig in b:
            print (ig)
class delete:
    #It will delete value from the table
    def __init__(self,j):
        mycursor.execute("""DELETE FROM WWW where id=%s"""%(j))
        conn.commit()
        #commit is the important command as it will save the value in table
        print ("Values left in the database")
        mycursor.execute("""SELECT * FROM WWW""")
        ik=mycursor.fetchall()
        for j in ik:
            print (j)
if W=="s":
    #If user press W than this will work
    a=input("Value id you wanted to search::")
    b=str(a)
    d=search(b)
elif W=="i":
    #If user press I than this will work
    a=input("NAME you wanted to add::")
    b=str(a)
    d=input1(b)
else:
    #else everything will work
    print("Invalid input")

input("Press Enter to Exit")

