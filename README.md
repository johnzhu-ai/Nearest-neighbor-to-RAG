0. Imperative: binge watch Tom and Jerry, but with different plots
We are binge watching Tom and Jerry, and want to continue with similar-but-not-the-exactly-the-same episodes.

For example, in one episode, Tom is dreaming about catching Jerry in the sleep, whereas in another episode, Tom is really chasing down Jerry (and not in the sleep-walking sense).

In this program, we will demonstrate how to surface the 2nd/3rd/4th... closest story (nearest neighbor) to a "sleeping-cat" story-line.

Think of real-life implications:

In the case of renter's insurance, how can we tell contract 1 lightly touches on plumbing, whereas contract 2 includes substantial clauses?
More generally, can we feed months/years of software/building/legal contacts, to discover (subtle) changes, i.e. COVID-19 could break up the contracts?
In other words, can we feed colossal amount of documents without domain knowledge/supervised learning, so as to surface and drive the adoption for Document/Label Sleuth/other AI/ML/NLP tools?
0.1. Solution: find close-but-not-the-exactly-same clues, in scale
One potential way is to be able to

Measure the distance of vector/embeddings, i.e., think of Cosine Similiarities in extremely high yet sparse representations
Find the 2nd/3rd/4th.. closest distance, but not the closest-distanced nor the precisely-matched one
And do so in-scale
0.2. Approximate Nearest Neighbor (ANN) with Anisotropic Vector Quantization, Shallow Tree + Asymmetric Hashing
Google's Approximate Nearest Neighbor (ANN) Index is a high scale, low latency solution, to find similar vectors (or more specifically "embeddings") for a large corpus.

The highlight is "Anisotropic Vector Quantization" Approximate Nearest Neighbor (ANN) technology.

0.3. Vector/embedding with Setence Transfomer/sentence-t5-base
To build the vector/embedding, we are using Setence Transfomer/sentence-t5-base from Hugging Face https://huggingface.co/blog/sentence-transformers-in-the-hub

0.4. Distance measure of 'The cat likes to sleep in the sun' to 9 other sentences
Let's say that, we have summarized a Tom and Jerry episode into the one-liner of

'The cat likes to sleep in the sun'.

Meanwhile, we have summarized 9 other random TV-shows into 9 one-liners as follows:

I spent the day at the medical facility.
That a cultured medical genius found her inspiring was beyond flattering.
She drew nearer, eyes sweeping over the medical equipment in the room.
I did not ask the American Medical Association their opinion of this arrangement.
I think the cat wants dessert!
Im in no mood to watch a cat fight tonight.
The cat would like to eat the mouse.
A large grey cat was asleep on a rocking chair.
The pilot was able to land the airplane
0.5. Result
You will see in the following that for the sentence of 'The cat likes to sleep in the sun'.

The closest sentences would be:

A large grey cat was asleep on a rocking chair.
I think the cat wants dessert!
The cat would like to eat the mouse.
Im in no mood to watch a cat fight tonight.
The pilot was able to land the airplane
Pretty good, right?

0.6. Continue watching episodes 2 and 3 - throw out 1, 4 and 5
Based on above, we will toss away show 1 because it is roughly the same, and disregard show 4 and 5 since they are further away from our core interest/topics.

This leaves with summary 2 and 3:

I think the cat wants dessert!
The cat would like to eat the mouse.
Now we can continue binge watching with 2 and 3!

0.7 Specific steps
Prep environment/var
Create vector/embedding with sentence-transformers
Create ANN Index and Brute Force Index
Create an IndexEndpoint with VPC Network
Deploy ANN Index
Perform online query
0.8 To-do
Test cases, algorithms (sorting), document/contracts
