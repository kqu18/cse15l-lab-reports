### Lab 3: Researching Commands
---

## grep

(Courtesy of ChatGPT)

`grep` is a command-line utility in Unix-like systems that is used for searching text files for patterns. 

The basic syntax of the grep command is:

`grep *pattern* *filename*`

where `pattern` is the regular expression pattern to search for, and `filename` is the name of the file to search.

---
## Example section: 
we will now use /written2 (class provided file path, [Link](https://github.com/ucsd-cse15l-w23/docsearch))


## **grep -r**

`-r`, which stands for 'recursion', is a useful command which allows us to search through all files recursively, looking for elements in files. 
For example, we can use `grep -r "Lucayans"` to find the file where the word *Lucayans* have appeared. 

```
# grep -r demo

>> grep -r "Lucayans"

./travel_guides/berlitz2/Bahamas-History.txt:Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.

./travel_guides/berlitz2/Bahamas-History.txt:The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.


```

Note that if we only want the file information but not te specific occurences, we can simply use `-rl` instead: 

```
# grep -rl demo

>> grep -rl "Lucayans"

./travel_guides/berlitz2/Bahamas-History.txt

```
---

## **grep -i**

sometimes, we don't want to specify upper or lower case. In the previous example, if we search for "lucayans":

```
#no output demo

>> grep -rl "lucayans"

```

we will see that there are no matching items. this is because grep searches for exact matches, across all texts. 

therefore we can use `grep -ril`: (i stands for ignore case)

```
#ignore case example

>> grep -ril "lucayans"

./travel_guides/berlitz2/Bahamas-History.txt

```
and we have found the desired occurence. 

---

## **grep -w**

sometimes, we want exact matches and sometimes we don't. We can use `grep -w` to help us find words with exact matches (W stands for word).

for eaxample, if we want to look for all occurences for keyword "Lucayan", we can simply do:


```
>> grep -ril "lucayan"

./travel_guides/berlitz2/Bahamas-WhereToGo.txt
./travel_guides/berlitz2/Bahamas-History.txt

```

However, sometimes we only want exact matches, not just words that include "lucayan". For example, we only want "lucayan", but not "lucayans". 
What should we do? We can use -w to help us:
```
>> grep -rilw "lucayans"

./travel_guides/berlitz2/Bahamas-History.txt
```
Now we have achieve exact match searching.


---

## **grep -A/-B/-C**

sometimes, we want to check out what is going on near the occurence of our keyword. 

We have `grep -A *num*`, which allows us to access `num` lines before the occurence:

```
>>grep -A 1 -i "Lucayans" ./travel_guides/berlitz2/Bahamas-History.txt

Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.

The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.

English sea captains also came to know the beautiful but deserted Bahamian islands during the 17th century. England’s first formal move was on 30 October 1629, when Charles I granted the Bahamas and a chunk of the American south to his Attorney General, Sir Robert Health. But nothing came of that, nor of a rival French move in 1633 when Cardinal Richelieu, the 17th-century French statesman, tried claiming the islands for France.
```



