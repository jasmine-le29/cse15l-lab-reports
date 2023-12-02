## Lab Report 4

### Log into ieng6: 
<img width="493" alt="Screenshot 2023-11-19 at 4 11 13 PM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/a7d76a0c-72ce-48d0-9d78-92137ff17769">

- `<up> <enter>`
- Using `<up> and <enter>` was a fast and convenient way to log in to my ieng6 since that command has previously been used and can save time instead of typing the whole thing out again.

### Clone your fork of the repository from your Github account (using the SSH URL): 
<img width="551" alt="Screenshot 2023-11-19 at 4 26 59 PM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/2e63408c-3c12-458e-88c3-7dbb2ab70d36">

- `<ctrl> r g <enter> `
- Using `<ctrl> r` is a quick way to search through the command line recursively in the command history. This a fast and effective way to get your ssh git clone command without having to type `git clone`. 

### Run the tests, demonstrating that they fail: 
<img width="627" alt="Screenshot 2023-11-19 at 4 37 02 PM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/e1876110-0951-40cc-8bb3-a6d11b731304">

- `cd l <tab>`
- `bash t <tab> <enter>`
- Use `cd` to change directories followed by the name. Instead of typing out `lab7` we can just type `l <tab>` which autocompletes the name of the directory we are trying to `cd` into followed by the `<enter>` key to make the change.
- To run the test we can follow the same method for `cd`, `bash t <tab>` to autocomplete to `test.sh` then we can `<enter>` to make the command effective.

### Edit the code file to fix the failing test:
<img width="409" alt="Screenshot 2023-11-19 at 4 47 10 PM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/071b4ae8-fc70-4e80-842a-c70ecde4695f">

- `vim <space> <shift> L <tab> . <tab> <enter>`
- To enter `vim` in order to edit the tests that failed. We need to `vim` to the specific file we want to edit. In this case, it would be the file `ListExamples.java`. Instead of typing the whole thing out, we can type the first letter of the file name then press `<tab>` to autocomplete the name of the file followed by the `.` then `<tab>` to autocomplete the `java` file.

<img width="371" alt="Screenshot 2023-11-19 at 4 53 58 PM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/5e8279cc-8d72-45ea-9db8-92d41bb7ddba">

- `:44 <enter> e r 2`
- `:wq <enter>`
- Once we are in `vim` and the file `ListExamples.java`, we can see that the error is located on line 44. We can use the commands `:44` and `<enter>` to jump directly to the error line. Once we get to the beginning of the line, we can use the key `e` to jump to the end of the word `index`, where we can change `index1` to `index2` by quickly doing `r` followed by `2` after. `r` is the command to replace and since we want to change `1` to `2` we can just directly use the `2` after `r`. After fixing the commands required for the test to pass, the command `:wq` is to quit and save followed by the `<enter>` key.

### Run the tests, demonstrating that they now succeed:
- `bash t <tab> <enter>`
-  `bash t <tab>` to autocomplete to `test.sh` then we can `<enter>` to make the command effective. Same as when we were initially running the test before revision.

<img width="330" alt="Screenshot 2023-11-19 at 4 55 40 PM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/2f99606e-db94-49fd-b3df-c3586d287a47">

### Commit and push the resulting change to your Github account (you can pick any commit message!):

<img width="502" alt="Screenshot 2023-12-02 at 2 33 14 AM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/f61b8582-a360-4dff-8f98-07b9296f2547">

- `<ctrl> r git add <enter>`
- `git com -m "Updated Version" <enter>`
- Using `<ctrl> r` to search through the command line recursively in the command history for the commit function `git com` followed by the `<enter>` key.
- Once you enter `vim` again, you change your commit message. In this case, I changed mine to "lab 7 revise". Use `:wq` followed by `<enter>` key to save changes. This should display that it committed to the GitHub after you save and quit.

<img width="716" alt="Screenshot 2023-11-19 at 5 05 42 PM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/5ec2e4d1-be99-432f-8bea-cb63ca0cba28">

- `<ctrl> r git pu <enter>`
- We use `<ctrl> r` once again to search recursively for the command `git push`. In this case, I didn't have to type out `push` completely but `pu` will show the rest of the command. Followed by the `<enter>` key will push the changes to Git Hub.
