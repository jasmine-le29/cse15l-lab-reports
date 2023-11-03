## Lab Report 2

# Part 1

<img width="772" alt="Screenshot 2023-10-21 at 10 38 27 PM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/3bb0470a-3b0b-4c33-a6f3-67815f0889a7">

- The handleRequest and the main method were called for this example above.
- In the method handleRequest, there consists of a parameter called url that takes the URL to the beginning of the path. For Main, there consists of a string parameter "args" used to intake the port number provided. As shown in the screenshot above, I used port 1025 which is the value of the parameter of main. For handleRequest, the parameter is localhost. Some relevant values for this class are count, strg, and strgCount where count is = 0 and strg/strgCount is "" (empty string).
- For the request in the image shown above, "/add-message?s=Hello" the strg variable is changed from "" to "Hello, count it changed to 1 from 0, strgCount is changed from "" to "1.", and the url is changed followed by the "/add-message?s=Hello" along with the local host and port number.
  
<img width="887" alt="Screenshot 2023-10-21 at 10 39 01 PM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/c429abc6-3658-4368-b46c-769b6374bb05">

- The handleRequest and the main method were called for this example above.
- The relevant arguments for this class are url and arg. The relevant values are strg and strgCount. Since we are asked to output another string with the below it changed the count. The local host and port number remain the same.
- The values are changed. The task was changed from /add-message?s=Hello to /add-message?s=How are you. Although my first attempt at changing the to "/add-message?s=How are you" it output "How+are+you". I revised that by changing the + to "" shown in the code below. The count changed from 1 to 2 on the new line of the "How are you?" statement. strgCount also changed from "1" to "2".
  
**StringServer.java Code**

<img width="593" alt="Screenshot 2023-10-21 at 10 40 20 PM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/c920612a-b707-4c4e-a2f8-201b618ef6ec">



# Part 2

Login without password

<img width="982" alt="Screenshot 2023-10-21 at 11 21 04 PM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/854ecd6c-bd57-4230-a9b0-3ec6067c6764">

Path to public key

<img width="556" alt="Screenshot 2023-11-03 at 12 27 57 PM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/261fc0af-c756-4bfb-bdac-2e40f34be424">

Path to the private key

<img width="355" alt="Screenshot 2023-10-21 at 11 45 28 PM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/6676ed7d-e463-453d-b913-d6c1c7de8b34">




# Part 3
- I learned from week 2/3 how to use the ssh command to connect to a remote server. We could access our personalized usernames and change our passwords to access our remote server. Upon completing this lab report, instead of having to enter our password every time we would log in to our remote server, we could set up and save the public key and save our password.
