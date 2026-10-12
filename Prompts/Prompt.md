Make sure to process the text datasets like the next
Using the rust library <https://docs.rs/sentencize/latest/sentencize/> split every paragraph into a full sentence, then process the like Q/A. 

Every sentence is the prompt of the next sentence.
If you have odd 

sentence
sentence 1 sentence 2 sentence 3
The Q/A will be

sentence 1 sentence 2

sentence 2 sentence 3

If you have pair sentence
sentence 1 sentence 2 sentence 3 sentence 4

The Q/A will be

sentence 1 sentence 2

sentence 2 sentence 3

sentence 3 sentence 4
