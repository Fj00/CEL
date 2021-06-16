# CEL

Common English Lexicon (CEL), a word list with common words, for word games.

## Background

1. What is the CEL?
   - The CEL stands for Common English Lexicon, created by Eric Smith (Fj00) and Kenji Matsumoto. The CEL focuses on the most common words that exist in the international Scrabble dictionary (CSW). As such, the CEL is less than 1/3 the size of CSW, with just over 67,500 words in total and over 35,800 words under 9 letters.

2. How was the CEL compiled?
   - The CEL was compiled by counting the number of times specific words were used in Internet articles, books, and webpages Google searches. Those that made it past pre-specified thresholds had made it into CEL, as well as related words necessary for consistency.  

3. What does it mean for a word to be "common"? Why are there still some weird words in here?
   - We wanted the CEL to be an inclusive, diverse dictionary that reflected people throughout the world with a variety of interests and expertise. As such, we included entries that may span beyond basic vocabulary, and included various plants, animals, foods, scientific terms, etc. that might not be part of even the most educated person's vocabulary. Such terms are supported by millions of Google hits and sufficient usage in books, internet articles, etc. but may not be familiar to the majority of players using the CEL. Knowing all entries in the CEL would require an absurd amount of information about almost every subject.

4. What does ________ mean?
   - Some words may not be initially intuitive. For example, the word 'mac' might not look like a word to many people, and it may confuse people that 'macs' is not a valid string, but will make sense once they understand the intended definition (short for macaroni, i.e. mac and cheese).
   - All words in CEL have common definitions. The overwhelming number of words can be defined through dictionary or google, although in a few cases, using an advanced search in one of our sources may help players looking to define an entry.

5. Why are there so few -S/-IER/-ED/RE- etc. words?
   - Scrabble players may be accustomed to a lexicon with every conceivable conjugation, but we feel that many of these conjugations are unwarranted and do not represent common English. As a result, we have removed conjugations that are both uncommonly used and not unessential to the word's common definition. This may make it more difficult to play a game of Scrabble, but restricting conjugations allows us to better reflect the English language.

6. Why isn't (insert common word) found in CEL?
   - There are a variety of reasons why a common word may not have made it into CEL. The most common reasons are:
     - It didn't make it into the Scrabble dictionary. For example, KEYCHAIN is not valid in CSW.
     - It exists primarily as a proper noun. For example, alaska did not make it into CEL, since its primary form is baked alaska, it's still often capitalized, and it's not all that common of a dessert.
     - It exists in English but primarily from another language. For example, alma (alma mater) did not make it since we deemed it as being primarily Latin.
     - It failed to get the requisite number of hits in books, webpages, or web articles. There are some words that didn't qualify that mystify us, too.

## Community

CEL is currently implemented on the Woogles platform for playing OMGWords (Orthogonal Morphemes Game). https://woogles.io

Woogles is a community whose mission is to:

1. Create a great place to play word games online.
2. Create a tool that lets people of all skill levels from all over the world improve at our favorite board game.
3. Build the best AI our community has ever seen.

Woogles achieved a successful Kickstarter in October last year, and was created by a team led by César Del Solar, one of the top North American Scrabble players. The Woogles team is also made up of several other top players.

## Getting Started

The repository contains `cel.txt`, the master CEL list. The `2-15` folder contains subsets of CEL by word length, from 2-15 letters. The `a-z` folder contains subsets of CEL by starting letter, from A-Z. More subset lists can be generated if desired. In the future, these lists will be updated to stay consistent with `cel.txt`.

## Methodology

The working spreadsheet is public. It currently contains 4 tabs, cel is the current working list, 2s is just 2 letter word selection, 3s is 3 letter word selection, and movies is another list described below. The spreadsheet can be viewed at: https://docs.google.com/spreadsheets/d/1N-LfFbuuVA176f6pI8oTHYtpUGOy7t2i_ovsCTalq4A/edit?usp=sharing

The starter list chosen was 2of12, which contains a list of common words and their inflections, created by finding words that were in at least 2 out of 12 dictionaries that were selected. More information on 2of12 here: http://wordlist.aspell.net/12dicts-readme/#2of12inf

