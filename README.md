# Izen's Git Practice Repository

## An Article I Found Interesting

[Building Akinator with Python using Bayes Theorem](https://medium.com/analytics-vidhya/building-akinator-with-python-using-bayes-theorem-216253c98daa)

*By Rogério Chaves*

## Why I Find It Interesting

This article shows how to build the guessing game Akinator in Python using Bayes' theorem. In the game, you think of a character and the program asks you yes or no questions until it guesses who it is. After every answer, the program uses Bayes' theorem to update how likely each character is to be the right one. Characters that match your answers become more likely, and the ones that don't become less likely, until one clearly stands out.

What I liked most is that a game that feels almost like magic is really just simple probability repeated over and over. I followed this article myself to build my own version of Akinator in C++. I also added something that isn't in the article: a variance formula to help the program pick the best question to ask next. Instead of asking questions in a fixed order, it looks for the question whose answer will tell it the most about which character you are thinking of. This helped the game guess correctly in fewer questions, and it was a fun way to see math I learned in class actually being useful.