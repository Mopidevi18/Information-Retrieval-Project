--------------------------------------------------------------------------------IR PROJECT----------------------------------------------------------------------------------------------------

Details of the project:
---------------------
   --> Domain : Sports
   --> Document Collection: 100000(Json format documents containing sports articles)
   --> Algorithms used: TF-IDF weighting,Cosine Similarity

Tasks Implemented:
-------------------
Task-1:
  --> Searching and retrieving the top 10 ranked documents : When a user enters an input as phrasal query he can retrieve the top 10 ranked Documents based on "TF-IDF" score.
 Task-2:
  --> User Recommendations on Query Expansion based on previous searches: When a user enters an input as phrasal query he can get recommendations based on previous queries using "Cosine similarity" score.

About my Code:
-----------------
--> I implemented everything from scratch and only used basic libraries like re,glob.
--> I stored the inverted index result into json file using Json package called dump.  


For Task-1 Implementation:
       --> First i stored all file paths in a list variable by using glob module so that we can access each file.
     
       --> After accessing each file i had opened and read that file now the file has a string of characters here I used RegEx for pattern matching for accessing each word.
    
       --> I created Inverted index by removing stop words and storing each unique word as a key, posting list as value.
     
       --> Now for calculating TF.IDF score we need term frequency and document frequency.
      
       --> For calculating term frequency I am checking the intersection of words in phrasal query and document terms, for the intersection terms only i am calculating the term frequency in that particular document.

       --> For calculating the document frequency I used Inverted Index as i stored posting list as dictionary value, simply size of Posting list corresponding to a term gives document frequency of that term in collectioin.

       --> I multiplied the Tf-idf scores obtained from between each common term between query and document. 
       
       --> Then based on resultant TF.IDF score for each document I am retrieving the Top 10 Ranked documents.

For Task-2 Implementation:
      --> I stored all previous queries vectors in one list.
       
      --> After entering the User phrasal query input, i am using cosine similarity between phrasal query and previous queries.

      --> Based on that cosine similarity Score I am displaying the recommendations for that Query. 


------------------
Time Complexity --> O(n) where n is total no of words in all documents.

Space Complexity --> O(n*m) where n is number of unique words and m is total no of documents.    



      