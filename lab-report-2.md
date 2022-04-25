# Lab Report 2: Debugging & Improving a Markdown Parser 
Published: 4/24/22  

## Failure 1: Parsing Through a File With an Extra Line
***

Failing Test File: [Test File 2](https://github.com/trinityxortiz/markdown-parser/blob/main/Testing/test-file-2.md)  
Failure-Inducing Output: ![Symptom SS](Images\Lab 3\TF2-Output-Failure.png)

Commit with Changes: ![Change Commit](Images\Lab 3\TF2-Fix-Commit.png)

### Relationships:
The bug was that the program could not handle markdown files with an extra line and no proceeding links. The symptom of this was an out of memory error when running that file in the terminal. The failure-inducing ouput was the lack of output and the exception being shown instead.

## Failure 2: Reading Images as A Link
***

Failing Test File: [Test File 3](https://github.com/trinityxortiz/markdown-parser/blob/main/Testing/test-file-3.md)  
Failure-Inducing Output: ![Symptom SS](Images\Lab 3\TF3-Ouput.png)

Commit with Changes: ![Change Commit SS](Images\Lab 3\TF3-Fix.png)  

### Relationships:
The bug was that the program did not ignore images when searching for links. The symptom of this was the production of the wrong answer in the terminal. This symptom was shown by the failure-inducing output.

## Failure 3: Reading Links With Brackets and Parenthesis Far Apart
***

Failing Test File: [Test File 4](https://github.com/trinityxortiz/markdown-parser/blob/main/Testing/test-file-4.md)  
Failure-Inducing Output: ![Symptom SS](Images\Lab 3\TF4-FIP.png)

Commit with Changes: ![Change Commit SS]()  

### Relationships:
The bug was that the parser kept looking for the parenthesis after the brackets even though they are supposed to be right next to one another. The symptom of this was the production of the wrong answer in the terminal. This symptom was shown by the failure-inducing output that showed the first link followed by another empty link.   


