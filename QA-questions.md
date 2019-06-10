# QA Interview Question

## 1. What is software testing?
open ended question, go as deep as you can

## 2. How do you design test cases? 
(Black box techniques: State transition, Error guessing, Equivalence Class Partitioning ECP). 

## 3. What size of test case do you think is most suitable? 
* Trick questions, there is no hard set standard. 
* varies from case to case. 
* but general idea is to keep test case small. 

## 4. If a bug is spotted in production environment, how would you approach to it?
open ended question. Try to mention the following points:
* production Log inspection
* bug reproduction in test environment ( Dev, QA...) 
* develop test cases for this bug for future development

## 5. What if the bug is not re-producible?
difficult question, try to stay on checking log. make an example of multi-threaded application

## 6. What is the difference between unit test and integration test? 

## 7. Do you have experience in Test Driven Development TDD ?

## 8. Do you have experience in Behaviour Driven Development BDD? 

## 9. Do you think having comprehensive unit test would be sufficient? 
Trick question, 
* Unit test can never “truly covers” everything.. 
* there is just something that can not be tested or difficult to test
* employ other techniques to cover where unit test can not
* Understand the difference between Validation and Verification 

## 10. What is the difference between Smoke test and Sanity test?

## 11. How would you automate testing?
Open ended question, some helpful points
* build a continuous integration serve (CI) to enforce automated test to be a part of software building

## 12. What are test deliverables? 
* strategy
* plan
* development cost estimation
* test cases
* acceptance criteria 
* defect report
* execution log
* summary report (metrics or simply a document)
* many more... 

## 13. How do you assign priority of each test cases?

## 14. What are Acceptance testing?

## 15. What is the difference between Alpha and Beta?

## 16. How to manage the life cycle of a reported bug? 
tools such as Jira, GitHub Issues
depends on tools

## 17. Give me some examples of your previous testing outcome, success or failure?
can approach from unit test and integration test, because these are the most common ones that every develop should incorporate into their development

## 18. Do you have experience in testing automation?

## 19. Do you have experience in Quality Assurance? 
bonus: six-sigma 

## 20. How do you perform pre-production testing? 

## 21. When would you give a conditional sign off? 
must mention that you understand the risk and have solid rationale for backing up your decision. and make an example

## 22. How would you divide the responsibility between developer and QA?
:) 

## 23. what are the effective ways of catching defects early in development phases
some helpful points
* unit test
* integration test
* deployment automation (deploy product early and often into Dev, QA , UAT, review environment)
* bonus: DevOps and CI & CD pipeline

## 24. Would you encourage peer-review for test cases? 

## 25. What are the steps before going into production?
mention the entire process from a high level view, then focus on your parts as a testing engineer

## 26. what are the differences among Dev, QA, UAT, test, production environment? 
 
## 28. Do you have experience in tools like Jira? 

## 29. When should a team have a Code Freeze?

## 30. Is it good to have the team set a hard Code freeze date or time?
it’s always good :) but remember explain why.. and make example

## 31. What is RTM?
requirement traceability matrix
 
## 32. Do you have experience in Agile? 

## 33. What are Regression test cases?

## 34. When do you think a test should be automated and when should not? 
frequent changes in requirement...
remember automation is not indented to replace manual testing

## 35. What testing frameworks are you most comfortable with? 

## 36.  Do you know the concept of Abstraction? 

## 37. How do you design tests for component in a lower & higher abstraction level? 
abstract levels follow contract, so we can mock some levels

## 38. What do you think a good test suite should consist of? 

## 39. What is the difference between QA and QC?
quality assurance and control

## 40. What does code coverage mean? 

## 41. Have you ever performed Exploratory Testing? 

## 42. Give me a example of Performance Testing? 
  
## 43. Some keywords:
alpha testing, Beta testing, Ad-hoc testing, black box testing, clear box testing, functional testing, regression testing, CI & CD, testing automation, unit test, integration test, behaviour test, smoke test, sanity test, code freeze, abstraction, environment, RTM, test plan, test strategy, test scripts, Dev, QA, UAT, PROD environment, Non Reproducible bug, test management tool.
