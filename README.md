<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>English to Braille Translator</title>
  <style>
    body { font-family: Arial, sans-serif; text-align: center; padding: 20px; }
    textarea { width: 80%; height: 100px; margin-bottom: 10px; }
    .braille-output { font-size: 2em; letter-spacing: 5px; white-space: pre-wrap; }
  </style>
  <script>
    const englishToBraille = {
      "a": "⠁", "b": "⠃", "c": "⠉", "d": "⠙", "e": "⠑",
      "f": "⠋", "g": "⠛", "h": "⠓", "i": "⠊", "j": "⠚",
      "k": "⠅", "l": "⠇", "m": "⠍", "n": "⠝", "o": "⠕",
      "p": "⠏", "q": "⠟", "r": "⠗", "s": "⠎", "t": "⠞",
      "u": "⠥", "v": "⠧", "w": "⠺", "x": "⠭", "y": "⠽", "z": "⠵",
      "A": "⠠⠁", "B": "⠠⠃", "C": "⠠⠉", "D": "⠠⠙", "E": "⠠⠑",
      "F": "⠠⠋", "G": "⠠⠛", "H": "⠠⠓", "I": "⠠⠊", "J": "⠠⠚",
      "K": "⠠⠅", "L": "⠠⠇", "M": "⠠⠍", "N": "⠠⠝", "O": "⠠⠕",
      "P": "⠠⠏", "Q": "⠠⠟", "R": "⠠⠗", "S": "⠠⠎", "T": "⠠⠞",
      "U": "⠠⠥", "V": "⠠⠧", "W": "⠠⠺", "X": "⠠⠭", "Y": "⠠⠽", "Z": "⠠⠵",
      " ": " ", ".": "⠲", ",": "⠂", ";": "⠆", ":": "⠒", "?": "⠦",
      "!": "⠖", "’": "⠄", "-": "⠤", "(": "⠶", ")": "⠶", "'": "⠄",
      "\"": "⠐⠦", "/": "⠌", "\n": "\n"
    };

    function translateToBraille(text) {
      let brailleText = "";
      for (let char of text) {
        brailleText += englishToBraille[char] !== undefined ? englishToBraille[char] : char;
      }
      document.getElementById("outputText").innerText = brailleText;
    }

    window.addEventListener("DOMContentLoaded", () => {
      const inputField = document.getElementById("inputText");
      inputField.addEventListener("input", () => translateToBraille(inputField.value));
    });
  </script>
</head>
<body>
  <h2>English to Braille Translator</h2>
  <textarea id="inputText" placeholder="Enter English text..."></textarea>
  <p><strong>Braille Translation:</strong></p>
  <p class="braille-output" id="outputText"></p>
</body>
</html>