The uncountable nouns (%) in 2of12 were removed almost completely, and it was filtered by a competitive word list. This resulted in a total of 80775 words. There were less than 100 words in 2of12 that were not in the competitive word list. The list was a good start, but due to the methodology and lack of oversight, many words remained that were either obscure or unused. Thus the great purge began.

The list was audited, and initially only the 4-9 letter words and their inflections were considered. I was going to handle the 2-3 letter words at a later point. I started going through the list the first time, but it was apparent that my strataji was evolving over time, even early on. I decided to finish one pass and then make another pass to try to correct the inconsistencies. The second pass, I ended up deciding to clean up the 10-15 letter words as well, since many of them would look odd to keep in the list.

Definitions were checked on https://www.dictionary.com/, https://www.collinsdictionary.com/, and Google dictionary.

When necessary, Google search was helpful for figuring out words. Results with less than 1M hits were typically removed.

After the second pass, it was determined that the process was too subjective and there needed to be more objectivity when deciding on words. I had access to a data set containing the cleaned full text of 8.4M internet articles (34 GB of text). That data set was processed for word frequency and then filtered by the same list.

A 0-10 score for each word was computed using this formula: `(10/log(1 + freq(THE)))*log(1 + freq(word))`

`THE` had the highest frequency of any 2-15 letter word, and is used to normalize the score.

Words above a score of 3 almost always make the cut, whereas words below 2 almost always miss the cut. 

Names and proper nouns can confound the scores, so those words had to be recognized and handled on a case-by-case basis.

For 2 letter words, a cutoff of 7 was able to split the very common words from the rest.
For 3 letter words, a cutoff of 5 was helpful in determining how common they were.

Google Books Ngram Viewer was also helpful for 2-3 letter words. It provided a percent score for each of the words based on their frequency within books. A 0-10 score was computed from it using the following formula: `10*(log(ngram) - min(log(ngram)))/(max(log(ngram)) - min(log(ngram)))`

A cutoff of 4 was used for 2s, and a cutoff of 3.5 was used for 3s.

For the most part, onomatopoeia are left out, especially for 2-3 letter words with consonant clusters. I made that determination mainly due to my PTSD from playing HM in a game with classmates in school and getting mocked for it. There are some instances of onomatopoeia which are common enough to keep, such as various animal sounds used as verbs.

Expletives, slurs and pejorative words are not in CEL. There is a good case that such words could scare off some audiences. I am maintaining a separate list that contains such words.

Comparatives and superlatives are a gray area. Internet articles usually avoid using them, and their scores are low in general, whereas conversational English would be more likely to use them. Similarly, adverbs are likely used less in writing. These might need to be handled on a case-by-case basis.

Loanwords are generally avoided, unless they have a significant degree of commonality. Historical, archaic or outmoded words are also generally avoided.

Words that are common but limited to specific fields are avoided. Some instances are words only related to high-level chemistry, physics or mathematics.

Elements 1-118 in the periodic table are all included for completeness. It would be hard to determine what counts as a common element.

Obscure medicines, medical terms and chemicals are left out. Common medicines such as ASPIRIN or IBUPROFEN are left in.

Letters from the Greek alphabet have been included for completeness, regardless of commonality. Letters from the Hebrew alphabet have been omitted. However, spellings of letters from the English alphabet have also been omitted since they aren't typically spelled out in writing. Greek letters typically are treated as uncountable nouns, however a few have auxiliary definitions that require inflections, ALPHA(S), BETA(S), DELTA(S), OMEGA(S).

Uncountable nouns have the plural omitted in almost all cases, mainly thanks to the 2of12 list having labeled them. However, there were still many more that needed to be classified. Often there is a little bit of gray area, so some plurals are included. It mostly depended on the ratio between the frequency of the singular and plural forms.

Inflections are usually all included, however oftentimes a group of inflections will have a subset that are very common, whereas one or more words are not. For example, a noun and its plural along with an adjectival form might be included, where as the present participle of the verb is excluded. Another example is where only the adjectival form and the gerund form are common.

Even though all the 9-15 letter words were examined, they are a lot less important for some games where the majority of words employed are less than 9 letters. They were left in mainly for extending 7-8 letter words using inflections, and also as an attempt to slow Nigel Richards down when he learns the dictionary.

Variants of words are only included if they are common enough. Verbs ending in L often had both single and double L inflections, and there was a lot of unmanageable inconsistency with frequency. This might be a reason to look into it making it more consistent later.

