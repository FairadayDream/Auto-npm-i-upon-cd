# Auto-npm-i-upon-cd
automate npm i (install) and npm t (test) whenever you cd into a new directory! (MAC)

NOTES: 
This is a script to automate the installation of npm dependencies whenever the user changes the working directory (cd) to a folder containing a package.json file.

Desired Script Features:
- The script should be triggered automatically whenever a user changes directories in the terminal.
- It should check if the new directory contains a package.json file.
- If a package.json file is found, it should run npm install to install the dependencies.

Additional Information:
-  user is using zsh as default shell.
-  user wants to add this automation as a custom function to ~/.zshrc file.


*  STEPS  *

1. Open terminal and type either (I used zshrc):
` nano ~/.bashrc`
OR
` nano ~/.zshrc`

2. Insert:
`function cd {
    builtin cd "$@"
    if [[ -f "package.json" ]]; then
        echo "Running npm install..."
        npm install
        if [[ $? -eq 0 ]]; then
            echo "Running npm test..."
            npm t
        fi
    fi
}`

3. then on keyboard press ` ^ x ` and then press `Y` and  `enter`

4. then `source ~/.zshrc` to reset the terminal to accept yourr changes
