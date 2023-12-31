# machineBust
Crawling a bank website to find hidden and unprotected web pages that allow access to sensitive user data.

# Tool Overview:

GoBuster is an open-source tool designed for finding hidden paths, directories, and files on web servers. It is commonly used in penetration testing and ethical hacking activities to discover potential vulnerabilities in web applications. GoBuster operates by launching brute-force attacks against a target web server, attempting to enumerate and locate existing directories and files.

Key features of GoBuster include:

1. **Directory and File Enumeration:** GoBuster helps in the systematic discovery of directories and files on a web server by trying different paths and filenames.

2. **Brute-Force Attacks:** It employs a brute-force approach by systematically trying various combinations of directory and file names to identify hidden resources.

3. **Multithreading Support:** GoBuster supports multithreading, allowing it to perform multiple requests concurrently. This can significantly speed up the scanning process.

4. **Wordlist Support:** Users can provide custom wordlists to guide the tool's brute-force attempts. Wordlists contain a list of potential directory and file names that GoBuster will try during the enumeration process.

5. **HTTP Methods:** GoBuster supports different HTTP methods such as GET and HEAD, allowing users to customize their requests based on the target web server's behavior.

6. **Recursive Mode:** GoBuster can be set to operate in recursive mode, exploring directories and files within discovered paths to provide a more comprehensive view of the web server's structure.

It's important to note that while GoBuster can be a valuable tool for security professionals, it should only be used in ethical and legal hacking scenarios with proper authorization. Unauthorized or malicious use of such tools is illegal and unethical. Always ensure you have permission before conducting any security assessments or testing.

# Similuation Walkthrough

Most companies will have an admin portal page, giving their staff access to basic admin controls for day-to-day operations. For a bank, an employee might need to transfer money to and from client accounts. Often these pages are not made private, allowing attackers to find hidden pages that show, or give access to, admin controls or sensitive data.

Using this command to find potentially hidden pages on FakeBank's website using GoBuster (a command-line security application):

```bash
gobuster -u http://fakebank.com -w wordlist.txt dir
```

The command will run and show you an output similar to this:

![plot](./GoBuster.png)

In the command above, `-u` is used to state the website we're scanning, `-w` takes a list of words to iterate through to find hidden pages.

You will see that GoBuster scans the website with each word in the list, finding pages that exist on the site. GoBuster will have told you the pages it found in the list of page/directory names (indicated by Status: 200 => Succesful Request).

You should have found a secret bank transfer page that allows you to transfer money between accounts at the bank (/bank-transfer). By typing the hidden page into the FakeBank website on the machine:


https://github.com/Farouk-Echaref/machineBust/assets/66710845/f3884af4-5f90-4663-b721-8786a7bf3b68







