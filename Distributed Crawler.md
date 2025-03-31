
What is Web crawler
- A bot that systematically visits the websites and fetches contents from the website for use.
##### USE cases
1. Search engine  -> Google Bing
2. copyright violations -> 
3. Key word based finding -> search keywords like sharemarket , stocks  etc
4. Web Malware detections
5. Web analytics
6. LLM/Data-science world


## Requirement
####  Functional Requirement
1. Priority Crawling
2. Crawl web pages (HTML Only)
3. preserve crawled pages 
4. Duplicate Detection
5. Freshness on the Page
6. DNS Query
#### Non Functional Requirement
1. Distributed Crawling
2. Fault Tolerant 
3. Extensible for other type of content 
4. Robust
5. Highly available

##  Scale 
 
refer [[Capacity Estimates]]   for how to do  calculations effeciently
On internet there are 1 billion pages 1 * 10^9  pages
out of this 50 % are only maintained  500 million =  5 * 10^8  websites 
each website has ~100 page
So Total pages of website = 100 * 5 * 10^8

one page generate 100Kb of data
Total size = Total Pages * size of one page 
100 * 5 * 10^8* 100 kb
100 x 5 x 10^8 x 100 x 10^3 
5 x 100^15
5 PB of data storage is needed for one run







