---
layout: post
title:  "Blog Post: Final Project Jornal"
categories: blog assignment
permalink: posts/blog-final-project
author: Nora Adadurova
---

## Hello Everyone!

This post will be about demonstrating how to use my Selenium-Based Manga Monitor, as well as the building process!
If you would like to follow along, my code is available in my GitHub repository: https://github.com/NoraAda/PIC16B/tree/main/Final%20Project 

## Personal Insight into the project:

This final project was a unique experience for me, since, before this project, I always followed someone's instructions for all of the programs. So, before this experience, I have never had creative control. Therefore, for my final project, I decided to choose something personal and fun to do. As a result, I decided to make a project about searching for new chapters of manga in the top 5 websites I use in my day-to-day life. Choosing to make a project about a silly topic like searching for new chapters in manga made me feel that finally, I have a connection between my academic and non-academic interests. Moreover, when I was able to develop my own idea from scratch and the program started to slowly work according to my own idea, it reassured me that I did grow and learn a lot in the past few years and now can independently work on projects using my creativity and available online resources. In addition, this connection motivated me to finish its first version for the class and hopefully will inspire me to further work on it during the upcoming Christmas break. I hope that in a few months I can make it into something bigger and can share it with my friends' group so they can also benefit from it.

## Technical component:

It is an example of a python script which can be called through a terminal. Also, it uses users input in the terminal and gives output in the terminal as well. The first input of the program takes the title of needed manga. The input is processed by using text processing by regular expression to prepare the input for the search algorithm. This means that we disregard all non letter characters and transform it into the form convenient for our search algorithm.

The second input, devids users into two categories: if the user says any word starts from any letter not equal to N then we interpret his answer as Yes, the next program asks for the third input such as number of characters read before. If the answer had N as a first letter then the program interprets it as No and does not ask for chapters and assume that 0 characters was read. Also, it is important to note that this program uses Selenium. Selenium is an open source umbrella project for a range of tools and libraries aimed at supporting browser automation. It provides a playback tool for authoring functional tests across most modern web browsers, without the need to learn a test scripting language (Selenium IDE). It also provides a test domain-specific language (Selenese) to write tests in a number of popular programming languages, including JavaScript (Node.js), C#, Groovy, Java, Perl, PHP, Python, Ruby and Scala. Selenium runs on Windows, Linux, and macOS. But since in this class we used scrapy for homework #2, my first idea was to use scrapy but due to the website's protection called CloudFlare it did not work properly. Hence, I decided to use Selenium to avoid detection by CloudFlare.

Next, I have two choices: to use Selenium to see all its operations or to download the Xvfb package to hide the process and use virtual display. It is possible on Linux and Macrasoft but hard for IOS. Main objective of this program is working with is open program using selenium. Each website is treated and processed separately to collect needed information about the manga in question. The processing is dependent on the CSS structure of the website and the CSS elements. So, we go from the home page of the website to the manga information page (using the adopted page) to collect the needed information about characters’ updates. If a manga information page is not found, the program uses search and selects the first option in the search assuming that it is the most relevant to the user’s demand. But if the program uses search and there are no matches then the program outputs “this manga is not presented on” + name of the website and comments such as “you can still try to find other mangas.” Furthermore, optionally in the program can use a CSS object with a header to identify cases when manga was not found on the website but it is not mandatory since the program will determine that check was failed for this object.

Also, in the text found on the informational page for manga, it is important to get the number of characters in the manga. This is important since we want to provide the user with the number of characters they still have left to read. This adds additional logic since we might get negative numbers. For example, because users made a mistake writing number of characters (for example 300 instead of 30), or the website is not as relevant for this manga so it is late on updates for this title, or if a program found the most relevant manga to the search but it is a wrong manga and has less characters. Hence, while building I accounted for this cases. In case, if it is a negative number of characters, “unfortunately check for new chapters failed on url” and as a comment program says the negative difference detected and the name of the manga found for the case if it is a wrong manga found.

Also, for the website with similar structure, the problem uses CSS objects and correcting direct links. But in the second type (WEBTOON) of the website more text processing is needed since in order to find the correct link to the manga the program needs to know genera. So, if we want to add more resources, we need to create a transaction to either direct link or search and then we can use existing functionality of the program. Hence, this program can be expanded pretty easily and for an unlimited number of websites.

## Multiple Test Cases:

### Test 1:

- Honey Lemon
- yes
- 2
![Test1]("/images/Test #1.png")

### Test 2:

- Honey Lemon
- no

### Test 3:

- Honey Lemon
- [just press enter button]
- 3

### Test 4:

- Honey Lemon
- Yes
- 20

### Test 5:

- the gamer
- yeh
- 300

### Test 6:

- My Giant Nerd Boyfriend
- Y
- 100

### Test 7:

- hl
- Yeah
- 0

## Conclusion:

To sum up, I enjoyed this first personal project because I can see myself using and improving it in the future due to my interest in manga. Moreover, being a practical person, I have struggled for a while with my classes at UCLA being too theoretical and not connecting to my non-academic interests or real life. Hence, this little project strengthen my confidence and interest in continuing to study since it demonstrated that this class and the past classes prepared me to work independently and gave me the necessary tools to make my ideas come true even if they are silly like helping to find chapter updates for a manga. Also, next, I hope to do a different project for a more serious real-life topic/issue with friends or by myself over the upcoming winter.
