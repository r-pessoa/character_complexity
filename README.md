  
# character_complexity
Ranking CJK characters according to stroke and radical complexity

I tried to come up with a way to rank Chinese characters according to difficulty, while at the same time weighing them according to frequency.

The result is this table:

The code is available in my GitHub.

For character decompositions, I referred to 

[https://archive.codeplex.com/?p=cjkdecomp](https://archive.codeplex.com/?p=cjkdecomp)

For the 1,000 most frequent characters, I referred to data from 

[https://lingua.mtsu.edu/chinese-computing/statistics/char/list.php?Which=MO](https://lingua.mtsu.edu/chinese-computing/statistics/char/list.php?Which=MO)

The formula I used for ranking character by easiness was:

[equation]("http://www.sciweavers.org/tex2img.php?eq=%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bc%7D%20f_i%20%5Cover%20c%5E2&bc=White&fc=Black&im=jpg&fs=12&ff=arev&edit=0" align="center" border="0" alt="\sum\limits_{i=1}^{c} f_i \over c^2" width="40" height="67")

where $f_i$ is the frequency count for each stroke and radical and c is stroke and radical count. Note that the numerator is linear, while the denominator is exponential - I decided to penalize characters exponentially for having a high stroke count. Of course, if you want to calculate the complexity, just take the inverse.
