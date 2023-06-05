# Web-Scraping-and-Linguistic-Analysis-of-Text-Data-from-Multiple-URLs
The given code performs web scraping on a set of URLs, extracts text content from the web pages, and analyzes the text using various linguistic and sentiment analysis techniques. Here is a brief description of the code:

The code imports necessary libraries, such as requests for making HTTP requests, BeautifulSoup for parsing HTML, pandas for data manipulation, re for regular expressions, and nltk for natural language processing tasks.

It downloads required NLTK resources by executing the nltk.download() function.

The code reads an Excel file named "BlackCoffee.xlsx" using pandas and extracts the 'URL' and 'AVG NUMBER OF WORDS PER SENTENCE' columns into a dataframe (df).

It reads additional columns 'Negwords', 'Poswords', and 'Stopwords' from the same Excel file into separate dataframes (posword, negwords, stopwords).

The code defines several functions:

eliminate(sw, k): Eliminates words from list k if they exist in the stopword list sw.
pp(text): Counts the occurrences of personal pronouns in the given text.
count(t): Calculates the average number of words per sentence in the given text.
neg(text, nw): Counts the number of negative words from the text that match the negative word list nw.
pos(text, pw): Counts the number of positive words from the text that match the positive word list pw.
stemming(k): Performs word lemmatization on a list of words k.
sub(t): Removes punctuation marks from a list of words t.
avg_word_len(w): Calculates the average word length from a list of words w.
syllable(words): Counts the number of complex words and syllables in a list of words words.
polarity_subjectivity(pos, neg, sw): Calculates the polarity and subjectivity scores based on positive count pos, negative count neg, and the number of stopwords sw.
A loop iterates through the URLs in the 'URL' column of df and performs the following steps:

Requests the web page content using requests.get().
Parses the HTML content using BeautifulSoup.
Extracts the text content from all paragraphs (<p>) in the HTML.
Tokenizes the text into words using nltk.word_tokenize().
Calculates various linguistic features such as average sentence length, personal pronoun count, word length, complex word count, etc.
Performs sentiment analysis by counting positive and negative words.
Calculates polarity and subjectivity scores.
Creates a dictionary d with all the extracted features.
Appends d to a list dataframe.
After the loop, the list dataframe is used to create a new dataframe df.

The resulting dataframe df is saved as a CSV file named 'output.csv' using the to_csv() function.

Finally, the code prints the updated dataframe df and a message "updated" to indicate successful execution.
