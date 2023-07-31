### 1 Display middle characters of string

def get_middle_character(word):
    word_length = len(word)
    middle_index = word_length // 2

    if word_length % 2 == 0:
        return word[middle_index - 1 : middle_index + 1]
    else:
        return word[middle_index]

Test the function
print(get_middle_character("test"))  # Output: "es"
print(get_middle_character("python"))  # Output: "th"
print(get_middle_character("hello"))  # Output: "l"

### 2 Make string upper case
def make_upper_case(s):
    return s.upper()

### 3 A hero is on his way to the castle to complete his mission. However, he's been told that the castle is surrounded with a couple of powerful dragons! each dragon takes 2 bullets to be defeated, our hero has no idea how many bullets he should carry.. Assuming he's gonna grab a specific given number of bullets and move forward to fight another specific given number of dragons, will he survive?Return true if yes, false otherwise :)

def hero(bullets, dragons):
    x = dragons * 2
    return bullets >= x

### 4 For simplicity, you'll have to capitalize each word, check out how contractions are expected to be in the example below.Your task is to convert strings to how they would be written by Jaden Smith. The strings are actual quotes from Jaden Smith, but they are not capitalized in the same way he originally typed them.
Example:
Not Jaden-Cased: "How can mirrors be real if our eyes aren't real"
Jaden-Cased:     "How Can Mirrors Be Real If Our Eyes Aren't Real"
def to_jaden_case(string):
    x = string.split()
    cw = [word.capitalize() for word in x]
    return " ".join(cw)

### 
