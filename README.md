# Izen's Git Practice Repository

## An Article I Found Interesting

[Building Akinator with Python using Bayes Theorem](https://medium.com/analytics-vidhya/building-akinator-with-python-using-bayes-theorem-216253c98daa)

*By Rogério Chaves*

## Why I Find It Interesting

This article shows how to build the guessing game Akinator in Python using Bayes' theorem. In the game, you think of a character and the program asks you yes or no questions until it guesses who it is. After every answer, the program uses Bayes' theorem to update how likely each character is to be the right one. Characters that match your answers become more likely, and the ones that don't become less likely, until one clearly stands out.

What I liked most is that a game that feels almost like magic is really just simple probability repeated over and over. I followed this article myself to build my own version of Akinator in C++. I also added something that isn't in the article: a variance formula to help the program pick the best question to ask next. Instead of asking questions in a fixed order, it looks for the question whose answer will tell it the most about which character you are thinking of. This helped the game guess correctly in fewer questions, and it was a fun way to see math I learned in class actually being useful.

# Comment from Muhammad Hamza
Good pick. What strikes me reading this is that most of the cleverness in Akinator isn't in the Bayes update at all and that part is mechanical and it's in choosing which question to ask next, which is exactly the bit the original article glosses over. So your variance addition is arguably the more interesting half of the project. It's also close to what decision tree algorithms do when they pick a split, just reached from the game side rather than from a textbook, which is a better way to end up understanding it. The one thing I'd push on: naive Bayes assumes the answers are conditionally independent given the character, and in practice they're heavily correlated — "is your character fictional" and "does your character have superpowers" are carrying a lot of the same information, so answering both double-counts the evidence. It still works, which is the genuinely surprising part. Curious whether you noticed the probabilities getting overconfident too fast in your C++ version, since that's usually where it shows up.

# Comment from Noor Khan
Really fun pick. It's a great example of how a small amount of probability can feel like intelligence from the user's side. One thing I kept thinking about is what happens when the *player* is wrong. People misremember details or interpret questions differently, and if the model ever assigns a character a probability of exactly zero after one mismatched answer, that character can never come back, no matter how well every other answer fits. A common fix is to treat each answer as noisy, for example assuming there's always a small chance someone says "yes" when the true answer is "no". That way one mistake lowers a character's probability instead of eliminating it.

I also liked your variance-based question selection. It's closely related to picking the question with the highest expected information gain (entropy reduction), which is how decision trees choose splits. It would be interesting to compare the two in your C++ version and see which one gets to the right character in fewer questions on average.
