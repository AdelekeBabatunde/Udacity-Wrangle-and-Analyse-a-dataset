# Udacity-Wrangle-and-Analyse-a-dataset
## Data Wrangling for the WeRateDog tweets
The data wrangling steps are highlighted as follows

> Data Gathering

> Data Assessment

> Data Cleaning

## Data Gathering
Data was gathered from three sources given below

1. Tweeter Arhcive data for WeRateDogs tweets in a CSV file provided by Udacity. This file was programatically downloaded in the python notebook using the link provided in the resources tab of the Udacity project

2. The image prediction file for dogs also provided by Udacity in a tsv file. This file was also programatically downloaded and saved in the workspace

3. Retweet and favorite counts for each tweet in the archive data. This data was pulled from twitter using the twitter developer API

## Data Assessment
Data Assessment was carried out visually and programatically on all the datasets.

The following quality issues where detected
1. Remove unwanted records i.e. retweets and replies from the archive table and leave only original tweets

2. The column id in the tweet api table should be changed to tweet_id for standardization of tweet_id across the data sources.

3. Invalid datatypes for columns tweet_id and timestamp

4. Some tweets had "\&amp" combined with ";" which is the html code to display just the ampersand

5. The dog rating columns (numerator and denominator) need to be fixed

6. Source column is in HTML-formatted string

7. Columns in_reply_to_status_id, in_reply_to_user_id, retweeted_status_id, retweeted_status_user_id, retweeted_status_timestamp have many missing values

8. Many missing names from the list under 'None', and random names like 'a' and 'an' might be parts of strings that got taken out of context.

The following Tidiness issues where detected
1. doggo, floofer, pupper and puppo columns in twitter archive table should be merged into one column named "dog_stage"

2. The three tables should merged to one

## Data Cleaning
The define-code-test framework was used in the data cleaning process. The quality and tidiness issues where solved as indicated below

#### Fixing Quality issues
1. Remove retweets and replies were removed from the archive table so we are left with only original tweets

2. The column id in the tweet api table was changed to tweet_id for standardization of tweet_id across the data sources.

3. The data type for timestamp column in the tweeter archive dataset was changed to datetime64 als The tweet id for all tables was changed to object

4. The text data was cleaned of html code by removing the html code &amp and the links included in text

5. Rating Denominators with zero value were removed, data types for numerator was changed to float and data type for denominator was changed to int. Also a new column was created for rating by dividing the numerator by the denominator

6. HTML Formatting was removed from the source column

7. unwanted columns were removed from the twitter archive dataset i.e. in_reply_to_status_id, in_reply_to_user_id, retweeted_status_id, retweeted_status_user_id, retweeted_status_timestamp

8. The dog name column was cleaned to remove invalid dog names

#### Fixing Tidiness issues
1. doggo, floofer, pupper and puppo columns were merged into one column named "dog_stage"

2. The three tables were merged to one table and the result was saved to twitter_archive_master.csv in the workspace
