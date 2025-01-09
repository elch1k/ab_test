Here I dive into ordinary Data Analyst task to make a common AB test. As I mentioned in .ipynb file it's really necessary to properly model the whole experiment: determine hypotesis, choose right metrics and randomization units, calculating sample size with a predetermined power and significance level and etc.. 
This is a truly difficult and expensive process that a company must be confident in choosing. In my way I just grab data from the [kaggle](https://www.kaggle.com/datasets/sergylog/ab-test-data) and then just make some research and AB test analysing. Since I did not have clear conditions for what to research, I simply took into account all possible variants that might be interesting from this AB test data.

Well, the research was conducted around all users and payment users. We can now see their distribution, and as we see, there are many more ordinary users which distort our data, but i'm still research both situation.
![image_01](https://github.com/elch1k/ab_testing/blob/main/images/image_01.png?raw=true)

After a little EDA we have to choose the right test for the data, but these steps are detailed in the [notebook](https://github.com/elch1k/ab_testing/blob/main/AB_test_project.ipynb). I then chose the Mann-Whitney U test for my data where I ended up failing to reject H0 in both options. After that I tryied to implement universal method called bootstrap.

We can observe a difference in the comparison of mean (average) revenue between all users and paying users.
![image_02](https://github.com/elch1k/ab_testing/blob/main/images/image_02.png?raw=true)
![image_03](https://github.com/elch1k/ab_testing/blob/main/images/image_03.png?raw=true)

As we see that in both situation we have variant group even worse than control, from this we can assume that our new change is not so good as we wanted.

And finally solution by bootstrap method.
![image_04](https://github.com/elch1k/ab_testing/blob/main/images/image_04.png?raw=true)
![image_05](https://github.com/elch1k/ab_testing/blob/main/images/image_05.png?raw=true)

## Conclusion
In this A/B testing project, we applied various methods and techniques, uncovering several important insights, such as issues with data collection, lack of proper randomization between groups, the presence of outliers, data distribution patterns, and the absence of significant differences between our metrics. More detail in [notebook report](https://github.com/elch1k/ab_testing/blob/main/AB_test_project.ipynb).
