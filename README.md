# AN588-Homework1-jzeng21
Here are some of the challenges I had to take into account when writing the code.

1. Handling Punctuation in Strings
When splitting the sentence in Challenge 1, punctuation like commas and periods might stay attached to words (e.g., "Stately," instead of "Stately").
Why it's tricky: It affects word extraction and indexing.
Fix: Use gsub("[[:punct:]]", "", string) before splitting.

2. Off-by-One Errors in Indexing
R uses 1-based indexing, not 0-based like some other languages (e.g., Python).
Why it's tricky: You might select the wrong row/column by accident if you're used to 0-based indexing.

3. Misinterpreting Multidimensional Array Access
In Challenge 3, accessing a 4D array like a[2, 3, 2, ] returns a 1D vector—not always intuitive.
Why it's tricky: The result shape can be unexpected; you may not realize you're dropping dimensions unless you specify drop = FALSE.

4. List vs Vector Confusion in Taxonomy
When building the taxonomy list in Challenge 4, mixing up list() vs c() can break the structure.
Why it's tricky: list() creates nested structures, while c() flattens. Using the wrong one gives incorrect nesting.

5. Data Type Coercion Errors
In Challenge 5, coercing to logical or factor may silently change your data if not done carefully.
Why it's tricky: For example, coercing numeric 1 to logical returns TRUE, but coercing non-0s without checking intent can lead to misinterpretation.
