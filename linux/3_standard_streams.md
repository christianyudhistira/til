# 3 Standard Streams - stdin, stdout, stderr

3 types:    
1. stdin - 0
2. stdout - 1
3. stderr - 2

> They have input and output flow.   
> The output flow will be connected to the terminal window, connected to a pipe, or redirected to a file or other command.   

### Redirecting stdout and stderr
### example 1:  

redirection symbol **>** works with stdout by default.  
    
1. copy following shell script and save it into a .sh file
```bash
#!/bin/bash

echo "About to try to access a file that doesn't exist"
cat bad-filename.txt
```

2. make the script executable and run the script
3. try to redirect the ouput to a file
```bash
./error.sh > capture.txt
```

The error message that is delivered via stderr is still sent to the terminal window.    
The output from stdin was redirected to the file as expected.   

### example 2:  

To explicitly redirect stdout, use **1>**   
To explicitly redirect stderr, use **2>**

1. This command will direct stdout to a file called capture.txt and stderr to a file called error.txt.
```bash
./error.sh 1> capture.txt 2> error.txt
```

source:
- [howtogeek](https://www.howtogeek.com/435903/what-are-stdin-stdout-and-stderr-on-linux/)