Agent nouns (-ER, -OR, -IST) are avoided, unless they are significantly common, or a profession, machine or tool.

The only major currencies included are DOLLAR(S), EURO(S), [Swiss] FRANC(S), POUND(S), YEN. PESO(S), RENMINBI, RUBLE(S), RUPEE(S) are also included due to commonality.

This is just a disclaimer that it is impossible to be objective in every instance, and it is fine that people disagree with some of the choices that were made. Hopefully the goal is achieved that people who don't play word games competitively will enjoy playing more with a word list that contains only words they know.

## Stats

Again, the initial list contained 80775 words. The number of words removed was 24688, making 56087. There were 150 additions that weren't 2 or 3 letters. The total number of 2 letter words is 65 (out of 127 competitive), and the total number of 3 letter words is 640 (out of 1347 competitive). Combining the purged list with the additions and 2-3 letter words makes 56311 words, and here is the list broken down by word length:

| Length | CEL Count | Competitive Count | Percent CEL/Competitive |
| --- | --- | --- | --- |
| 2 | 65 | 127 | 51.18% |
| 3 | 640 | 1347 | 47.51% |
| 4 | 2246 | 5638 | 39.84% |
| 5 | 4234 | 12973 | 32.64% |
| 6 | 6593 | 23035 | 28.62% |
| 7 | 8657 | 34345 | 25.21% |
| 8 | 8961 | 42153 | 21.26% |
| 9 | 8065 | 42935 | 18.78% |
| 10 | 6543 | 37749 | 17.33% |
| 11 | 4541 | 29591 | 15.35% |
| 12 | 2932 | 21506 | 13.63% |
| 13 | 1658 | 14703 | 11.28% |
| 14 | 794 | 9652 | 8.23% |
| 15 | 382 | 6103 | 6.26% |
| Total | 56311 | 281857 | 19.98% |

Unsurprisingly, the proportion of words in CEL is strictly decreasing as the number of letters increase. The number of CEL words with 2-8 letters is 31396 for reference. Here is the same table for words starting with letters A-Z:

| Letter | CEL Count | Competitive Count | Percent CEL/Competitive |
| --- | --- | --- | --- |
| A | 3278 | 16315 | 20.09% |
| B | 3205 | 15380 | 20.84% |
| C | 5282 | 25223 | 20.94% |
| D | 3467 | 16719 | 20.74% |
| E | 2336 | 11397 | 20.5% |
| F | 2404 | 10676 | 22.52% |
| G | 1712 | 9410 | 18.19% |
| H | 1997 | 10619 | 18.81% |
| I | 2320 | 9684 | 23.96% |
| J | 448 | 2315 | 19.35% |
| K | 360 | 3411 | 10.55% |
| L | 1622 | 8105 | 20.01% |
| M | 2897 | 16034 | 18.07% |
| N | 1121 | 6782 | 16.53% |
| O | 1533 | 9017 | 17.0% |
| P | 4504 | 24560 | 18.34% |
| Q | 279 | 1413 | 19.75% |
| R | 3825 | 15168 | 25.22% |
| S | 6657 | 32194 | 20.68% |
| T | 2954 | 14656 | 20.16% |
| U | 1554 | 9695 | 16.03% |
| V | 817 | 4609 | 17.73% |
| W | 1466 | 5950 | 24.64% |
| X | 13 | 309 | 4.21% |
| Y | 161 | 1040 | 15.48% |
| Z | 99 | 1176 | 8.42% |
| Total | 56311 | 281857 | 19.98% |

 After making the first revision, the total number of words is 60133. Here is what the same charts look like:

| Length | CEL Count | Competitive Count | Percent CEL/Competitive |
| --- | --- | --- | --- |
| 2 | 63 | 127 | 49.61% |
| 3 | 645 | 1347 | 47.88% |
| 4 | 2296 | 5638 | 40.72% |
| 5 | 4320 | 12973 | 33.3% |
| 6 | 6773 | 23035 | 29.4% |
| 7 | 8948 | 34345 | 26.05% |
| 8 | 9431 | 42153 | 22.37% |
| 9 | 8676 | 42935 | 20.21% |
| 10 | 7206 | 37749 | 19.09% |
| 11 | 5103 | 29591 | 17.25% |
| 12 | 3328 | 21506 | 15.47% |
| 13 | 1917 | 14703 | 13.04% |
| 14 | 954 | 9652 | 9.88% |
| 15 | 474 | 6103 | 7.77% |
| Total | 60133 | 281857 | 21.33% |

