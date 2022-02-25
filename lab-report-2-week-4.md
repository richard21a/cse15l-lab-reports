[Lab Report 1](https://richard21a.github.io/cse15l-lab-reports//lab-report-1-week-2.html)
[Lab Report 3](https://richard21a.github.io/cse15l-lab-reports/lab-report-3/lab-report-3-week-6.html)
[Lab Report 4](https://richard21a.github.io/cse15l-lab-reports/lab-report-4/lab-report-4-week-8.html)
# Change 1:

![Image](error1.png)

[Link of test file](https://github.com/AnniePhan02/markdown-parse/blob/main/testincorrect.md)

![Image](symptom1.png)

The symptom was that the code was printing the same two output repeatedly. This meant that the while loop in the code was not exiting which was caused by switching a close bracket[] with open brackets() in the input.

# Change 2:

![Image](error2.png)

[Link of test file](https://github.com/AnniePhan02/markdown-parse/blob/main/test2incorrect.md)

![Image](symptom2.png)

The symptom was that the code printed out the incorrect contents. This likely meant that the code was picking the wrong set of paraenthesis in the input file which contained an extra pair of paranethesis before the one that contains the link.

# Change 3:

![Image](error3.png)

[Link of test file](https://github.com/lbryton/CSE15L-Panther/commit/9d71066e913331140038a64bcca98484ba6fca07)

![Image](symptom3.png)

The symptom was that the code printed out a supposed link that contains a space. Since no real links contain spaces, the code should have checked for a space and filtered any links containing spaces. However, when we inputted a "link" containing a space, the program didn't filter out the faulty link.