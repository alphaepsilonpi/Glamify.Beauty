# Glamify.Beauty

The following steps were deployed in the recommendation system code which we’ve written for glamify.beauty. The story clearly explains the pipeline in detail, how each section of the code functions and what value it adds to the pipeline :

1.	We start our analysis by reading the raw data which we have scraped/extracted through multiple requests from Amazon.com
2.	Then we proceed with the basic data cleansing by selecting the appropriate features for our model and imputing the NAs with blanks, etc.
3.	Next, we do the much required feature transformation step wherein we convert each column into a TF-IDF vector, which makes mathematical sense to the model which interprets each of these features in our corpus as a numerical vector with a certain magnitude and direction in the space we have defined. For this we use “TfidfVectorizer” module, which basically spreads out each product in the training data in a n-dimensional space. Now all we need to do is to check which other products are closest in terms of proximity to a certain product we select, in order to recommend the appropriate relevant products to the user
4.	Once the vectors are created, we calculate the pairwise cosine similarity between them and see which one’s are closely spaced in the n-dimensional space mentioned above
5.	We’ve defined a helper function which takes inputs of a product name and number of recommendations for that product. It gives an output of top ‘N’ recommended products for the given product. This function basically computes the pairwise cosine similarities between the given product and all other products and chooses the N closest cosine similarity values
6.	Finally, we output the names of the top N most similar products based on the indices returned from the helper function.
7.	Included in the code pipeline is also a collaborative based recommendation stack, which takes in user as an input and provides recommendation based on consumption of similar users in terms of socio-economic, demographic or even consumption patterns. This will greatly broaden the horizons of our recommendations and will help target new users with appropriate products and better user experience. 
