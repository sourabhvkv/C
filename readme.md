Created a folder named C.
Created an input.txt and output.txt files. 

In VS code toolbar Terminal > Configure tasks 

tasks.json file will open up

&& paste the following code, so you can compile the c program just by hitting Ctrl + Shift + B , will take inputs from the input.txt file and print output on output.txt 



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

Learnings

In Windows I didnt have C compiler installed so had breif problem when compiling, but later realised that there is no compiler 

Installed MYSYS2 and installed mingw compiler and included the path of the installed compiler on environment variables. 

Including path means showing the cmd the location where the compiler is installed so CMD can use the compiler 

I shall upload this to github now 

git init 

git add . 

