# Lyrics-Analysis
Implementation of Song Lyrics analysis. 
This was originally created in December 2021 by Ameya Naik MIMS '23 as a final project for INFO 202: Information Organization and Retrieval.

# Introduction 
Petrusich's piece [“Genre is Disappearing, What Comes Next?”](https://www.newyorker.com/magazine/2021/03/15/genre-is-disappearing-what-comes-next) on musical genres made me wonder: how do artists use the same words differently? When classroom(![Info202](https://www.ischool.berkeley.edu/courses/info/202)UC Berkeley very interesting course do check it out!) discussion of the topic of document level embedding and document-vectors made me wonder, “how can document-level embedding help distinguish differences between artists?”.For my final project, I combined these concepts in an implementation project. Specifically, I investigated how effectively document-level embedding tells us which artists' song lyrics are similar, and whether this approach aligns or contradicts to methods of genre categorization.

# Project Concepts
These were the concepts covered in this project(I enjoyed learning further)
## 1. Genre Classification: 
The concepst of genre is very vague and rely heavily on the feeling. I feel labelling an artist to a genre is restricting and dis-respectful to the art. The genre classification and song categorisation as binary is uncreative. The "Protoype Theory"[Read more here](https://en.wikipedia.org/wiki/Prototype_theory) , is really an interesting way to understanding the songs and the concept of genre. Since lot of time songs could lie in fuzziness for different genre. Like the "Bohemian Rapsody" by queens could be more towards rock in comparison to Careless whisper(it's often labelled as yatch rock), or is very less rock in comparison to "Thunderstruck" by AC/DC. Hence genre classification is more in relative terms rather than absolute hence the concepts of distance between artist and their lyrics could provide how close ther are to each other.
## 2. Web Scrapping:
I learnt the concepts of web crawling how it gather all the available information  while scraping is retriving only of the relevant data. Inorder to gather lyrics data I used Genius API, and request to get details of top 100 song of artist provided and then used the list to search and then retrieve the lyrics. The whole process indeed was taxing and time consuming(sepcially Timeout Error after 20 minutes etc.), however I could gather the exact data which would be relevant for the project. 

## 3. Bag of Words: 
In this model the song lyrics document is divided in to words with respective frequencies (frequently used words) then to viusalise it we plotted bar graphs and word clouds for each of the artist.
## 4. Word Embedding & Document Embedding (it's implementation) :
The concept of word embedding and document embedding is based on conversion to vectors form.
## 5. Model Visualisation:

# Implmentation
# Instructions to Run the project
# Analysis
# Conclusion
