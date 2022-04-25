# Lab Report 2: Debugging & Improving a Markdown Parser 
Published: 4/24/22  

## Failure 1: Out of Memory Error
***

Symptom Description:  

![Symptom SS]()  

Failing Test File: []()  

![Change Commit SS]()  

## Failure 2: Reading Images as A Link
***

Failing Test File: [Test File 3](https://github.com/trinityxortiz/markdown-parser/blob/e93fdc1154d0d3348d5ccb5099b7c23f321e8e80/Testing/test-file-3.md) 

![Symptom SS](Images\Lab 3\TF3-Ouput.png)

![Change Commit SS]()  

### Relationships:
The failure-inducing output was the following:
```
[geisel.jpeg]
```

The bug was that the program did not ignore images when searching for links. The symptom of this was the production of the wrong answer in the terminal. This symptom was shown by the failure-inducing output.

## Failure 3: No Links
***

Symptom Description:

![Symptom SS]()  

Failing Test File: []()  

![Change Commit SS]()     


