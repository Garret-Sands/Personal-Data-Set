# Personal-Data-Set

As a religious person myself I am interested to know more about religion. I am
particularly interested in the polling information of members from different religions 
with-in the confines of the United States. I wanted to know how religions differed along 
controversal topics. Once I came across data that polled abortion beliefs I knew that I 
had found what I wanted.

The category 'Score of dedication' was constructed from the average of all percentage categories 
collected from each religion in the "Raw Data" page. Once formed, the 'Score of dedication' was 
juxtaposed next to the percent of people who 'believe abortion should be illegal all/most of the time'.
This wording was from the pewforum poll. 

In the visualization comparing 'Score of dedication' and '%Ab_ill', I did not include the
'Unaffiliated'. I excluded this category because of its status as an outlier and the unkown 
information around this category. 


R Code:

library(readr)
Personal <- read_csv("C:/Users/Garret's Laptop/OneDrive/Desktop/Personal.txt")
View(Personal)

library(ggplot2)
barplot(Personal$Score_of_Dedication, names.arg = Personal$Religion, xlab ="Religion", 
        ylab ="Score of Dedication", col ="green")


ggplot(mapping=aes(x=Personal$Score_of_Dedication, y=Personal$Ab_ill)) + geom_point()

Lin_Reg <- lm(Personal$Ab_ill ~ Personal$Score_of_Dedication)
summary(Lin_Reg)







