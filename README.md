# Capstone

 Capstone- Praharshita Kaithepalli
Image results: https://github.com/pk2971/Capstone/tree/main/Images
CSV and Text results: https://github.com/pk2971/Capstone/tree/main/Results 
## Pronoun Analysis:
GitHub: https://github.com/pk2971/Capstone/blob/main/Code/Pronoun%20Analysis.ipynb 

At any given year, the number of male pronouns is consistently higher than the female pronouns. 
There is an increase in the amount of female pronouns throughout the years.
All though it has to be noted that in the feature importance analysis later it has been found that the sentences related to female pronouns/words are returning country names.
When the text data was examined it was found that in the 1900s they were referring to countries and ships as ‘she’ or ‘her’. So though it might show up as pronoun count, the actual number is lower than we think.

Example from 1927:
“America decided to nationali se shipping and to control all the ships, but she is very glad indeed to be out of it to-day.”
“Nature provides her own antidotes for these diseases.”


## Word embedding:
GitHub: https://github.com/pk2971/Capstone/blob/main/Code/Word%20embedding.ipynb 

In the 1800s, woman were not represented well in the parliament, words like concubine, seducer, prison etc showed up in the word-cloud. While men were associated with soldiers and noblemen.

In the 1900s, women were associated with relationships such as wife, mother, husband, bride etc. Probably due to the wars the words widower and soldier showed up. But the word breadwinner is a good sign. While men were associated with soldier, policeman, miner etc.
There is not much difference between the words associated with women 10 yrs before and after the suffrage(1928). 
Even in 2000s women are still being associated by relationships such as mother, son, wife etc. A lot of negative words like trauma, beaten, tortured etc also showed up.






## Token Analysis:
Split the words into tokens based off of white space, counted and plotted them.
Github: 
Token count: https://github.com/pk2971/Capstone/blob/main/Code/Token%20Analysis.ipynb 
Top 5 words by year: https://github.com/pk2971/Capstone/blob/main/Code/top%205%20words%20by%20years%20only%20female%20related%20sentences.ipynb 
Top 5 words by year(only female related sentences):
https://github.com/pk2971/Capstone/blob/main/Code/top%20words%20by%20year.ipynb 

Based upon the line graph we can see that the amount of conversation that is being had is increasing. But also it is a time series graph based upon how it is going up and down throughout the years.

For a better understanding of the text data, top 5 words for every  year were found. 
Most of the words were related to conversation terms. Words were slightly different in each year, but words were similar in the surrounding years. 

Top words in 1927 and 1928:

1927
['hon.', ',', 'right', 'think', 'member', 'bill', 'great', 'say', 'question', 'gentleman']
1928
['hon.', ',', 'right', 'think', 'member', 'great', 'question', 'say', 'gentleman', 'bill']



Top words in 1927 and 1928 in sentences related to women:

1927
['women', ',', 'men', 'number', 'great', 'woman', 'girls', 'minister', 'children', 'case']
1928
['women', ',', 'number', 'men', 'minister', 'hon.', 'labour', 'employment', 'case', 'persons']


In both of the years, though the words differ, in the words related to women we can see ‘children’, ‘men’ etc. Women are still being represented as relationships.

## Feature importance:
GitHub: https://github.com/pk2971/Capstone/blob/main/Code/Feature%20Importance.ipynb 
TfidfVectorizer is a scikit-learn class that converts a collection of raw documents to a matrix of TF-IDF features.
The fit_transform method converts the text data into a sparse matrix of TF-IDF features.
feature_names = vectorizer.get_feature_names_out()
It retrieves the feature names (terms) from the vectorizer.
Then the features are compared to the last century to show the difference in importance. 
1800s to 1900s, 1900s to 2000s are compared. 
10 years before and after suffrage are also compared.

Results: 
A lot of the important feature words are words that are used in conversations in the parliament. That is why we had to generate 200 words to get some decent results.
In the 1800s century we find words related to countries, such as India, England, Scotland. The word war was also on the list of high importance.
In the 1900s century, we see words like ‘Industry’, ‘Education’, ‘trade’, ‘Employment’ make an appearance in the high importance vectors. Due to the occurrence of world wars, the word ‘war’ is also on the list.
In the 2000s, ‘health’, ‘house’, ‘service’ made it to the top of high importance words. Words like ‘police’, ‘education’, ‘transport’ etc made it to the list. There is no word ‘war’ in the 2000s list but the word ‘defense’ is present.

Language changes from 1800s to 1900s:

ireland
0.1015976210881740
0.0343694465317822
0.0672281745563922


war
0.0357498976604474
0.0416305526927709
0.005880655032323500


gentleman
0.1386314030820730
0.084566411106952
0.05406499197512130


tax
0.0255840035667537
0.0347838108177556
0.009199807251001900

Language around the words related to countries like Scotland, Ireland have decreased. The importance of the word ‘war’ has increased across the centuries. 
An interesting change in language was seen, where people probably stopped referring to each other as ‘gentlemen’. There has been a slight increase in the importance of the word ‘tax’. 

Language changes from 1900s to 2000s:

health
0.0583160759497475
0.1043433627999610
0.0460272868502133


police
0.0294057250169509
0.0590916242561681
0.029685899239217200


gentleman
0.084566411106952
0.0474527612170502
0.0371136498899018


trade
0.0556796811009351
0.0344276965125991
0.021251984588336


defence
0.031825705599986
0.0468532139075157
0.015027508307529700


development
0.0384340757279921
0.0491447722483204
0.0107106965203283


education
0.047322364323903
0.0577537082801935
0.0104313439562905


tax
0.0347838108177556
0.0396807771340575
0.004896966316301900

The importance for the words ‘health’, ‘development’, ‘police’, ‘defense’  has increased from 1900s to 2000s. As seen before the importance for the word ‘gentlemen’ has decreased.

There has not been a significant change in the language from 10 yrs before suffrage to 10 years after suffrage.

## Text summarization:
GitHub: https://github.com/pk2971/Capstone/blob/main/Code/Text_summarization.ipynb 
I was expecting the words related to women or suffrage to show up in the feature importance part, but unfortunately the representation of women is very less for these words to make it to high feature importance. 
With the help of a function, sentences having keywords related to women were extracted and summarized.
Summarization was achieved using a pre-trained BART (Facebook's "BART: Denoising Sequence-to-Sequence" model).
For each paragraph, it tokenizes it using the BART tokenizer, generates a summary using the BART model, decodes the generated summary.
Results: 
Word summarization model was used to summarize the sentences related to women in 1927 and 1928, the years before and during suffrage. 

In the year 1927, there was only one discussion regarding suffrage. The summary is as follows: 
”asked the Prime Minister on what date he proposes to make his promised statement on the granting of Parliamentary suffrage to women at the age of 21. If a question on that matter is desired to be put, it had better be addressed to the Chancellor of the Exchequer.”
In the year 1928, there were no sentences having suffrage and women related words in the same sentences. 

Conclusion:

While the word clouds provided valuable insights into the evolving language and representation of women, I sought a more comprehensive analysis. Turning to token analysis, I aimed to identify the predominant words each year. However, this approach proved challenging as the top words were largely centered around general conversations, offering limited assistance. Compounded by the scarcity of words specifically related to women, their presence in the list was minimal.

Undeterred, I developed code to extract sentences featuring keywords pertinent to women, summarizing the findings using NLP techniques. This method yielded promising results. Nevertheless, it became apparent that the overall representation of women in the British Parliament remains exceedingly low.














