This was my solution to the sortable.com 2012 coding challenge.

To run, do:
./run

It expects products.txt and listings.txt, and writes the results to results.txt.


# DESIGN CONSIDERATIONS

The first thing you need to know about me is that my absolute favourite
data structure in the whole word is the stack.
However, the only reason I could justify using them for this challenge
is that Java allows most of its data structures to be iterated over.
So even though I used several stacks, they're really just lists,
and I refer to them as such in the comments.

The focus of the exercise seems to be efficiency and precision.
In order to avoid having to compare every listing with every product,
I decided to go with a kind of divide-and-conquer solution where the
manufacturer is checked first, since that seems to be the most basic field.
I noticed that some of the listings have bogus manufacturer fields,
but checking the listing title for the manufacturer tended to bring up
irrelevant products such as batteries and bags and lens kits.
This approach allows each listing to be considered exactly once.

In order to quickly recall products of the same manufacturer,
I used a hash table (Java's HashMap) to map a manufacturer string the
list of products that the manufacturer makes.

