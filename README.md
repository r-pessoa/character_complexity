  
# character_complexity
Ranking CJK characters according to stroke and radical complexity


I've been learning Chinese for over 10 years, and in the meantime I've also taught and translated some. Characters are arguably the most alluring part of the Chinese language, and also one of the most difficult to learn. To this day, I still forget how to write a lot of them.

While I was teaching, I was constantly faced with the tradeoff: tell students to learn the characters of every new word, however hard they are to memorize (谢谢，跳舞), and risk demotivating them, or give them only the easy ones at first, including characters for which they haven't learned the words yet (人，口，木，保), and risk alienating them.

With this in mind, I tried to come up with a way to rank Chinese characters according to difficulty, while at the same time weighing them according to frequency.

The result is this table:

The code is available in my GitHub.

For character decompositions, I referred to 

[https://archive.codeplex.com/?p=cjkdecomp](https://archive.codeplex.com/?p=cjkdecomp)

For the 1,000 most frequent characters, I referred to data from 

[https://lingua.mtsu.edu/chinese-computing/statistics/char/list.php?Which=MO](https://lingua.mtsu.edu/chinese-computing/statistics/char/list.php?Which=MO)

The formula I used for ranking character by easiness was:

`$$`{\sum\limits_{i=1}^{c} f_i \over c^2}`$$`

where $f_i$ is the frequency count for each stroke and radical and c is stroke and radical count. Note that the numerator is linear, while the denominator is exponential - I decided to penalize characters exponentially for having a high stroke count. Of course, if you want to calculate the complexity, just take the inverse.
