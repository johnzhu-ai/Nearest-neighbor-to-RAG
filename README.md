# Surface close-but-not-the-exactly-same clues, in scale

### with Approximate Nearest Neighbor in Anisotropic Vector Quantization, Shallow Tree + Asymmetric Hashing, and Sentence Transformer

## 1. Intro: binge watch Tom and Jerry, but with different plots

We are binge watching Tom and Jerry, and want to continue with similar-but-not-the-exactly-the-same episodes.

For example, in one episode, Tom is dreaming about catching Jerry in the sleep, whereas in another episode, Tom is really chasing down Jerry (and not in the sleep-walking sense).

In this program, we will demonstrate how to surface the 2nd/3rd/4th... closest story (nearest neighbor) to a "sleeping-cat" story-line.

## 2. Real-life implications

In the case of renter's agreements, how can we tell <b>contract 1 lightly touches on plumbing whereas contract 2 includes substantial clauses</b>?

More generally, can we feed <b>months/years of software/building/legal contacts, to discover (subtle) changes, i.e. COVID-19 could break up the contracts</b>?

In other words, can we feed <b>colossal amount of documents, audio and video, without domain knowledge/supervised learning, with Document Sleuth for follow-on AI/ML/NLP tools</b>?

## 3. Solution: find close-but-not-the-exactly-same clues, in scale

One potential way is to be able to
1. Measure the distance of vector/embeddings, i.e., think of Cosine Similiarities in extremely high yet sparse representations
2. Find the <b>2nd/3rd/4th.. closest distance, but not the closest-distanced nor the precisely-matched one</b>
3. And <b>do so in-scale</b>

## 4. Approximate Nearest Neighbor with Anisotropic Vector Quantization, Shallow Tree + Asymmetric Hashing
Google's Approximate Nearest Neighbor (ANN) Index is a high scale, low latency solution, to find similar vectors (or more specifically "embeddings") for a large corpus.

The highlight is "Anisotropic Vector Quantization" Approximate Nearest Neighbor (ANN) technology.

## 5. Vector/embedding with Setence Transfomer/sentence-t5-base
To build the vector/embedding, we are using Setence Transfomer/sentence-t5-base from Hugging Face https://huggingface.co/blog/sentence-transformers-in-the-hub

## 6. Distance measure of one Document Summary to 9 others
Let's say that, we have summarized a Tom and Jerry episode into the one-liner of

'The cat likes to sleep in the sun'.

Meanwhile, we have summarized 9 other random TV-shows into 9 one-liners as follows:

1. I spent the day at the medical facility.
2. That a cultured medical genius found her inspiring was beyond flattering.
3. She drew nearer, eyes sweeping over the medical equipment in the room.
4. I did not ask the American Medical Association their opinion of this arrangement.
5. I think the cat wants dessert!
6. Im in no mood to watch a cat fight tonight.
7. The cat would like to eat the mouse.
8. A large grey cat was asleep on a rocking chair.
9. The pilot was able to land the airplane

## 7. Result
You will see in the following that for the sentence of 'The cat likes to sleep in the sun'.

The closest sentences would be:

1. A large grey cat was asleep on a rocking chair.
2. I think the cat wants dessert!
3. The cat would like to eat the mouse.
4. Im in no mood to watch a cat fight tonight.
5. The pilot was able to land the airplane

Pretty good, right?

## 8. Continue watching episodes 2 and 3 - throw out 1, 4 and 5
Based on above, we will toss away show 1 because it is roughly the same, and disregard show 4 and 5 since they are further away from our core interest/topics.

This leaves with summary 2 and 3:

2. I think the cat wants dessert!
3. The cat would like to eat the mouse.

Now we can continue binge watching with 2 and 3!

## 9. Specific steps
1. Prep environment/var
2. Create vector/embedding with sentence-transformers
3. Create ANN Index and Brute Force Index
4. Create an IndexEndpoint with VPC Network
5. Deploy ANN Index
6. Perform online query

## 10. To-do
Test cases, algorithms (sorting), document/contracts
