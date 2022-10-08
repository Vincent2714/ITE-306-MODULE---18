ITE-306-MODULE---18 UNARCE

Step 1: Install Flask
To Install Flask open CMD:

$ pip install Flask
Step 2: Testing
copy hello.py and save it in your selected python compiler and save the program into hello.py
from flask import Flask
from flask import jsonify
from flask import request
app = Flask(__name__)
empDB=[
{
'id':'101',
'name':'Dorry Britz',
'title':'Technical Leader'
},
{
'id':'102',
'name':'Barbie Gurl',
'title':'Software Engineer'
}
]

@app.route("/")
def hello():
        return "Hello World!"

@app.route('/empdb/employee/', methods=['GET'])
def getAllEmp():
        return jsonify({'emp':empDB})

@app.route('/empdb/employee/<empId>', methods=['GET'])
def getEmp(empId):
        usr = [ emp for emp in empDB if (emp['id']==empId)]
        return jsonify({'emp':usr})

if __name__ == '__main__':
        app.run()
open CMD and type the python (hello.py) file directory
C:\Users\Desktop>python C:\Users\Desktop\hello.py
The Output would be:

* Serving Flask app 'hello'
* Debug mode: off
WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
* Running on http://127.0.0.1:5000
Press CTRL+C to quit
copy the URL http://127.0.0.1:5000/ and paste it in your preferred browser tab
After pasting the URL it should display:

Hello World!
TO DO:
What is the output if you open this URL while hello.py is running:

http://127.0.0.1:5000/empdb/employee/
http://127.0.0.1:5000/empdb/employee/101
http://127.0.0.1:5000/empdb/employee/103
On your command prompt press "CTRL=C" to end the process of hello.py. What is the output if you open this URL while hello.py is not running:

http://127.0.0.1:5000/empdb/employee/
If you find this repository helpful then don't forget to give a star 🌟 to this repository. :)