| Letter | CEL Count | Competitive Count | Percent CEL/Competitive |
| --- | --- | --- | --- |
| A | 3511 | 16315 | 21.52% |
| B | 3371 | 15380 | 21.92% |
| C | 5694 | 25223 | 22.57% |
| D | 3679 | 16719 | 22.0% |
| E | 2401 | 11397 | 21.07% |
| F | 2492 | 10676 | 23.34% |
| G | 1787 | 9410 | 18.99% |
| H | 2097 | 10619 | 19.75% |
| I | 2412 | 9684 | 24.91% |
| J | 472 | 2315 | 20.39% |
| K | 388 | 3411 | 11.37% |
| L | 1688 | 8105 | 20.83% |
| M | 3082 | 16034 | 19.22% |
| N | 1186 | 6782 | 17.49% |
| O | 1659 | 9017 | 18.4% |
| P | 4725 | 24560 | 19.24% |
| Q | 311 | 1413 | 22.01% |
| R | 4161 | 15168 | 27.43% |
| S | 7345 | 32194 | 22.81% |
| T | 3203 | 14656 | 21.85% |
| U | 1673 | 9695 | 17.26% |
| V | 894 | 4609 | 19.4% |
| W | 1614 | 5950 | 27.13% |
| X | 10 | 309 | 3.24% |
| Y | 167 | 1040 | 16.06% |
| Z | 111 | 1176 | 9.44% |
| Total | 60133 | 281857 | 21.33% |

After making a second and third revision, the total number of words is 67520. Here is what the same charts look like:

| Length | CEL Count | Competitive Count | Percent CEL/Competitive |
| --- | --- | --- | --- |
| 2 | 66 | 127 | 51.97% |
| 3 | 635 | 1347 | 47.14% |
| 4 | 2442 | 5638 | 43.31% |
| 5 | 4665 | 12973 | 35.96% |
| 6 | 7407 | 23035 | 32.16% |
| 7 | 9901 | 34345 | 28.83% |
| 8 | 10700 | 42153 | 25.38% |
| 9 | 9834 | 42935 | 22.9% |
| 10 | 8140 | 37749 | 21.56% |
| 11 | 5823 | 29591 | 19.68% |
| 12 | 3810 | 21506 | 17.72% |
| 13 | 2292 | 14703 | 15.59% |
| 14 | 1185 | 9652 | 12.28% |
| 15 | 620 | 6103 | 10.16% |
| Total | 67520 | 281857 | 23.96% |

| Letter | CEL Count | Competitive Count | Percent CEL/Competitive |
| --- | --- | --- | --- |
| A | 3808 | 16315 | 23.34% |
| B | 3829 | 15380 | 24.9% |
| C | 6290 | 25223 | 24.94% |
| D | 4190 | 16719 | 25.06% |
| E | 2685 | 11397 | 23.56% |
| F | 2872 | 10676 | 26.9% |
| G | 2081 | 9410 | 22.11% |
| H | 2400 | 10619 | 22.6% |
| I | 2645 | 9684 | 27.31% |
| J | 527 | 2315 | 22.76% |
| K | 488 | 3411 | 14.31% |
| L | 1988 | 8105 | 24.53% |
| M | 3646 | 16034 | 22.74% |
| N | 1396 | 6782 | 20.58% |
| O | 1850 | 9017 | 20.52% |
| P | 5369 | 24560 | 21.86% |
| Q | 323 | 1413 | 22.86% |
| R | 4483 | 15168 | 29.56% |
| S | 8016 | 32194 | 24.9% |
| T | 3572 | 14656 | 24.37% |
| U | 1947 | 9695 | 20.08% |
| V | 1047 | 4609 | 22.72% |
| W | 1739 | 5950 | 29.23% |
| X | 11 | 309 | 3.56% |
| Y | 184 | 1040 | 17.69% |
| Z | 134 | 1176 | 11.39% |
| Total | 67520 | 281857 | 23.96% |
