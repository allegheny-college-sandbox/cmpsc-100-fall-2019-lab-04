# CMPSC 100-03 Lab Session 4: Hail, Geiwev%
* Assigned: 22 September 2019
* Due: 29 September 2019
* Point value: 35 pts

> If he had anything confidential to say, he wrote it in cipher, that is, by so changing the order of the letters of the alphabet, that not a word could be made out. If anyone wishes to decipher these, and get at their meaning, he must substitute the fourth letter of the alphabet, namely D, for A, and so with the others. 
— Suetonius, _Life of Julius Caesar_

In this laboratory session, we explore topics including: 

* "casting"
* file inputs
* primitives like `char` and `int` 

in pursuit of implementing a "Caesar" cipher, a simple way of encoding messages.

## General guidelines for laboratory sessions

* **Follow steps carefully.** Laboratory sessions often get a bit more complicated than their preceeding Practical sessions. Especially for early sessions which expose you to platforms with which you may not be familiar, take notes on `command`s you run and their corresponding effects/outputs. If you find yourself stuck on a step, let a TL or the professor know! Laboratory sessions do not mean that we won't help you in the same way we do during Practicals.
* **Regularly ask and answer questions.** Some of you may have more experience with the topics we're discussing than others. We can use this knowledge to our advantage. But, like in Practicals, let students try things for a while before offering help (**always _offer_ first**). To ask questions, use our [Slack](https://cmpsc100fall2019.slack.com)'s `#labs` channel.
* **Store and transfer files using GitHub.** Various forms of file storage are more or less volatile. *You* are responsible for backing up and storing files. If you're unsure of files which have been changed, you can always type `git status` in the terminal for your working folder to determine what you need to back up.
* **Keep all of your files.** See above, but also remember that you're responsible for the files you create.
* **Back up your files regularly.** See above (& above-above).
* **Review the [Honor Code](https://sites.allegheny.edu/about/honor-code/) reguarly when working.** If you're taking a solution from another student or the Internet at-large (_especially_ [Stack Overflow](https://stackoverflow.com)), bear in mind that using these solutions _can_ constitute a form of plagiarism that violates the Allegheny Honor Code. While it may seem easy and convenient to use these sources, it is equally easy and convenient to rely on them and create bad habits which include not attributing credit or relying exclusively on others to solve issues. Neither are productive uses of your intellect. Really.

## Further helpful reading for this assignment

If you have not already done so, I recommend reading the [GitHub Guides](https://guides.github.com) which GitHub makes available. In particular, the guides:
* [Mastering markdown](https://guides.github.com/features/mastering-markdown/)
* [Documenting your projects on GitHub](https://guides.github.com/features/wikis/)
* [GitHub Handbook](https://guides.github.com/introduction/git-handbook/)
* GitHub handouts distributed at the beginning of the lab session

As for a markdown cheatsheet, [this GitHub repository](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) serves as a useful online, single-page guide.

## Required deliverables

A successful submission for this lab will include a Java program which:

* Compiles
* Runs successfully
* Contains:
    * No instances of the `TODO` placeholder
    * No instances of the `{YOUR NAME HERE}` placeholder
    * At least one (1) instance of the `charAt` method
    * An enciphered word stored in a `String` variable named `encipheredWord`
    * Use of the `+=` assignment operator in the correct context
    * One (1) method named `newCharValue` with a `return` statement returning an `int` value
    * At least one (1) use of the `newCharValue`
    * Output printed on two lines using the `System.out.print` method with a line break
    * Correct program output which prints the enciphered value `Geiwev%`
    * Three (3) multiline "Javadoc" comments accompanying classes and methods
    * Five (5) single line comments separating different parts of the program, each containing descriptions of the code following them

This submission should be accompanied by:

* A 300-word reflection included in a file named `reflection.md`, located in a directory called `writing` located in the main directory of your `commit`ted repository.
    * This file must contain:
        * One (1) level one header which should read "CMPSC 100-03: Lab 4" under which is written:
            * A brief, general description of how the program works
        * Five (5) additional headers (of the second and third levels) which describe:
            * Specific description of the `main` method, including key method calls such as `charAt`
            * Specific description of the `newCharValue` method, including:
                * Its relationship to `main`
                * Why it uses a `return` statement
                * The reason why it is separate from the `main` method
            * A description of "casting" and why you had to invoke the strategy (see pages 83-84 in the textbook for more information)
            
## Write your code

- [ ] If you have not already cloned the repository, do so now.
* Remember proper file management here. You should have a directory where you've started storing files for this course which may be in one of the following locations:
    * ~/Desktop
    * ~/OneDrive/Desktop
- [ ] When you're ready, begin coding in the `DisplayCipher.java` file located in the `/src/main/java/cipher/` directory.

## Using GatorGrader

GatorGrader is a software utility actively developed and maintained by students in consultation with Allegheny faculty, Prof. Kapfhammer. This software allows you to check your work _before_ turning it in, so that you know--at any point--what your grade would be on an assignment if turned in at the moment you run GatorGrader.

When you turn assignments in for this class, the action triggers a "build" in a utility called [Travis](https://travis-ci.com). One of the steps it includes is running GatorGrader against the submitted code. There aren't any hidden criteria; the grader will grade the assignment the same way, regardless of who run it because it is based on files which are contained _in the very repository you commit_. Once a repository is cloned, grading critieria will never change.

### Installation

#### Mac

- [ ] In a terminal window, type `docker pull gatoreducator/dockagator`.
* This will contact Docker Hub to download the GatorGrade docker `image`.
- [ ] Type `docker images`
* The newly-acquired image should appear in the list as `gatoreducator/dockagator`
- [ ] To run the GatorGrader, `cd` to the main directory of your repository and type:
```
docker run -it --mount type=bind,source="$(pwd)",target="/" --hostname GatorGrader gatoreducator/dockagator
```
* You should now be in the GatorGrader `container`.
- [ ] Type `gradle build` to begin setting up your assignment for grading.
- [ ] When the above command completes, type `gradle grade`
* This will begin the grading process.
- [ ] When the grading process completes, call the professor over to discuss.

#### Windows

For those Windows users interested in using a Docker image to implement GatorGrader, please [book student hours](https://cs.allegheny.edu/sites/dluman) to discuss the process with me.

**Note:** For all of the following steps, you will need administrator privileges to install these programs.

##### Install `gradle`

Using the simplest definition, Gradle is a build automation tool. In plain terms, it's a program that orchestrates complex processes so that you, the end user, don't have to do them. 

The faculty have written scripts to automate the grading process--a process which can take many, many individual commands to complete. As you'll see, there are really only three things you need to do when running a `gradle` grading process instead of the many that the process may actually require. The tool makes things easy for you.

- [ ] In a `cmd` window, use `choco` to install Gradle by typing `choco install gradle -y`
- [ ] Once complete, test your installation by typing `gradle --version`
* A typical response would be similar to: `Gradle` followed by a version number

##### Install `python` and `ruby`

If you're not familiar with these two languages, Python and Ruby are 3<sup>rd</sup> generation languages--similar to Java. Some of you may have experience with them while others of you may never have heard of them. You do not need to know anything about either in this course except that they need to exist on your computer to run GatorGrader. 

If you're so inclined, you might begin to tinker in these languages to learn a bit more about how different languages operate. Python and Ruby, while similar to each other, are different from Java.

- [ ] Use `choco` to install Python by typing `choco install python -y`
- [ ] Use `choco` to install Ruby by typing `choco install ruby -y`

To facilitate GatorGrader finding the right `python` command, we need to use `mklink` to create a "symbolic link" (a.k.a. a fake file).

- [ ] In the same `cmd` window, type:
```
mklink "c:\Python37\python3.exe" "c:\Python37\python.exe"
```

We're in the home stretch.

- [ ] Close the current `cmd` window and open another with administrative privileges
- [ ] Use `pip`, a "package manager" like `choco` to install a couple of tools:

```
pip install proselint
```

```
pip install pipenv
```

* `pip` is exclusive to Python, and installs extensions and applications for the Python language.

- [ ] Use `gem`, another "package manager" to install one tool:

```
gem install mdl
```

- [ ] When you're ready to grade, either call the professor over (if we're still in the lab session), or [schedule student hours](https://cs.allegheny.edu/sites/dluman) to discuss the process.