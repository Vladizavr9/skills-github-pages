<!DOCTYPE html>
<html>
<head>
    <title>Учебный материал</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            background-color: #f9f9f9;
            padding: 20px;
            overflow-x: hidden;
        }

        .container {
            display: flex;
            flex-direction: column; /* Blocks stack vertically */
            align-items: center;
            max-width: 800px;
            margin: 0 auto;
        }

        .block {
            width: 90%; /* Wider blocks */
            max-width: 700px; /* Keep blocks from expanding too much on large screens */
            padding: 25px; /* Increased padding */
            border-radius: 12px; /* More rounded corners */
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            text-align: center;
            border: 1px solid rgba(0, 0, 0, 0.1);
            box-sizing: border-box;
            position: relative;
            min-height: 200px; /* Updated minimum height */
            margin-bottom: 20px; /* Space between blocks */
            overflow: hidden;
            transition: all 0.3s ease;
            color: #333;
        }

        h2 {
            font-size: 1.6em; /* Slightly larger headings */
            margin: 5px 0 10px;
            color: #000;
        }

        textarea {
            width: 100%;
            padding: 12px; /* Increased padding for textareas */
            border: 1px solid #ccc;
            border-radius: 6px;
            font-family: inherit;
            font-size: 1.1em; /* Slightly larger font in textareas */
            box-sizing: border-box;
            resize: vertical;
            min-height: 100px; /* Larger textarea height */
            overflow-y: auto;
            /* Adjust height to match the border-box */
            height: calc(100% - 44px); /* Adjusted to accommodate the padding */
            background-color: #fff;
            color: #000;
        }

        .expand-button {
            background-color: transparent; /* Make background transparent */
            border: none; /* Remove the border */
            color: rgba(76, 175, 80, 0.5); /* Green with 50% opacity - adjust rgba values or color name as needed */
            font-size: 1.5em; /* Increase the font size for the emoji */
            cursor: pointer;
           /* Remove all circular button styles */
        }

        .expand-button:hover {
            color: rgba(62, 142, 65, 0.8); /* Darker icon color on hover with more opacity */
        }
    </style>
</head>
<body>

    <div class="container">
        <div class="block" id="videoBlock">
            <h2>Vidéo</h2>
              <div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden;">
                  <iframe src="https://www.youtube.com/embed/2bch5kWyecw?start=156" style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; border:0;" allowfullscreen></iframe>
              </div>
            <button class="expand-button" data-target="videoBlock">↕️</button>
        </div>

        <div class="block" id="vocabulaireBlock">
            <h2>Vocabulaire</h2>
            <textarea id="vocabulaireInput" rows="6">
1. Je suis . . .
2. Vous êtes . . .
3. Il est . . .
4. C'est . . .
5. Je m'appelle . . .
6. Tu t'appelles . . .
7. Il s'appelle . . .
8. Qui est-ce ?
9. Oui
10. Non
11. Bonjour
12. et
13. monsieur
14. ma femme
15. mari
            </textarea>
            <button class="expand-button" data-target="vocabulaireInput">↕️</button>
        </div>

        <div class="block" id="dialogueBlock">
            <h2>Dialogue</h2>
            <textarea id="dialogueInput" rows="6">
1) - Bonjour, monsieur. Vous vous appelez . . . ?
- Doucet. Yves Doucet. Et voici ma femme,
Alice.
- Bonjour, madame.
2) - Bonjour. Je suis Alice Doucet. Vous êtes
madame Falco ?
- Bonjour. Oui, je m'appelle Nicole Falco.
Aldo, mon mari.
- Arnaud ?
- Non. Aldo. Il s'appelle Aldo.
3) - Qui est-ce ?
- C'est Aldo. Aldo Falco.
- Aldo ? Il est italien ?
- Oui, et elle, c'est Nicole, elle est française.
4) - Tu t'appelles Giacomo ! Tu es italien ?
- Oui, oui. Je suis italien.
            </textarea>
            <button class="expand-button" data-target="dialogueInput">↕️</button>
        </div>

        <div class="block" id="practiceBlock">
            <h2>Pratique</h2>
            <textarea id="practiceInput" rows="6">
1) «Я являюсь . . .»
   a) Je suis
   b) J'ai

2) «Вы являетесь . . .»
   a) Vous êtes
   b) Vous avez

3) «Он является . . .»
   a) Il est
   b) Il a

4) «Это . . .»
   a) C'est
   b) Ce sont

5) «Меня зовут . . .»
   a) Je m'appelle
   b) Je suis

6) «Тебя зовут . . .»
   a) Tu t'appelles
   b) Tu es

7) «Его зовут . . .»
   a) Il s'appelle
   b) Il est

8) «Кто это?»
   a) Qui est-ce ?
   b) Qu'est-ce que c'est ?

9) «Да»
   a) Oui
   b) Non

10) «Нет»
    a) Non
    b) Oui

11) «Здравствуйте»
    a) Bonjour
    b) Salut

12) «И»
    a) et
    b) ou

13) «Господин»
    a) monsieur
    b) madame

14) «Моя жена»
    a) ma femme
    b) mon mari

15) «Муж»
    a) mari
    b) femme
            </textarea>
            <button class="expand-button" data-target="practiceInput">↕️</button>
        </div>

        <div class="block" id="discussionBlock">
            <h2>Discussion</h2>
            <textarea id="discussionInput" rows="6">
1) Say "Hello"
2) Say what your name is.
3) Clarify smb's name.
4) Say what your friend's name is.
5) Say "It's my husband"
6) Ask "Who is it?"
7) Ask "Are you Italian?"
8) Say "I am French / She is French"
            </textarea>
            <button class="expand-button" data-target="discussionInput">↕️</button>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const blockIds = ['videoBlock','vocabulaireBlock', 'dialogueBlock', 'practiceBlock', 'discussionBlock'];

            function generateGradient() {
              const hue = Math.floor(Math.random() * 360);
              const saturation = 70;
              const lightness = 85;

                return `linear-gradient(to right, hsl(${hue}, ${saturation}%, ${lightness}%), white)`;
            }

            blockIds.forEach(blockId => {
                const block = document.getElementById(blockId);
                block.style.backgroundImage = generateGradient();
            });

            const expandButtons = document.querySelectorAll('.expand-button');

            expandButtons.forEach(button => {
                button.addEventListener('click', () => {
                    const targetId = button.dataset.target;
                    const textarea = document.getElementById(targetId);
                    const video = document.getElementById(targetId)

                  if (targetId === 'videoBlock') {
                       const videoBlock = document.getElementById('videoBlock');
                       if (videoBlock.style.height === 'auto' || videoBlock.style.height === '') {
                            videoBlock.style.height = 'auto';
                        } else {
                            videoBlock.style.height = '';
                        }
                  }

                    if (textarea) {
                        if (textarea.style.height === 'auto' || textarea.style.height === '') {
                            // Expand
                            textarea.style.height = textarea.scrollHeight + "px";
                        } else {
                            // Shrink
                            textarea.style.height = '';
                        }
                    }
                });
            });
        });
    </script>

</body>
</html>
