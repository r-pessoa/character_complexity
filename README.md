  
# character_complexity
Ranking CJK characters according to stroke and radical complexity

Context: When teaching/learning Chinese characters, there is a tradeoff between necessity and complexity. Some basic words （谢谢, 跳舞）are represented by some rather difficult characters for a beginner. On the other hand, some less relevant characters from a beginner's vocabulary perspective are not only simpler, but also represent buiding blocks for more complex characters (目，木，口，土）.

In this project, I tried to come up with a way to rank Chinese characters according to difficulty (complexity), while at the same time weighing them according to frequency (necessity).

The result is in finaltable.xlsx

The code is in Hanzi.ipynb

For character decompositions, I referred to 

[https://archive.codeplex.com/?p=cjkdecomp](https://archive.codeplex.com/?p=cjkdecomp)

For the 1,000 most frequent characters, I referred to data from 

[https://lingua.mtsu.edu/chinese-computing/statistics/char/list.php?Which=MO](https://lingua.mtsu.edu/chinese-computing/statistics/char/list.php?Which=MO)

The formula I used for ranking character by easiness was:

sum(F_i)/C\**2

where F_i is the frequency count for each stroke and radical, and C is stroke and radical count. Note that the numerator is linear, while the denominator is exponential - I decided to penalize characters exponentially for having a high stroke count. Of course, if you want to calculate the complexity, just take the inverse.
