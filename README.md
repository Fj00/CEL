# CWL

Common Word List (CWL), a word list with common words, for word games.

## Background

I compiled this word list in two months. I am releasing it into the public domain so anyone can use or modify it at will.

It was a project envisioned by David Eldar, who is commonly recognized as the second best Scrabble player in the world.

The purpose of CWL is to bring more people to word games. Traditional dictionaries and word lists currently used in conjunction with popular word games are filled with obscure and impractical words.

This is still a work in progress and will never achieve perfection. The next steps are to merge additional word lists made by other community members, described in more detail below.

## Community

CWL will be initially implemented on the Woogles platform for playing OMGWords (Orthogonal Morphemes Game). https://woogles.io

Woogles is a community whose mission is to:

1. Create a great place to play word games online.
2. Create a tool that lets people of all skill levels from all over the world improve at our favorite board game.
3. Build the best AI our community has ever seen.

Woogles achieved a successful Kickstarter in October last year, and was created by a team led by César Del Solar, one of the top North American Scrabble players. The Woogles team is also made up of several other top players, including Will Anderson, ranked 1st in North America.

## Getting Started

CSW-only words (#)

## Methodology

The working spreadsheet is public. It currently contains 4 tabs, cwl is the current working list, 2s is just 2 letter word selection, 3s is 3 letter word selection, and movies is another list described below. The spreadsheet can be viewed at: https://docs.google.com/spreadsheets/d/1N-LfFbuuVA176f6pI8oTHYtpUGOy7t2i_ovsCTalq4A/edit?usp=sharing

The starter list chosen was 2of12, which contains a list of common words and their inflections, created by finding words that were in at least 2 out of 12 dictionaries that were selected. More information on 2of12 here: http://wordlist.aspell.net/12dicts-readme/#2of12inf

The uncountable nouns (%) in 2of12 were removed almost completely, and it was filtered by the CSW word list. This resulted in a total of 80775 words. There were less than 100 words in 2of12 that were not in CSW. The list was a good start, but due to the methodology and lack of oversight, many words remained that were either obscure or unused. Thus the great purge began.

The list was audited, and initially only the 4-9 letter words and their inflections were considered. I was going to handle the 2-3 letter words at a later point. I started going through the list the first time, but it was apparent that my strategy was evolving over time, even early on. I decided to finish one pass and then make another pass to try to correct the inconsistencies. The second pass, I ended up deciding to fix the 10-15 letter words as well, since many of them would look odd to keep in the list.

Definitions were checked on https://www.dictionary.com/, https://www.collinsdictionary.com/, Google dictionary, and the CSW dictionary.

When necessary, Google search was helpful for figuring out words. Results with less than 1M hits were typically removed.

After the second pass, it was determined that the process was too subjective and there needed to be more objectivity when deciding on words. I had access to a data set containing the cleaned full text of 8.4M internet articles (34 GB of text). That data set was processed for word frequency and then filtered by CSW.

A 0-10 score for each word was computed using this formula: `(10/log(1 + freq(THE)))*log(1 + freq(word))`

THE had the highest frequency of any 2-15 letter word, and is used to normalize the score.

Words above a score of 3 almost always make the cut, whereas words below 2 almost always miss the cut. 

Names and proper nouns can confound the scores, so those words had to be recognized and handled on a case-by-case basis.

For 2 letter words, a cutoff of 7 was able to split the very common words from the rest.
For 3 letter words, a cutoff of 5 was helpful in determining how common they were.

Google Books Ngram Viewer was also helpful for 2-3 letter words. It provided a percent score for each of the words based on their frequency within books. A 0-10 score was computed from it using the following formula: `10*(log(ngram) - min(log(ngram)))/(max(log(ngram)) - min(log(ngram)))`

A cutoff of 4 was used for 2s, and a cutoff of 3.5 was used for 3s.

For the most part, onomatopoeia are left out, especially for 2-3 letter words with consonant clusters. I made that determination mainly due to my PTSD from playing HM in a game with classmates in school and getting mocked for it. There are some instances of onomatopoeia which are common enough to keep, such as various animal sounds used as verbs.

Expletives, slurs and pejorative words were left in for completeness, but there is an ongoing discussion for how to handle them. I don't believe it is up to me whether they get used or not at the end of the day. There is a good case that such words could scare off some audiences. It is at least a good idea to make a list of such words and maintain a separate list with those words removed.

The list tends to favor non-CSW and American-only spellings, although there are British spellings for many words. This might be an area that needs better consistency. There were less than 200 CSW-only words that made the cut in the end, however there are likely many more that need to be investigated. There is a plan described below in next steps to address this issue.

Comparatives and superlatives are a gray area. Internet articles usually avoid using them, and their scores are low in general, whereas conversational English would be more likely to use them. Similarly, adverbs are likely used less in writing. These might need to be handled on a case-by-case basis.

Loanwords are generally avoided, unless they have a significant degree of commonality. Historical, archaic or outmoded words are also generally avoided.

Words that are common but limited to specific fields are avoided. Some instances are words only related to high-level chemistry, physics or mathematics.

Elements 1-103 in the periodic table are all included for completeness. It would be hard to determine what counts as a common element. However, elements 104-118 are all theoretical and in most cases have been synthesized in only very small quantities. In addition, all have been recently named, therefore they are not included.

Letters from the Greek alphabet have been included for completeness, regardless of commonality. Letters from the Hebrew alphabet have been omitted. However, spellings of letters from the English alphabet have also been omitted since they aren't typically spelled out in writing. Greek letters typically are treated as uncountable nouns, however a few have auxiliary definitions that require inflections, ALPHA(S), BETA(S), DELTA(S).

Uncountable nouns have the plural omitted in almost all cases, mainly thanks to the 2of12 list having labeled them. However, there were still many more that needed to be classified. Often there is a little bit of gray area, so some plurals are included. It mostly depended on the ratio between the frequency of the singular and plural forms.

Inflections are usually all included, however oftentimes a group of inflections will have a subset that are very common, whereas one or more words are not. For example, a noun and its plural along with an adjectival form might be included, where as the present participle of the verb is excluded. Another example is where only the adjectival form and the gerund form are common.

Simple plurals with -ES or -S were favored over more obscure plurals, even in some cases where the usage was skewed in the other direction.

Even though all the 9-15 letter words were examined, they are a lot less important for some games where the majority of words employed are less than 9 letters. They were left in mainly for extending 7-8 letter words using inflections, and also as an attempt to slow Nigel Richards down when he learns the dictionary.

Variants of words are only included if they are common enough. Verbs ending in L often had both single and double L inflections, and there was a lot of unmanageable inconsistency with frequency. This might be a reason to look into it making it more consistent later.

Agent nouns (-ER, -OR, -IST) are avoided, unless they are significantly common, or a profession, machine or tool.

The only major currencies included are DOLLAR(S), EURO(S), [Swiss] FRANC(S), POUND(S), YEN. PESO(S) is also included due to commonality.

A number of words were added to the list that were either missed inflections or just missed making the list altogether. There is a plan to analyze the rest of the NWL+CSW words described in more detail below.

This is just a disclaimer that it is impossible to be objective in every instance, and it is fine that people disagree with some of the choices that were made. Hopefully the goal is achieved that people who don't play word games competitively will enjoy playing more with a word list that contains only words they know.

## Stats

Again, the initial list contained 80775 words. The number of words removed was 24688, making 56087. There are 124 CSW-only words. There were 150 additions that weren't 2 or 3 letters. The total number of 2 letter words is 65 (out of 127 NWL+CSW), and the total number of 3 letter words is 640 (out of 1347 NWL+CSW). Combining the purged list with the additions and 2-3 letter words makes 56311 words, out of which there are:

| Length | CWL Count | NWL+CSW Count | Percent CWL/NWL+CSW |
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

Unsurprisingly, the proportion of words in CWL is strictly decreasing as the number of letters increase. The number of CWL words with 2-8 letters is 31396 for reference. Here is the same table for words starting with letters A-Z:

| Letter | CWL Count | NWL+CSW Count | Percent CWL/NWL+CSW |
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

## Next Steps

I plan on assimilating several word lists compiled by others.

Kenji Matsumoto, Scrabble Grandmaster and top 10 player in North America independently created a list of common words. The overlap between our lists is over 90%, which seems to validate the idea. Kenji's website is here: http://www.breakingthegame.net/

Dani Barker developed an initial word list based on the TV and movie scripts list on https://en.wiktionary.org/wiki/Wiktionary:Frequency_lists, removing words not commonly considered words, proper nouns, and also adding in other commonly used English words. https://github.com/danibarker/CommonWordLexicon

One thing I need to do is look at CSW words that were not in the original starter list I made using 2of12 and sort by letter and score. This way I can find any common words that were not in the original list.

I plan on making a spreadsheet containing this list, Kenji's list, Dani's list, and also the union of CSW19 and NWL18, making sure to point out the removed words from NWL20 and NWL/CSW-only words. The list will contain ngram scores for 2-3 words, as well as the frequency score for all words. In addition, there will be columns for first letter and number of letters, which will help for sorting and filtering. The purpose will be to accomplish all of these next steps in one location.

I put extra effort into creating lists of 2 and 3 letter words, however there will probably be a need to crowdsource the smaller words, especially by non-competitive players. Being as objective as possible probably can't compete with the combined opinion of hundreds or thousands of players for whom the list was created. Maybe a survey with all the 2s and maybe 3s needs to be created and sent to the appropriate audience for validation.

## Twitch Shoutouts

- David Eldar https://twitch.tv/deldar182
- César Del Solar https://twitch.tv/14domino
- Will Anderson https://twitch.tv/wanderer15
- Fj00 https://twitch.tv/WTFj00
