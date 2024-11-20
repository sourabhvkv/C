Goal is to record all the programs that I write and practice for the 
course. 

Starting from Basic C to Embedded C journey.

Created a directory and named it C,
to record all the programs I write and practice in C.

Created input.txt and output.txt files. 

In VS code toolbar Terminal > Configure tasks 

tasks.json file will open up

&& paste the following code, 
so you can compile the c program just by
hitting Ctrl + Shift + B , will take inputs
from the input.txt file and print output on 
output.txt 

Following code is the config code for the above
stated VS Code setup 


{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "Compile and run",
      "type": "shell",
      "command": "cmd",
      "args": [
        "/c",
        "copy \"${file}\" \"${workspaceFolder}\\temp.c\" && gcc \"${workspaceFolder}\\temp.c\" -o \"${workspaceFolder}\\temp\" && \"${workspaceFolder}\\temp\" < \"${workspaceFolder}\\input.txt\" > \"${workspaceFolder}\\output.txt\" && del \"${workspaceFolder}\\temp.exe\" && del \"${workspaceFolder}\\temp.c\""
      ],
      "presentation": {
        "reveal": "always"
      },
      "group": {
        "kind": "build",
        "isDefault": true
      },
      "problemMatcher": {
        "owner": "c",
        "fileLocation": [
          "relative",
          "${workspaceRoot}"
        ],
        "pattern": {
          "regexp": "^(.*):(\\d+):(\\d+):\\s+(warning|error):\\s+(.*)$",
          "file": 1,
          "line": 2,
          "column": 3,
          "severity": 4,
          "message": 5
        }
      }
    }
  ]
}

Once the playgroud is created, written the first test program 

HareKrishna.c 

Have tested various ways of providing the inputs and tested with characters 
as inputs and figured that to avoid any spaces as input 
we can break the input while scanf is reading the input over to the next line. 


Learnings during installation 

In this Windows system I didnt have C compiler installed
so had breif problem when executing the code not realising this fact,
but later realised that there is no compiler in
the system.. why does windows does not have an
inhouse c compiler by default.. ?? I shall 
migrate to linux soon ..

Installed MYSYS2 and 
installed mingw compiler 
and included the path of the 
installed compiler on environment variables. 

Including path means showing the 
cmd the location where the compiler 
is installed so CMD can use the compiler 

Now that everything is done, and set up to the perfect state,
its time to push the code to remote repository 


Git commands 

git init // initializes the git version control in the directory

git add .  //adds a change in the working directory to the staging area. 

git commit -m "Add the commit to GitHub repo"  //commits with the message 

git remote add origin ##paste the link## //to add the host where you want to upload the code - one time procedure

git push -u origin main  // pushing the code 

git branch -M main  //changed the branch name to main from master

-------------------------------------------
EOD 1 - Will add remaining later today. 