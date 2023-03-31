# I310D-Assignment10

The purpose of this project was to test the [Perspective API](https://perspectiveapi.com/) on a sample datatset to reveal any potential biases the API may have. The Perspective API utilizes machine learning to judge comments based on their perceived toxicity, and return a decimal score from 0 to 1, with 0 being not toxic and 1 being extremely toxic.

## Hypothesis

I theorized that Perspective may possibly treat comments in all-uppercase as more "toxic" (deemed by the toxicity score) than comments in lowercase.

## Testing
The sample dataset given had a list of comments that were deemed "toxic" or "not toxic" by human volunteers. I combed through the sample dataset and filtered the comments by those labeled toxic, and tested Perspective on the first 50 comments. Averaging out the toxicity score of these 50 comments gave me a benchmark score of 0.72 over which I defined any comment as meeting or exceeding that score to be "toxic".

Next, I sorted through the sample data and made a new dataset of 50 all-lowercase comments that were also labeled as "not-toxic". I created an identical dataset of the same 50 comments but made them uppercase, and ran Perspective on both datasets to see if there was any tangible difference. I also stored the toxicity scores of both datasets in lists to visualize the results in graphs. 

## Results
The lowercase comments had a mean and median toxicity score of 0.2. The uppercase comments had a mean toxicity score of 0.24 and median of 0.15, showing slight variance. Catplots graphed of both lists showed only minor differences but demonstrated that they both followed the same overall trends and had the same shape. 

## Analysis
While the graphs between uppercase and lowercase toxicity scores vary slightly, both yield extremely similar results and therefore it can not be concluded that there is any significant bias in the Perspective API between uppercase and lowercase comments. 

However, we can see two interesting pieces of information:
1. Perspective did flag a single comment from both datasets as toxic (per our definition), with a few other values trailing behind. For a dataset of comments that were deemed non-toxic (as per the dataset's definition), it is interesting that certain comments would be flagged so high. These could simply be outliers indicative of the fact that Perspective is not perfect.
2. Certain comments that have been labeled as non-toxic by the dataset include content that certainly could be considered toxic to another person. This could be the another reason why certain comments have Perspective toxicity scores above 0.5 and why one was flagged as toxic by Perspective.

All in all, my hypotheses was not validated but there are other interesting questions to chase with this data.

## Libraries and APIs used
- [Pandas](https://pandas.pydata.org/)
- [Seaborn](https://seaborn.pydata.org/index.html)
- [Perspective](https://perspectiveapi.com/)

## License
- [MIT License](https://github.com/utsav-nimavat/I310D-Assignment10/blob/600c27d7626acf1be47fef7a68d07d18492dfb91/LICENSE) 
