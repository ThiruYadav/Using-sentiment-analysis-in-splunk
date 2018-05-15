# Using-sentiment-analysis-in-splunk

(I want to use sentiment analysis app for social media data. Please can anyone tell me the step by step procedure.
1. How to insert data to sentiment analysis app ?
2. How to extract data from social media ? In which format ? 
3. Do we need to change any conf files ?
Please put some light on all these.
Is there any detailed documentation for using this app ?
I am using windows machine. Will it work only in linux ?)

The sentiment analysis app uses a training dataset to learn and uses your data to analyze the sentiments. Two training datasets are included with the app. For social media analysis Twitter training data (included) would be ideal.

Inserting data into sentiment analysis app can be done directly through the search. 

You can extract data from social media (in this case, twitter) using rest api. Follow this - http://blogs.splunk.com/2014/07/03/splunking-social-media-tracking-tweets/ or https://discoveredintelligence.ca/stream-twitter-splunk-10-simple-steps/

No, you don't really need to meddle with the conf files for this.

Once you have your tweets streaming into Splunk, you can use a SPL query such as sourcetype=tweets | sentiment twitter text.

Here, tweets is the name of the sourcetype you have given while setting up your twitter app. The syntax for sentiment analysis app is: sentiment . 'Twitter' is the name of the included training data. You can use your own training data by adding it into the same directory. 'text' is the field name derived from the search which contains the content of the tweets, which need to be analyzed.

This video can give you some additional details -https://www.youtube.com/watch?v=EU1sgObvrbI
