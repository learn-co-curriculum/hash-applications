## Hash Table Applications

### Objectives 

- Learn various applications of when it is good to use a hash.

### Review

In the last section we learned how a hash table involves inputting a key into a hash function to determine precisely where to retrieve and place values related to that key.  The benefit of this is that given a key, we can quickly determine in O(1) time, whether that value is in the hash and what the value is.  This is similar to how we can determine if a value is in a specific index in O(1) time for an array.

### Benefits

The benefits of this is that hashes become quite good at determining inclusion of a key, and at finding specific data related to a key.  While hashes maintain a key value data structure, because hashes work by having a hash function return a location that does not map to any order of the keys or any other information - but approaches an almost random return value - hashes are not good at ordering or sorting information.  So problems related to ordering or sorting information, would much better be handled by a data structure like a sorted array.   

So let's think for a minute about where we should use an array, and where we should prefer a hash.

| Use an array                             |Use a hash |
| -------------                            |:-------------:|
| Ordering elements based on criteria      | Element in collection?  |
| Finding the first or last element (max or min)| Retrieving associated information|
|finding rank of an element (eg. 'c' is 3rd highest) |


So **repeated lookup of information** is better performed by a hash.

### Repeated Lookup Problems

Now, we can rephrase our question of where to use a hash to ask what are some examples of where we are solving repeated lookup.  As we'll see, the four principle areas are through checking for uniqueness, caching information, with gatekeeping, and with search.  

A. Uniqueness/Deduplication

*  Unique Visitors to a website

	Say we want to see all of the unique visitors to a website.  We might do so by storing a list of IP addresses to represent the computers that have visited our website.  Because we want only one key associated with each IP address, this is a problem of repeated lookup.  Every time we receive a request to our website, we look to see if the computer making the request has already been stored in our hash.
	
* Web Crawlers

	Google's page rank algorithm ranks the importance of a website by looking at which other websites linking to it.  Now, Google's algorithm wants to control for uniqueness.  That is, it should allocate more importance to a website if the links come from different websites as opposed to all from the same website.  So Google can use a hash to quickly lookup to see if it has already recorded the link between two websites.      	
	
	![](http://www.searchengineoptimizations.co/wp-content/uploads/2011/01/inbound-linking.gif)
	
B. Caching/Memory

Caching is similar to the problem of de-duplication.  Caching is a technique whereby we prevent running a calculatin again by instead storing the result of the solution we previously stored.  
	
* Caching Webpages  

	Say there are types of requests repeatedly made, for example for the same CSS stylesheet.  A browser, or a server see if it has already requested the information, and if so, retrieve the information in a local hash.	

* Caching Previous Calculations - Chess Moves

	Consider a computer program that calculates chess moves.  For any given point of the game, there are various moves and counter moves that can be made.  For the computer to avoid recalculating the quality of a given move, it may store moves already considered in a hash.  Then it can quickly see if it had already considered a move, and avoid recalculating its quality. 
 
C. Gatekeeping/Restricting

* Routers and Internet 

	Sometimes, a web application will block network traffic from ip addresses.  This is another problem of repeated lookup that can be solved from a hash. 

* Forbidden Passwords
	
	When creating a new password, there are a set of passwords which are not allowed.  For example, maybe we do not want to permit a user to signup with generic passwords like 'password' or 'letmein'.  We can store the list of forbidden passwords in a hash and if the password is on the list we throw an error.     
	
* Spell Checkers 

	Spell checkers seems very similar to our forbidden passwords problem.  Here, we store an entire language's collection of words, and each time a user types in a word we see that it is in our hash.  If it is not in our hash we indicate to the user that the word is mis-spelled.
	
D. Search
 
* Search 

	Another way of saying repeated lookup is really that we are performing a search.  So in previous lessons we have learned various a sorting algorithm like merge sort.  Then, sometimes we checked for inclusion by employing binary search. 

	However, hashes give us a faster mechanism to determine if a value is in our collection.  Remember that sorting an array takes O(n log n) and that employing binary search takes O(log n).  With a hash, we can place every element into a hash in O(n) time and determine if an element is in a hash in O(1) time.  

### Summary

We now see that we really only use hashes for one thing: repeated lookup.  Unlike arrays, hashes are not good at determining a min or max, or other operations that depend on the relative order of a list of elements.  However, this problem of repeated lookup occurs in many operations.  It occurs in determining uniqueness, in caching and remembering information, in checking if something is restricted, and in searching for inclusion.  In the exercises that follow, we will see examples of how and when to move from using an array to using a hash.


	

	

		
	
