# Data Exploration for PISA 2012 dataset
## by Anh Nguyen


## Dataset

The Program for International Student Assessment (PISA) is the global survey developed by the Organization for Economic Co-operation and Development (OECD) 
to evaluate the competencies of 15-year-old students in reading, mathematics and science, family backgrounds, and educational systems. 65 countries and economies participated in PISA 2012. 
Of those countries and economies, 44 took part in an assessment of creative problem solving and 18 were assessed in financial literacy.

The PISA 2012 dataset has 485,490 student records grouped in 636 columns. Here, I only focused on some features of interest such as country of residence, 
OECD membership, student's gender, parents' education level; 
academic performance in Math, Science, and Reading along with the corresponding learning time.

* The PISA zip file (325 MB) is provided in the Udacity learning site [HERE](https://www.google.com/url?q=https://s3.amazonaws.com/udacity-hosted-downloads/ud507/pisa2012.csv.zip&sa=D&ust=1581581520574000). 
* Extract the zip file above, we have a CSV file (2.75 GB) named *pisa2012.csv*.
* Details about the data dictionary can be found [HERE](https://www.google.com/url?q=https://s3.amazonaws.com/udacity-hosted-downloads/ud507/pisadict2012.csv&sa=D&ust=1554482573645000).

The main features of this dataset are plausible values for mathematics, science, and reading along with 3 learning time columns. 
According to the PISA 2012 Technical Report [(LINK)](https://www.oecd.org/pisa/pisaproducts/PISA%202012%20Technical%20Report_Chapter%209.pdf), 
these plausible values are not actual test scores but random numbers drawn from the distribution of scores that could reasonably be assigned to each individual. 
Various factors can affect these test scores, so taking the average across each subgroup is best.  

## Summary of Findings

### 1. Distribution of Scores
All histogram of scores follows a clear normal distribution, ranging from 200 to 800 each. 
The total scores also exhibit a normal distribution pattern.

![image](https://github.com/qanhnn12/dax-note/assets/84619797/a14006ad-41d7-4c88-aac9-a70efd3d4b5d)

### 2. Distribution of Learning time
All distributions are right-skewed. The peak for each subject's learning time is about 180-220 minutes per week.

![image](https://github.com/qanhnn12/dax-note/assets/84619797/32bdc8fc-f78a-422f-b90f-96074b894e65)

### 4. Scores by Gender
Overall, male and female students have similar total scores. 
Female students have better performance in Reading while male students perform slightly better in Math. 
Both genders perform equally well in Science.

![image](https://github.com/qanhnn12/dax-note/assets/84619797/ad1dbc09-e02b-4969-920b-adee216ef4a7)

### 4. Scores by OECD membership
OECD countries have better performance in all subjects than non-OECD countries.

![image](https://github.com/qanhnn12/dax-note/assets/84619797/90091d3c-6dac-4020-bbe2-c749374bb810)

### 5. Total score by parents' education
A similar trend can be seen between both parents with their children's total score. 
Students whose parents have higher level of education are more likely to perform better. 
But for parents with educational levels from Upper Secondary to Vocational Tertiary, 
the difference in their children's performance is less significant.

![image](https://github.com/qanhnn12/dax-note/assets/84619797/dbd3c287-0934-4962-991e-c31ac7e3262a)

### 6. Correlation between Scores
All scores show a positive correlation, suggesting that if a student performs well in either of 
the 3 subjects, he or she also performs well in the other two. 
Notably, the graph about Math and Science has the highest level of density, 
so these two subjects have the strongest correlation.

![image](https://github.com/qanhnn12/dax-note/assets/84619797/afd4f049-7137-4b61-ac16-c6551b94369e)

### 7. Scores by Gender and OECD membership
Overall, OECD students tend to perform better than non-OECD students. 
On average, males perform better in Math while females perform better in Reading. 
However, for Science, the median score of females is higher in OECD countries 
but lower in non-OECD countries.

![image](https://github.com/qanhnn12/dax-note/assets/84619797/d701206f-480b-4b62-a968-0860d123e279)

### 8. Total learning time by Gender and OECD membership
While females and males have the same learning time in non-OECD countries, 
males have longer learning time than females in OECD countries. 
Interestingly, the learning time of female students in non-OECD countries is slightly longer 
than those from OECD countries.

![image](https://github.com/qanhnn12/dax-note/assets/84619797/8e05632d-2651-4da4-be76-a21a6797c778)


## Key Insights for Presentation
I will first take a look at the distribution of scores and learning time. 
Then I will go through the impact of background factors such as gender, 
OECD membership, parents'education on students' performance and study time.
