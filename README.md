#### Newsfeed-Automation

Python


This is a demo to use docker-compose to build up a newsfeed automation website. It is implemented by using Python Flask(web server) and MSSQL(database).
#### Folder structure
Newsfeed<br/>

├──README.md<br/>
└──src<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└──data_challenges.py<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└──data_challenges.ipynb<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└──dewikinews-20190720-pages-articles-multistream.xml<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└──requirements.txt<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└──unigram_df_example.csv<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└──bigram_df_example.csv<br/>
└──example<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└──unigram_df(top100_example).csv<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└──bigram_df(top100_example).csv<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└──top50_bigram.png<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└──top100_bigram.png<br/>


#### Challenges
* Download the German Wikipedia xml: https://dumps.wikimedia.org/dewikinews/20190720/dewikinews-20190720-pages-articles-multistream.xml.bz2
* Extract the text from every (XML page > text entity)          
* Remove markdown and formatting <br/> (Try to preserve the textual description of links (so not the link target but the description)     
* Remove punctuation
* Remove German stopwords
* Replace German Umlauts (ö -> oe, ü -> ue, ä -> ae, Ö -> Oe, Ü -> Ue , Ä -> Ae, ß -> ss)
* Combine bigrams with more than 5 occurrences
* Plot the 10 most frequent words (x-axis words, y-axis frequency)
* Plot the 10 most frequently occurring bigrams (a new count, not the bigrams from the previous step) and plot them
* Plot the 10 most frequent words at the beginning of a sentence

#### Note
* To save time, it is possible to set a random number of pages in the xml for processing.
** random_pages = 100 (in the code)
* It saves the bigram and unigram in csv when processing. One may see the example in the dir </example>
* The bigram network graph of page index 1 - 100 is also attached in the example directory.

After visualizing the data, we can see that there are a lot of date and category information. This is because of the description in the markdown links. In the data cleaning stage, we only removed Javascript, CSS, several HTML tags, markdown syntax and URLs, but not the description. Therefore, there exist many of technical terms.

