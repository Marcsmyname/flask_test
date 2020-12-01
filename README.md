# flask_test

I'm leaarnign flask by watching Youtube videos.

This is a basic flask deployment I am using to learn how to use virtual environments and Git.  These are my notes.

Notes from Youtube Video: "From Creating a Basic Python Flask environment in Windows"

Mike Colbert

"Creating a Python virtual environment and installing Flask using pip. We also create a requirements.txt file and a .gitignore file for the project. A simple Python Flask application that returns a "Hello World" string is created."

notes:

start in github

create a new repository. dont forget to add README.md file

clone or download URL, like you would any other github project

get the URL

#In CMD

to clone to desktop

cd desktop

git clone https://github.com/Marcsmyname/flask_test.git

cd flask_test

dir

#setup a virtual environment
#make sure python is installed.
python --version
#looking for anything > 3.5

#to create the virtual environment
python -m venv ./venv

.\venv\Scripts\activate

#this will activate the virutal environment and show you (venv)

#pip list to see what is installed
pip list

#install flask even if it's already on your computer, this is for github dependencies

pip install flask

#you get all of this cool stuff

(venv) C:\Users\Marc\Desktop\flask_test>pip list
Package      Version
------------ -------
click        7.1.2
Flask        1.1.2
itsdangerous 1.1.0
Jinja2       2.11.2
MarkupSafe   1.1.1
pip          19.2.3
setuptools   41.2.0
Werkzeug     1.0.1
WARNING: You are using pip version 19.2.3, however version 20.3 is available.
You should consider upgrading via the 'python -m pip install --upgrade pip' command.

# if someoe downloaded this they would get all of the dependencies
#or if you push it up to a server it will have all the packaages


#pip freeze takes a snapshot of all the installed packages and their versions they redirect them to requirements.txt
pip freeze >requirements.txt

#open editor. Atom, Sublime or something. I like Atom.


#open the folder you created and downloaded from github.  In this case: flask_test

#inside you can see the requirements the git venv and README.md




# create new file
.gitignore

#add the stuff you have in the gitignore file(hiddenn file) tells git what to ignore. dont want git trackin virtual environment
#Don't want to track the flask instance, or anything in there
#__pycache__ creates stuff we do not want in github
#webassets not tracked and some other python projects

#save

#create new file
app.py

 #add the stuff in the app.py file. I atually coppied most f it from flask documentation

#from flask module import Flask class
 from flask import flask
#the flask __name__ is a variable that is the same thing as


#how we capture our different web pages. we are not linking to subfolders and files
#we are linking to routes

# it creates a fucntion and tuns the app if the flak name is name

app = Flask(__name__)
@app.route('/')
def index():  
  return "hello world"

if __name__ =='__main__':
  app.run(debug=True)


#to run server type:
flask run

to make a new tab do this

@app.route('/marc')
def marc():
    return "Hello, Marc!"




#if you edit you will need to control c in console and rerun it.

ctrl + c

flask run

#To push to github, in console

git status


Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore
        README.md
        app.py
        requirements.txt

nothing added to commit but untracked files present (use "git add" to track)

#push this back up to github must be double quotes

git commit -m "initial commit of basic flask server"

git push origin master

#you will now have two commits, second commit onlu has app requirements and gitignore and readme file
