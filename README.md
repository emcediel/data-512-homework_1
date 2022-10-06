# data-512-homework_1

Our goal is to analyze dinosaur article traffic from English Wikipedia, specifically between July 1, 2015 and September 30, 2022. Through this repo, we have been able to construct, analyze and publish this work collecting data through Pageviews API (details on access, license and use below), that provides access to desktop and mobile trafic data. 

## Pageviews API

The Pageviews API documentation covers additional details that may be helpful when trying to use or understand this example can be found in the following link: https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews. 

Additional information to the Wikimedia Foundation REST API terms of use can be found here: https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions

This is the link to the REST API: https://www.mediawiki.org/wiki/Wikimedia_REST_API

Global Rules
Limit your clients to no more than 200 requests/s to this API. Each API endpoint's documentation may detail more specific usage limits.
Set a unique User-Agent or Api-User-Agent header that allows us to contact you quickly. Email addresses or URLs of contact pages work well.

By using this API, you agree to Wikimedia's Terms of Use and Privacy Policy. Unless otherwise specified in the endpoint documentation below, content accessed via this API is licensed under the CC-BY-SA 3.0 and GFDL licenses, and you irrevocably agree to release modifications or additions made through this API under these licenses. See https://www.mediawiki.org/wiki/REST_API for background and details.

## Files inside repo
### Source files
1. View data was retrieved fully from the REST API
2. The names of the dinosaur articles were obtained through the 'dinosaur_genera.cleaned.SEPT.2022 - dinosaur_genera.cleaned.SEPT.2022..csv' csv file 

## Intermediary files

Three JSON files were created, each contains article traffic information for a specific type of access (mobile, desktop, monthly cumulative)
The key for the JSON file is the name of the article (dinosaur)
Each article contains a list of monthly datapoints containing:
    a. project: The domain of any Wikimedia project, for example 'en.wikipedia.org', 'www.mediawiki.org' or 'commons.wikimedia.org'.
    b. article: 'The title of any article in the specified project. 
    c. granularity: The time unit for the response data. As of today, the only supported granularity for this endpoint is daily and monthly.
    d. timestamp: The monthly date of the data
    e. agent: If you want to filter by agent type.

## Output files

3 graphs were created:
1. Maximum Average and Minimum Average - The first graph should contain time series for the articles that have the highest average page requests and the lowest average page requests for desktop access and mobile access. 
2. Top 10 Peak Page Views - The second graph should contain time series for the top 10 article pages by largest (peak) page views over the entire time by access type. You first find the month for each article that contains the highest (peak) page views, and then order the articles by these peak values. 
3. Fewest Months of Data - The third graph should show pages that have the fewest months of available data. These will all be relatively short time series, some may only have one month of data. 

## Data limitations and special considerations

Not all articles have full data, some contain nulls in many of months. 

The API outoputs in JSON format, will have to use functions to transform to any other desired data format.

When obtaining data from the API remeber that Global Rules limit your clients to no more than 200 requests/s to this API. Each API endpoint's documentation may detail more specific usage limits. Set a unique User-Agent or Api-User-Agent header that allows us to contact you quickly. Email addresses or URLs of contact pages work well. We recommend using delays when requesting data to comply with these terms.


