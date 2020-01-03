```python



import string


# (1) Introduce an arbitrary string of English text
arbitraryString = "12345To Sherlock Holmes she is always the woman. 456I have seldom heard him ment467ion her 536under any other name. In his eyes she eclipses and predominates the whole of her sex. It was not that he felt any emotion akin to love for Irene Adler. All emotions, and that one particularly, were abhorrent to his cold, precise but admirably balanced mind. He was, I take it, the most perfect reasoning and observing machine that the world has seen, but as a lover he would have placed himself in a false position. He never spoke of the softer passions, save with a gibe and a sneer. They were admirable things for the observer-excellent for drawing the veil from mens motives and actions. But for the trained reasoner to admit such intrusions into his own delicate and finely adjusted temperament was to introduce a distracting factor which might throw a doubt upon all his mental results. Grit in a sensitive instrument, or a crack in one of his own high-power lenses, would not be more disturbing than a strong emotion in a nature such as his. And yet there was but one woman to him, and that woman was the late Irene Adler, of dubious and questionable memory."
print("(1) arbitraryString:","\n\n",arbitraryString,"\n\n")




# (2) Remove all digits from the string (e.g., '2'), leaving only alphabet characters (that is, the letters)
numbers = string.digits                                       # all the digits are assigned into a string called "numbers"
for number in numbers:                                        # all the digits are replaced with a for each loop of numbers
    arbitraryString = arbitraryString.replace(number, "") 
arbitraryString = arbitraryString.strip()                     # all the whitespaces are deleted.
print("(2) Raw text only includes letters below:","\n\n",arbitraryString,"\n")




# (3) Calculate the number of words in the string, and have your program print the result
punc = string.punctuation                                      # all the punctions values in a string called "punc"
wordList = list()                                              # creating a list to put all the words of the text into
lowerArbitraryString = arbitraryString.lower()                 # creating a list to play on lower letters.
arbitraryStringWords = arbitraryString.lower()                 # all the words converted to lower cases to prevent duplication of capital lettered same words
for p in punc:                                                 # eliminating of all punctiations in the text with a for each loop
    arbitraryStringWords = arbitraryStringWords.replace(p, " ") 
wordList = arbitraryStringWords.split()                        # all the words is put into the a list called "wordList"              
wordCount = len(wordList)                                      # to count all the words in the list, I used "len" function. This basically gives the number of objects in a list.
print("(3) Total number of the words in the text is",wordCount,"\n\n")




# (4) Calculate the number of times the letter 'a' appears in the string, and print the result
aLetterCount = lowerArbitraryString.count("a")                 # counting "a" letter in the lowered string
print("(4) Total number of 'a' letters(including lower and upper cases) is",aLetterCount,"\n\n")




# (5) Using the python 'for' loop, do the same for all of the 26 letters in the alphabet. Note that both upper and lower case letters should be counted.
lowerLetters = string.ascii_lowercase                          # assigning all the lower letters into a string called "lowerLetters"
allLetters = string.ascii_letters                              # assigning all the letters into a string called "allLetters"

print("(5) Total letter count is below (while all text is in lowercase):\n")
for lowers in lowerLetters:                                    # counting all the lower letters in the text throughout the "lowerLetters" string
    letterCount = 0
    letterCount = lowerArbitraryString.count(lowers)
    print("Total letter of '{}' is counted as {}".format(lowers, letterCount))

print("\n","(5) Total letter count in is below(lowercase and uppercase separately):\n")
for letter in allLetters:                                      # counting all the letters in the text throughout the "allLetters" string
    letterCount = 0
    letterCount = arbitraryString.count(letter)
    print("Total letter of '{}' is counted as {}".format(letter, letterCount))

print("\n")




# (6) Create a dictionary in which the frequency of each letter in the text is the value, and the letter is the key.
letterDict = dict()
print("(6) Letter Dictionary is as below:\n")
for letter in lowerArbitraryString:
    letterDict[letter] = letterDict.get(letter,0) + 1

for key in sorted(letterDict):                                 # to show all letters in a sequence, the dictionary was sorted.
    print ("%s: %s" % (key, letterDict[key]))
print("\n")




# (7) Using the dictionary, have your program print the text 'The most frequently appearing letter is X, and it appears in the text N times', where X and N are calculated in the step above.
largest = 0
theKey = None
for key,value in letterDict.items():                           # two indexed for loop was used to find the max value in the dictionary
    if value > largest:
        largest = value
        theKey = key 

if theKey == " ": 
    theKey = "Space"
    print("(7) The most frequently appearing character is '{}', and it appears in the text {} times.".format(theKey,largest))


    # Printing the non-space the most frequently used letter 
largest = 0
theKey = None
noSpaceLetterDict = dict()
noSpaceLetterDict = letterDict.copy()                       # another dictionary was created to put into all letters but spaces. And a copy of letterDict was assigned into it.
del noSpaceLetterDict[" "]                                  # spaces were removed from the dictionary
for key,value in noSpaceLetterDict.items():                 # two indexed for loop was used to find the max value in the dictionary
    if value > largest:
        largest = value
        theKey = key 

print("(7) The most frequently appearing letter is '{}', and it appears in the text {} times.".format(theKey,largest),"\n\n")

        
        

# (8) Using the 'while loop' and the 'if' statement, print out any letters that are missing in the string.
letterCount = len(lowerArbitraryString)                         # Counting the number of letters that the text includes
i = 0
missedLetter = 0
while i < letterCount:                                          # While loop continues as long as the number of the letters in the text.
    if lowerArbitraryString[i] not in letterDict:               # if the index value of "lowerArbitraryString" string is not in our dictionary, it prints the missed letter
        print("(8) {} letter is missed".format(lowerArbitraryString[i]))
        missedLetter += 1
    i += 1
if missedLetter == 0:                                           # if there is no missed letter, it is printed.
    print("(8) There is no letter has been missed...")
