# OCD_Patient_DP
Exploration of different methods for implementing differential privacy on a database of OCD patients

Collaborators: Catie Crowell, Johnna Schulz

This analysis aims to identify the demographic factors that increase susceptibility to Obsessive-Compulsive Disorder (OCD) diagnosis using the "OCD Patient Dataset: Demographics & Clinical Data." In this differentially private breakdown of the dataset, we implemented two noise mechanisms (Laplace and Gaussian). We compared the value counts across different mechanisms after adding noise to the data. We also predicted the probability of a person having certain compulsions based on their obsessions. Then, we predicted the likelihood and severity of OCD in patients based on demographic factors such as age, gender, education, and ethnicity.

The project aims to predict OCD susceptibility based on traits, starting with analyzing data value counts. To streamline analysis, three columns of the dataset were dropped - Patient ID, Medications, and OCD Diagnosis Date. Two tests were conducted on the original queries: one with Laplace noise and one with Gaussian noise added to the values for obsession and compulsion types. It was found that adding Laplace noise was much more useful and managed to provide privacy while still giving accurate and useful data. Functions were then implemented to predict a person's obsession type based on their compulsion type. The first function takes the compulsion type and finds the obsession type with the highest occurrence given that a person has that compulsion and then returns the highest occurring obsession type. The second function takes in a person’s compulsion and obsession type, which is then used to find the probability of that combination. Next, we were curious to see if it was possible to predict the Y-BOCS score from a specific demographic. The Y-BOCS score is the product of a clinical assessment of the severity of a person’s obsessions and compulsions. The functions of the project compute the average Y-BOCS score by taking into account a person's age, gender, ethnicity, and education level. This can be highly useful in identifying individuals who have severe obsessions and compulsions and can indicate the likelihood of an OCD diagnosis. For example, a person who is female, African, 32 years old with some college is most likely to have a Y-BOCS Obsession score of 17.3, which suggests moderate symptoms, and a compulsion score of 10.3, which is also moderate. However, a 32-year-old Caucasian male with a college degree is most likely to have a Y-BOCS obsession score of 2 and a compulsion score of 5, both of which suggest much milder symptoms. Following this, two more functions add noise to the Y-BOCS results. After comparing Laplace and Gaussian noise errors from the Y-BOCS functions, we concluded that Laplace noise was once again more accurate with less average error compared to Gaussian noise.

The most important outcome of this project is a precise and practical function that can predict the severity or presence of OCD in an individual based on their selected traits while maintaining the confidentiality of the results with noise. Additionally, we were able to predict the specific obsessions and compulsions of an individual by using their age, gender, ethnicity, and college education.

References:

Near, J. (2023). Data Privacy. University of Vermont.

Chowdhury, S. H. (2023, November 9). OCD patient dataset: Demographics & Clinical Data. Kaggle. https://www.kaggle.com/datasets/ohinhaque/ocd-patient-dataset-demographics-and-clinical-data 
