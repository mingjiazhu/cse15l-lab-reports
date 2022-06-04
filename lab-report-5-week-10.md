## Week 10 Lab Report

### How you found the tests with different results?

I used vimdiff.

### Provide a link to the test-file with different-results

[194.md](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/194.md)

[201.md](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/201.md)

[22.md](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/22.md)

[32.md](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/32.md)

[41.md](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/41.md)

### Answers for the questions

test 194:
<br>
actual outputs:
<br>
<img src="lab-report-5-images/test194.png" width="500" />
<br>
expected output:
<br>
<img src="lab-report-5-images/194-preview.png" width="500" />
<br>
Both implementations produce incorrect results. The expected result should be `[my_(url)]`. For the given implementation, since it is extracting the contents between open and close parentheses, it only gets "url" in the parentheses. 
<br>
<img src="lab-report-5-images/194fix.png" width="500" />
<br>
To fix the bug, we need to add several lines of code between line 64 and 65. We need to consider the situation that there's colon in the markdown. When there's a colon, we get the part after it until a space appears.
<br>

test 201:
<br>
actual outputs:
<br>
<img src="lab-report-5-images/test201.png" width="500" />
<br>
expected output:
<br>
<img src="lab-report-5-images/201-preview.png" width="500" />
<br>
My implementation (left) is correct. For the given implementation, since it is extracting the contents between open and close parentheses no matter it is a url, thus it is getting "baz", which is the content in the parentheses.
<br>
<img src="lab-report-5-images/194fix.png" width="500" />
<br>
To fix the bug, we need to add several lines of code between line 64 and 65. We need to consider the situation that there are "<>" between bracket and parenthese. When there are "<>" between bracket and parenthese, we don't consider it as a url.
<br>

test 22:
<br>
actual outputs:
<br>
<img src="lab-report-5-images/test22.png" width="500" />
<br>
expected output:
<br>
<img src="lab-report-5-images/22-preview.png" width="500" />
<br>
Both implementations produce incorrect results. The correct result should be `bar*`. For my implementation, since I'm not considering the slash and backslash in the url, it is producing the whole contents in the parentheses.
<br>
<img src="lab-report-5-images/22fix.png" width="500" />
<br>
To fix the bug, we need to add an if statement at this part (line 22-23) to check whether there's space between an open and a close parenthese. If there's space, we only extract the part before the space.
<br>

test 32:
<br>
actual outputs:
<br>
<img src="lab-report-5-images/test32.png" width="500" />
<br>
expected output:
<br>
<img src="lab-report-5-images/32-preview.png" width="500" />
<br>
Both implementations produce incorrect results. The correct result should be `föö`. For my implementation, since I'm not considering the characters like "&" and ";", it is directly producing the whole contents in the parentheses.
<br>
<img src="lab-report-5-images/22fix.png" width="500" />
<br>
To fix the bug, we need to add an if statement at this part (line 22-23) to check special characters in the markdown. The "ö" in this url was not considered in my implementation.
<br>

test 41:
<br>
actual outputs:
<br>
<img src="lab-report-5-images/test41.png" width="500" />
<br>
expected output:
<br>
<img src="lab-report-5-images/41-preview.png" width="500" />
<br>
The given implementation (right) produces correct results. For my implementation, since I'm not considering the characters like "&" and ";", it is producing the contents in the parentheses no matter whether they belong to a url.
<img src="lab-report-5-images/22fix.png" width="500" />
<br>
To fix the bug, we need to add an if statement at this part (line 22-23) to check the quotation marks in the markdown file. We need to exclude the content in the quotation marks in the url.
<br>


