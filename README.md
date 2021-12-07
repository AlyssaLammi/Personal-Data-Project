# Personal-Data-Project

## Motivation
When I started this project, I wanted to see what the difference between men's and women's pay was in STEM. Which is what motivated me to choose this dataset because it contains the average median pay for men and women arcoss a variety of fields. I choose with this dataset instead of choosing a strictly STEM pay focused dataset because I thought that it would be more interesting (and I simply just got curious when I stumbeled upon this dataset) to see what the pay gap was like across more than just STEM. In school, whenever a pay gap does get mentioned, it is always STEM focused and I wanted to go beyond that and show that, in general, women are paid less than men no matter the field. 

## Data Process
The data that I collected for this project came from the United States Census Bureau and can be downloaded here:
https://data.census.gov/cedsci/table?q=median%20earnings%20by%20sex&t=Employment%3AEmployment%20and%20Labor%20Force%20Status&tid=ACSST1Y2019.S2411. I personally used the data from 2019 though similar analysis could be done for any/all of the years where this kind of data was collected. The only thing I changed when it comes to the dataset is the column names. I wanted to condense them down a little in order to, hopefully, make them easier to understand. There wasn't any blank spots in the dataset or anything that seemed out of place which is why I did not do much, if any, actual cleaning of the dataset. One thing I really like about this dataset is that it actually accounts for a certain margin of error that can happen when it comes to collecting this kind of data. I did not do anything with this margin of error though I think that it could make for interesting observation.

## Visualization

### Figure 1
<img src="https://raw.githubusercontent.com/AlyssaLammi/Personal-Data-Project/main/Median%20Earnings%20for%20Men%20vs%20Women%20Scatterplot.png">
Caption: A scatterplot of the column 'Median Earnings for Male Estimate (Dollars)' by the column 'Median Earnings for Female Estimate (Dollars)' from the dataset.
ggplot(data, mapping = aes(x=data$`Median Earnings for Male Estimate (Dollars)`, y=data$`Median Earnings for Female Estimate (Dollars)`)) + geom_point() + xlab("Median Earnings for Men") + ylab("Median Earnings for Women") + ggtitle("Median Earnings for Men vs Women")

### Figure 2
<img src="https://raw.githubusercontent.com/AlyssaLammi/Personal-Data-Project/main/Median%20Earnings%20for%20Men%20vs%20Women%20Graph.png">
Caption: The same scatterplot as figure 1 just with a geom_smooth() line as line of best fit. The geom_smooth() line has nothing to do with linear regression.
ggplot(data, mapping = aes(x=data$`Median Earnings for Male Estimate (Dollars)`, y=data$`Median Earnings for Female Estimate (Dollars)`)) + geom_point() + xlab("Median Earnings for Men") + ylab("Median Earnings for Women") + ggtitle("Median Earnings for Men vs Women") + geom_smooth()

The two figures above (figure 1 and 2) show how, in general, men are paid more across all of the fields in the dataset than women are. They are also important because they show how the average median pay for women caps out at about $70,000 while there is not the same kind of limit or cap on the average median pay of men. 

## Analysis

### Figure 3
<img src="https://raw.githubusercontent.com/AlyssaLammi/Personal-Data-Project/main/MedIan%20Earnings%20for%20Men%20vs%20Women.png">
Caption: The same scatterplot as figure 1 but with a linear regression line over the top of it.
ggplot(data, mapping = aes(x=data$`Median Earnings for Male Estimate (Dollars)`, y=data$`Median Earnings for Female Estimate (Dollars)`)) + geom_point() + xlab("Median Earnings for Men") + ylab("Median Earnings for Women") + ggtitle("Median Earnings for Men vs Women") + geom_smooth(method=lm, formulta=y~x, color='blue')

The firgure above (figure 3) uses linear regression to further prove, beyond just looking at the graphed points, that men are, on average, paid more than women. It does this by highlighting the average median of men verse women in the form of a line which makes it easier to see the division in average pay. I did not learn anything new by using a linear regression model. I just used it to further prove what can be easierly seen by looking at the first scatter plot. 

Note: I considered taking out the two, seemingly outlying points from the scatterplot when doing the linear regression model but ended up just leaving them. I decided to leave them knowing that they would skew the linear regression model a little bit because I feel that the skew furthers my point. That said, I also left them so that anyone looking at the graph could see the major gap between the linear model and the outlying points. 
