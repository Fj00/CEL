# CWL

Common Word List (CWL), a word list with common words, for word games.

## Background

I compiled this word list in two months. I am releasing it into the public domain so anyone can use or modify it at will.

It was a project envisioned by David Eldar, the self-proclaimed second best Scrabble player in the world.

The purpose of CWL is to bring more people to word games. Traditional dictionaries and word lists currently in use in conjunction with popular word games are filled with obscure and impractical words. 

This is still a work in progress and will never achieve perfection. Next steps are to merge additional word lists made by other community members, described in more detail below.

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

2of12

filtered by CSW

Google search results typically > 1M

A data set containing the full text of 8.4M internet articles (34 GB of text) was processed for word frequency and then filtered by CSW.

A 0-10 score for each word was computed using this formula: `(10/log(1 + freq("the")))*log(1 + freq(word))`

"the" had the highest frequency of any 2-15 letter word, and is used to normalize the score.

Words above 3 almost always make the cut, whereas words below 2 almost always miss the cut. 

For 2 letter words, a cutoff of 7 was able to split the very common words from the rest.
For 3 letter words, a cutoff of 5 was helpful in determining how common they were.

Google Books Ngram Viewer was also helpful for 2-3 letter words. It provided a percent score for each of the words based on their frequency within books. A 0-10 score was computed from it using the following formula: `10*(log(ngram) - min(log(ngram)))/(max(log(ngram)) - min(log(ngram)))`

A cutoff of 4 was used for 2s, and a cutoff of 3.5 was used for 3s.

Expletives, slurs and pejorative words were left in for completeness, but there is an ongoing discussion for how to handle them.

Names or proper nouns can conflate the scores, so those words were recognized and handled on a case-by-case basis.

Comparatives and superlatives are a gray area. Internet articles usually avoid using them, and their scores are low in general, whereas conversational English would be more likely to use them. Similarly, adverbs are likely used less in writing. These might need to be handled on a case-by-case basis.

Loanwords are generally avoided

Historical, archaic or outmoded words are generally avoided

Words that are common but limited to specific fields

Uncountable nouns have the plural omitted in almost all cases, but often there is a little bit of gray area, so some are included.

Inflections are usually all included, however oftentimes a group of inflections will have a subset that are very common, whereas one or more words are not. For example, a noun and its plural along with an adjectival form might be included, where as the present participle of the verb is excluded. Another example is where only the adjectival form and the gerund form are common.

Even though the 9-15 letter words have also been examined, they are a lot less important for some games where the majority of words employed are less than 9 letters.

Variants of words are only included if they are common enough.

Letters from the Greek alphabet have been included for completeness, regardless of commonality. Letters from the Hebrew alphabet have been omitted. However, spellings of letters from the English alphabet have also been omitted since they aren't typically spelled out in writing. Greek letters typically are treated as uncountable nouns, however a few have auxiliary definitions that require inflections, such as DELTA(S).

Elements 1-103 in the periodic table are all included for completeness. Elements 104-118 are all theoretical and in most cases have been synthesized in only very small quantities.

Agent nouns (-ER, -OR, -IST) are avoided, unless they are significantly common, or a profession, machine or tool.

Favored simple plurals with -ES or -S over more obscure plurals

Only major currencies are included, DOLLAR(S), EURO(S), [Swiss] FRANC(S), POUND(S), YEN. PESO(S) is also included due to commonality.

Impossible to be objective

## Next Steps

I plan on assimilating several word lists compiled by others.

Kenji Matsumoto, Scrabble Grandmaster and top 10 player in North America independently created a list of common words. The overlap between our lists is over 90%, which seems to validate the idea. Kenji's website is here: http://www.breakingthegame.net/

Dani Barker developed an initial word list based on the TV and movie scripts list on https://en.wiktionary.org/wiki/Wiktionary:Frequency_lists, removing words not commonly considered words, proper nouns, and also adding in other commonly used English words. https://github.com/danibarker/CommonWordLexicon

One thing I need to do is look at CSW words that were not in the original starter list I made using 2of12 and sort by letter and score. This way I can find any common words that were not in the original list.

I plan on making a spreadsheet containing this list, Kenji's list, Dani's list, and also the union of CSW19 and NWL18, making sure to point out the removed words from NWL20. The list will contain ngram scores for 2-3 words, as well as the frequency score for all words. In addition, there will be columns for first letter and number of letters, which will help for sorting and filtering. The purpose will be to accomplish all the next steps in one location.

I created a list of both 2 and 3 letter words, however there will probably be a need to crowdsource the smaller words, especially by non-competitive players. Being as objective as possible probably can't compete with the combined opinion of hundreds or thousands of players for whom the list was created.

## Twitch Shoutouts

- David Eldar https://twitch.tv/deldar182
- César Del Solar https://twitch.tv/14domino
- Will Anderson https://twitch.tv/wanderer15
- Fj00 https://twitch.tv/WTFj00
