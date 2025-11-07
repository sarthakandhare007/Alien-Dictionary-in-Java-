# Alien-Dictionary-in-Java-
🧩 Problem Statement

You’re given a list of words sorted lexicographically according to an unknown alien language.
Return a valid order of characters in that language.

If no valid order exists, return "".


---

📘 Example

Input:
["wrt","wrf","er","ett","rftt"]

Output:
"wertf"

✅ Explanation:
From the order of words, we deduce:

w → e

e → r

r → t

t → f


Hence: wertf


---

❗ Invalid Case Example

["abc", "ab"]

Output: "" (invalid because a longer word comes before its prefix)


---

🧠 Approach

We treat this as a graph + topological sort problem:

1. Build graph

Compare adjacent words

Find first differing char → defines order c1 → c2



2. Compute in-degrees

Count incoming edges for each char



3. Topological sort (Kahn’s Algorithm)

Use a queue for characters with in-degree 0



4. If cycle detected → return ""


