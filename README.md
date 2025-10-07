# Spellchecker
This project is designed to automatically detect and correct spelling mistakes in user-input text. 

🛠️ Skills & Tools Used:
Python (Core Programming)
OOP (Object-Oriented Programming) → Created a class-based structure (SpellCheckerApp)
String Handling → Used methods like split() and join() for breaking and joining text
Conditionals & Loops → Implemented if conditions and while True loop for continuous checking
User Input Handling → input() for interactive text correction

Library Used:
pyspellchecker

 – For identifying and suggesting correct words
⚡ Functions & Methods Highlighted:
split() → To divide text into words
join() → To re-combine corrected words into a sentence
correction() → From SpellChecker library, to suggest the best correction
lower() → For case-insensitive comparison
print() → To display corrections in real-time


📌 Project Flow:
Import the SpellChecker library
Take user input (sentence/text)
Identify wrong words and suggest corrections
Replace mistakes with correct words
Display the corrected sentence

# step-1 importing the required library
from spellchecker import SpellChecker

# step-2 creating the app class 
class SpellCheckerApp:
 def __init__(self):
 self.spell = SpellChecker()

 def correct_text(self, text):
 words = text.split() # split text into words
 corrected_words = []

 for word in words:
 corrected_word = self.spell.correction(word) # find correction
 if corrected_word and corrected_word != word.lower():
 print(f'Correcting "{word}" to "{corrected_word}"')
 corrected_words.append(corrected_word if corrected_word else word)

 # step-4 returning the corrected text
 return ' '.join(corrected_words)

 # step-5 running the app
 def run(self):
 print("\n--- Spell Checker ---") 
 while True:
 text = input('Enter text to check or type "exit" to quit: ')
 if text.lower() == 'exit':
 print('Closing the program....')
 break

 corrected_text = self.correct_text(text)
 print(f'Corrected Text : {corrected_text}')


# step-6 running the main program
if __name__ == "__main__":
 SpellCheckerApp().run()


👉 Example:
Input: Helo frend
 Output:

Correcting "Helo" to "Hello"
Correcting "frend" to "friend"
Corrected Text : Hello friend
