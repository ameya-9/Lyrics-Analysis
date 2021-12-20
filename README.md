![clay-banks-fEVaiLwWvlU-unsplash](https://user-images.githubusercontent.com/19268537/146717200-1aabc298-9fcb-4fcf-be07-3be4f1588884.jpg)

# Lyrics-Analysis
Implementation of Song Lyrics analysis. 
This was originally created in December 2021 by Ameya Naik MIMS '23 as a final project for INFO 202: Information Organization and Retrieval.

# Introduction 
Petrusich's piece [“Genre is Disappearing, What Comes Next?”](https://www.newyorker.com/magazine/2021/03/15/genre-is-disappearing-what-comes-next) on musical genres made me wonder: how do artists use the same words differently? When classroom(![Info202](https://www.ischool.berkeley.edu/courses/info/202)UC Berkeley very interesting course do check it out!) discussion of the topic of document level embedding and document-vectors made me wonder, “how can document-level embedding help distinguish differences between artists?”.For my final project, I combined these concepts in an implementation project. Specifically, I investigated how effectively document-level embedding tells us which artists' song lyrics are similar, and whether this approach aligns or contradicts to methods of genre categorization.

![Screen_Recording_2021-12-17_at_12_38_32_PM_AdobeCreativeCloudExpress (1)](https://user-images.githubusercontent.com/19268537/146633657-646b2362-34c6-499f-ab9b-fd7594e871ed.gif)


# Project Concepts
These were the concepts covered in this project(I enjoyed learning further)
## 1. Genre Classification: 
The concepst of genre is very vague and rely heavily on the feeling. I feel labelling an artist to a genre is restricting and dis-respectful to the art. The genre classification and song categorisation as binary is uncreative. The "Protoype Theory"[Read more here](https://en.wikipedia.org/wiki/Prototype_theory) , is really an interesting way to understanding the songs and the concept of genre. Since lot of time songs could lie in fuzziness for different genre. Like the "Bohemian Rapsody" by queens could be more towards rock in comparison to Careless whisper(it's often labelled as yatch rock), or is very less rock in comparison to "Thunderstruck" by AC/DC. Hence genre classification is more in relative terms rather than absolute hence the concepts of distance between artist and their lyrics could provide how close ther are to each other.
## 2. Web Scrapping:
I learnt the concepts of web crawling how it gather all the available information  while scraping is retriving only of the relevant data. Inorder to gather lyrics data I used Genius API, and request to get details of top 100 song of artist provided and then used the list to search and then retrieve the lyrics. The whole process indeed was taxing and time consuming(sepcially Timeout Error after 20 minutes etc.), however I could gather the exact data which would be relevant for the project. 

## 3. Bag of Words: 
In this model the song lyrics document is divided in to words with respective frequencies (frequently used words) then to viusalise it we plotted bar graphs and word clouds for each of the artist.

## 4. Word Embedding & Document Embedding (it's implementation) :
The concept of word embedding and document embedding is based on conversion to vectors form, aslo taking into account the contextual orientation.
_"You Are the Average of the Company You Keep"_
The concept of doc2vec is context window, which slide through the paragraphs and captures the meaning of the words while continuing shift.

## 5. Model Visualisation:
It really difficult to visualised any vector with some many dimension so we need to visualise it in human underderstandable visualisations. There are many ways to do that like PCA, t-sne, UMap etc. However to ensure it's interactive, I searched about tensorboard and converted my model into an understandable .tsv file. 

# Implementation:
![Intro-video_AdobeCreativeCloudExpress](https://user-images.githubusercontent.com/19268537/146711747-1a160848-9df5-4c94-942f-dd1355fa4bd6.gif)

1.Create a list of documents, where each document contains all the lyrics of an artist.
2.Clean the document and tokenize, removing stop words (eg. at, to, for, etc.)
3.Using Doc2vec trained over the list of the documents, convert every artist to a vector.
4.Visualize these vectors, to understand the closeness of different artists.
5.Visualize the artist’s word usage and frequency using a word cloud.
6.Derive insights from the visualization - (using PCA on ![tensorboard projector](https://projector.tensorflow.org/) )

# Instructions to Run the project

1. Clone the git project. 
2. For Data: Please unzip the archive file, inside the data folder it would have all the data. 
3. src : Run the file "Final_Lyrics_Analysis.ipynb" file, this file has all the code to create a model from the scratch with the data. 
4. Incase of any error while running it, please do check the required libraries are installed.
5. Also do check the location of the data folder it should point to that part.
6. As soon as the all error resolved, the complete notebook should run and a new model should be generated. 
7. Upload the "lyrics_tensor.tsv" and "lyrics_metadata.tsv" files to https://projector.tensorflow.org/.
8. Select the PCA or in case if t-sne (please provide a stop point)

# Analysis:
Since we took top 100 songs of the 25 artists. The analysis is based on semantic similarities of the top 100 song lyrics of artists, which suprisingly isn't same as the genre classification. That is "The artist labelled with similar genre songs weren't necessarily closer in terms of semantic similarities". 
Example as per the "our_artistdata.csv" , which was derived from an existing csv file(refer the ![datasheet](https://github.com/ameya-9/Lyrics-Analysis/blob/main/data/DataSheet%20for%20Lyrics%20DataSets%20_.pdf)) . 
  Cranberries  and Coldplay both have  genre labels  "rock; pop; alternative rock; britpop; pop rock;" while Logic  has genre labels as "rap; hip hop; underground; dmv" . However as per our model in terms of semantics similarities Coldplay is closer to Logic, than Coldplay to Cranberries :
  ![image](https://user-images.githubusercontent.com/19268537/146716227-687acb8f-9432-4f2f-aec9-38e415cce5f3.png)

  
  Metallica and Judas Priest has genre labels "rock; 80s; heavy metal; 90s; thrash metal; metal;metal;hard rock;" which suggest they shoudl be close to each other in-term of semantic similarities, which is supported by our PCA graphs  for nearest neighbour for Metallica is Judas Priest.
  ![image](https://user-images.githubusercontent.com/19268537/146716760-66dd1770-0e57-4467-b80e-e811d6037bc7.png)


# Conclusion
![natalie-cardona-W8BRzoUTHNA-unsplash](https://user-images.githubusercontent.com/19268537/146717248-daf4ad78-dccc-4c4a-a768-2aa611ad0e4c.jpg)


Although semantic similarities could be used to broadly define which artist are similar to each other, however the semantics are just one aspect of an artist style or genre labels are lyrics. The artists song style , rythms, music, demeanor all together defines the genre and labels attached to them. Hence semantic distance or similartities could be a good primary filter to understand closeness, however must be complimented with other analysis to understand the artist complete style.       Genre classification is a complicated process and isn't binary rather are labels which songs of artist or artist could carry with them and are dynamic in nature, depending upon how the artist is being perceieved by listeners.
