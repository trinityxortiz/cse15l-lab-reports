# Lab Report 5 (Week 10)   
Updated: 6/10/2022  
## Chosen Tests
- [530](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/530.md)
- [507](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/507.md)

## Finding the Tests  
- First I cloned both my repository and the class repository into the cse15l server. Then I ran `bash script.sh > results.txt` on both repositories to generate output for each implementation and added the output to a text file. Afterwards, I used vimdiff to see the differences of the output.

## Determining the Correct Implementation 

### Test 507
- The class implementation was correct.
- My implementation was not correct because it should have ignored what is inside of the parenthesis since it is not a proper link. It should ignore what is inside the parenthesis if there are quotation marks or if the url starts with a slash. The code change could happen here when viewing the potential link.  

![ss of code that should be changed](Images\report-5\530-bug.png)  

- **Actual Outputs:**  

![screenshot of actual output](Images\report-5\507.png)  

(Left is my repo, right is class repo)
- **Expected Outputs:** ![screenshot of expected output](Images\report-5\507-expected.png)


### Test 530
- My implementation was correct.
- The class implementation was not correct because it should not read images as link. In this case, the image is embedded inside brackets so we should check if there is an exclamation mark and skip until we find a closed parenthesis. This area is where the code change should approximately take place.![ss of code that should be changed](Images\report-5\507-code-change.png).
- **Actual Outputs:** ![screenshot of actual output](Images\report-5\530-expected.png)  
(Left is my repo, right is class repo)
- **Expected Outputs:** ![screenshot of expected output](Images\report-5\test530.png)
