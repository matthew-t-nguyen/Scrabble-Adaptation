# Scrabble-Adaptation
"Scrabble Adaptation" Project

**OVERVIEW**

This game is a lot like Scrabble or Words With Friends. Letters are dealt to players, who then construct one or more words using their letters. Each valid word earns the user points, based on the length of the word and the letters in that word.
The rules of the game are as follows.

Dealing
*	A player is dealt a hand of HAND_SIZE letters of the alphabet, chosen at random. This may include multiple instances of a particular letter.
*	The player arranges the hand into as many words as they want out of the letters, but using each letter at most once.
*	Some letters may remain unused, though the size of the hand when a word is played does affect its score.

Scoring
*	The score for the hand is the sum of the score for each word formed.
*	The score for a word is the product of two components:
o First component: the sum of the points for letters in the word. o Second component: either [7 * word_leng th - 3 * (n - word_length)] or 1, whichever value is greater, where:
   1. word_length is the number of letters used in the word
   2. n is the number of letters available in the current hand
   3.	Letters are scored as in Scrabble; A is worth 1, B is worth 3, C is worth 3, D is worth 2, E is worth 1, and so on. We have defined the dictionary SCRABBLE_LETTER_VALUES that maps each lowercase letter to its Scrabble letter value.
*	Examples:
  1. For example, if n=6 and the hand includes 1 'w', 2 'e's, and 1 'd' (as well as two other letters), playing the word 'weed' would be worth 176 points:(4+1+1+2) * (7*4 - 3*(6-4)) = 176. The first term is the sum of the values of each letter used; the second term is the special computation that rewards a player for playing a longer word, and penalizes them for any left over letters.
  2. As another example, if n=7, playing the word 'it' would be worth 2 points:(1+1) * (1) = 2. The second component is 1 because 7*2 - 3*(7 - 2) = -1, which is less than 1.
