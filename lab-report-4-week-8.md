# Lab Report 4 (Week 8)  
Updated 5/21/2022  
## Relevant Repositiories:  
- [MY REPOSITORY](https://github.com/trinityxortiz/mdparse-week-7)  
- [REVIEWED REPOSITORY](https://github.com/trinityxortiz/mdparse-for-review)  

## Testing  

### Tests On My Repository  
**TEST 1**
- Expected Output and test in MarkdownParseTest.java: ![snippet test 1](Images\report-4\snippet-test-1.png)
- Test Results: PASS

**TEST 2**
- Expected Output and test in MarkdownParseTest.java: ![snippet test 2](Images\report-4\snippet-test-2.png)
- Test Results: PASS

**TEST 3**
- Expected Output and test in MarkdownParseTest.java: ![snippet test 3](Images\report-4\snippet-test-3.png)
- Test Results: PASS

![passing tests](Images\report-4\passing-tests-mine.png)

### Tests On Reviewed Repository    
**TEST 1**
- Expected Output and test in MarkdownParseTest.java: ![snippet test 1](Images\report-4\snippet-test-1.png)
- Test Results: PASS

**TEST 2**
- Expected Output and test in MarkdownParseTest.java: ![snippet test 2](Images\report-4\snippet-test-2.png)
- Test Results: PASS

**TEST 3**
- Expected Output and test in MarkdownParseTest.java: ![snippet test 3](Images\report-4\snippet-test-3.png)
- Test Results: PASS

![passing tests](Images\report-4\passing-tests-reviewed.png)

## Questions  
1. Do you think there is a small (<10 lines) code change that will make your program work for snippet 1 and all related cases that use inline code with backticks? If yes, describe the code change. If not, describe why it would be a more involved change.  

2. Do you think there is a small (<10 lines) code change that will make your program work for snippet 2 and all related cases that nest parentheses, brackets, and escaped brackets? If yes, describe the code change. If not, describe why it would be a more involved change.  

3. Do you think there is a small (<10 lines) code change that will make your program work for snippet 3 and all related cases that have newlines in brackets and parentheses? If yes, describe the code change. If not, describe why it would be a more involved change.  

## Answers  
1. I think that there could be a code change to handle inline code with backticks. I could follow the same process as finding the open and closed brackets by checking if there is a backtick before a link and finding the next backtick. After skipping the inline code I could change the index to start searching for the brackets after the second backtick.  
2. I don't think that there is a small code change to handle all instances of nested cases. It would take multiple lines of code to prevent all unique cases. For example, you would you have to check nested parentheses while in one set of parenthesis and keep track of the sets of open and closed parenthesis then ignore that number of parenthesis while still reading the remainder of the link inside the outermost closed parenthesis.  
3. I don't think that this would be a small code change. You would have to keep searching for the closed parenthesis and you would have to copy this same code for the brackets. It would take twice the amount of lines as a change fo finding a closed parenthesis.

