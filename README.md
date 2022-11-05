> When it comes to Test Driven Development, we have to understand many concepts in order to fully implement a test approach programming, is true that many developers writes tests in their project but only few follows the guidelines properly. This specification provides, in my own opinion a better way to follow TDD using NestJS as our language framework, the information provided here can be followed in some other languages as well.

# Concept and Mis-concept of UNIT testing

## Concept

In TDD, unit testing is a test approach which deals with testing only unit of work in the general system.
What we mean by that is that, in a situation whereby you have a system that does so many functions, and you want
to implement unit testing approach in this system, you have to break down the functionalities of the system
into many unit parts, a unit of work in the system should be able to execute in isolation of other unit of works and
return result provided that the data it needs to execute is available, this brings us back why we need to test it
and how we are going to achieve this easier, it also helps in providing a better quailty test. If in the system
provided one cannot be able to identify what a unit of work is, it simply means that there are flaws somewhere,
either in the system design or the developer is not knowledgeable enough to identify a unit of work in the system.
Once the unit of works are identified, then we implement test in each of these unit of work, not on the whole system
but in each integral part that can function and provide result. The major challenge in Unit testing falls under identifying
integral parts of the system.

Let's take this system for example:
A system where by students can come and upload receipt of their school payment, the system processes it and make sure that it
is a valid school reciept not forged. The system accepts it and activate school dashboard for this student. Now the student
can access the dashboard and join classes online, each class has section for assignments, quizes and exams.

Identifying the units of works in this system is important before implementing test and then coding. Lets look at this approach.

1. Student Upload's Reciept and it Get Proccessed and approve the student, we can treat this as test suit with a name like this: (Upload Receipt and Approve Student) which will have have many test cases under it to achieve this
2. Dashboard should be accessible to approved student to view classes, assignment, quizes and exams, and so on

## Misconcept

Sometimes even when we are trying to implement unit testing in our system there are some approaches we follow which is not advisable or sould I say we should always avoid.

1. Mock everything
2. Implementing expect count for each test case
3. Alwayss avoid test Setup; this is arguably right but not in all scenarios, it is good avoid test Setup but not always
4. Unit ensures that the whole system can is working, this is not true because you are testing for each unit of test.
5. Unit test provides insights on how the whole system works, this not also true as unit test provides insights on only how a unit of work of the whole system works not the whole system, bringing this together might not make if the test is clear on unit of work but on the general system.
6. It takes time, arguably true but not when you do it often.
7. Unit testing is all about the test than the code itself, is not true, unit testing more for the codebase being tested, is a guide to writing a quality and maintainable code not just the test.

# Why Unit Testing?

First of we need to recall that unit testing is only a single type of testing in the testing ecosystem, we also have integration testing and end to end testing. In all these kinds of testing, unit testing happens to be most seen and spoken of, so why is it that important. Unit testing helps improve code coverage and also in system whereby many developers are working on the same project, testing how each integral part of the system work might be tideous as e2e is all about how the whole system, unit testing provides execution insight of how each part of the system works and provides credibility of certain level of each part of the system. And knowing that each part of the system works well as they are expected to work increases the level of trust in the system implementation. In some system unit test touches almost every part of the code no matter how little.

# How test coverage works

I have seen so many talk about testing without saying much on how test coverage works and yet we write test to increase the test coverage in the system. Test coverage is all about how much of your code is covered with test, but we have seen a scenario whereby a function is not tested and yet test coverage insight tool is showing that is has been covered in the test in the platform. Simply, test coverage is all about how much of your code is executed when a test is run, is not only about the function that is being test but also the functions and methods that was called when the function being tested is called. This does not mean that you should not test the called function in isolation, but having this knowledge is important. Also you need to know that codebase with high test code coverage does mean that the codebase has quality code or everything is working as it should be, it simply means how much of the codebase that was executed when test performed

# Test first approach codebase why we need it

Just imagine writing test first before writing the actual code to be tested, it sounds strange but yes this is the approach you need follow in other to implement a quality code and have test guiding the implementation. One good thing I have noticed about test first approach is that the writing test first leads to writing a quality code, and implementing some design pattern correctly thereby understanding how some concept of design approach. Without argument have proven to work in 99% in the system is being followed. We need to follow this approach because writing the test first and it fails and we write code to pass it, then refactor and repeat this process is one of the steps and approach that helps us implement maintanable codebase.

# Qualities of good unit test

1. High rescilience in code change
2. Should run in isolation of other test cases
3. Should have every dependencies it needed to work provided in the test
4. Should not update or change any global object
5. Should connect to database or use file system
6. Should follow the arrange, act and assert approach
7. Should test only one method in each test case
8. No Logic in the tests
9. Should have good naming convention, a test with a good naming convention doesn't need assertion message
10. When a test failes the reason it failed should easily be identified in the code.


