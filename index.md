<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>English Sentences</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f4f5f7;
            margin: 0;
            padding: 0;
            color: #333;
        }

        .container {
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 30px;
        }

        .card-row {
            display: flex;
            width: 100%;
            justify-content: space-between;
            margin-bottom: 30px;
        }

        .card {
            width: 420px;
            height: 240px;
            perspective: 1000px;
            position: relative;
        }

        .card-inner {
            width: 100%;
            height: 100%;
            position: relative;
            transition: transform 0.4s;
            transform-style: preserve-3d;
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.18);
            border-radius: 15px;
            cursor: pointer;
            background-color: #fff;
        }

        .card.flipped .card-inner {
            transform: rotateY(180deg);
        }

        .card-front, .card-back {
            width: 100%;
            height: 100%;
            position: absolute;
            backface-visibility: hidden;
            border-radius: 15px;
            overflow: hidden;
            padding: 20px;
            box-sizing: border-box;
            display: flex;
            flex-direction: column;
            justify-content: space-around;
        }

        .card-front {
            background-color: #e8f0fe;
            color: #4a4a4a;
        }

        .card-back {
            transform: rotateY(180deg);
            background-color: #d7f1da;
            color: #383838;
        }

        .sentence {
            font-size: 17px;
            line-height: 1.4;
            text-align: left;
            margin-bottom: 5px;
        }

        .sentence::before {
            content: attr(data-number) ". ";
            font-weight: bold;
            margin-right: 7px;
            color: #777;
        }

        /* Button Styles */
        .button-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            margin-left: 10px;
        }

        .card-button {
            width: 40px;
            height: 40px;
            border: none;
            border-radius: 50%;
            cursor: pointer;
            margin-bottom: 5px;
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
            font-size: 22px;
            opacity: 0.7;
            transition: opacity 0.2s, background-color 0.2s;
        }

        .card-button:active {
            transform: scale(0.95);
        }

        .correct-button {
             background-color: rgba(76, 175, 80, 0.7); /* Semi-transparent green */
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
        }

        .correct-button.active {
            background-color: #00FF00; /* Very bright green, fully opaque  */
            opacity: 1;
        }

        .incorrect-button {
            background-color: rgba(244, 67, 54, 0.7); /* Red, transparent */
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
        }

        .incorrect-button.active {
            background-color: #f44336;
            opacity: 1;
        }

        .correct-button::before {
            content: '\2713';
        }
        .incorrect-button::before {
            content: '\2715';
        }
    </style>
</head>
<body>

    <div class="container">

        <!-- Card 1 -->
        <div class="card-row">
            <div class="card" onclick="flipCard(this, 1)">
                <div class="card-inner">
                    <div class="card-front">
                        <div class="sentence" data-number="1"><b>I have a cat.</b></div>
                        <div class="sentence" data-number="2"><b>She is an artist.</b></div>
                        <div class="sentence" data-number="3"><b>He didn’t buy a car.</b></div>
                        <div class="sentence" data-number="4"><b>Is it an interesting book?</b></div>
                    </div>
                    <div class="card-back" data-original-sentences='[
                        "<div class=\"sentence\"><b>У меня есть кошка.</b></div>",
                        "<div class=\"sentence\"><b>Она - художник.</b></div>",
                        "<div class=\"sentence\"><b>Он не купил машину.</b></div>",
                        "<div class=\"sentence\"><b>Это интересная книга?</b></div>"
                    ]'>
                    </div>
                </div>
            </div>
            <div class="button-container">
                <button class="card-button correct-button" onclick="markCard(this, true, 1)">
                </button>
                <button class="card-button incorrect-button" onclick="markCard(this, false, 1)">
                </button>
            </div>
        </div>

        <!-- Card 2 -->
        <div class="card-row">
            <div class="card" onclick="flipCard(this, 2)">
                <div class="card-inner">
                    <div class="card-front">
                        <div class="sentence" data-number="1"><b>There isn’t any milk left.</b></div>
                        <div class="sentence" data-number="2"><b>Do you have any questions?</b></div>
                        <div class="sentence" data-number="3"><b>They don’t have any apples.</b></div>
                        <div class="sentence" data-number="4"><b>I have some plans for today.</b></div>
                    </div>
                    <div class="card-back" data-original-sentences='[
                        "<div class=\"sentence\"><b>Не осталось молока.</b></div>",
                        "<div class=\"sentence\"><b>У вас есть вопросы?</b></div>",
                        "<div class=\"sentence\"><b>У них нет яблок.</b></div>",
                        "<div class=\"sentence\"><b>У меня есть планы на сегодня.</b></div>"
                    ]'>
                    </div>
                </div>
            </div>
            <div class="button-container">
                <button class="card-button correct-button" onclick="markCard(this, true, 2)">
                </button>
                <button class="card-button incorrect-button" onclick="markCard(this, false, 2)">
                </button>
            </div>
        </div>

        <!-- Card 3 -->
        <div class="card-row">
            <div class="card" onclick="flipCard(this, 3)">
                <div class="card-inner">
                    <div class="card-front">
                        <div class="sentence" data-number="1"><b>They are at home.</b></div>
                        <div class="sentence" data-number="2"><b>Am I late?</b></div>
                        <div class="sentence" data-number="3"><b>She isn’t a doctor.</b></div>
                        <div class="sentence" data-number="4"><b>We are happy.</b></div>
                    </div>
                    <div class="card-back" data-original-sentences='[
                        "<div class=\"sentence\"><b>Они дома.</b></div>",
                        "<div class=\"sentence\"><b>Я опаздываю?</b></div>",
                        "<div class=\"sentence\"><b>Она не доктор.</b></div>",
                        "<div class=\"sentence\"><b>Мы счастливы.</b></div>"
                    ]'>
                    </div>
                </div>
            </div>
            <div class="button-container">
                <button class="card-button correct-button" onclick="markCard(this, true, 3)">
                </button>
                <button class="card-button incorrect-button" onclick="markCard(this, false, 3)">
                </button>
            </div>
        </div>

        <!-- Card 4 -->
         <div class="card-row">
            <div class="card" onclick="flipCard(this, 4)">
                <div class="card-inner">
                    <div class="card-front">
                        <div class="sentence" data-number="1"><b>She was at the park.</b></div>
                        <div class="sentence" data-number="2"><b>Were they late?</b></div>
                        <div class="sentence" data-number="3"><b>I wasn’t tired yesterday.</b></div>
                        <div class="sentence" data-number="4"><b>We were happy.</b></div>
                    </div>
                    <div class="card-back" data-original-sentences='[
                         "<div class=\"sentence\"><b>Она была в парке.</b></div>",
                        "<div class=\"sentence\"><b>Они опоздали?</b></div>",
                        "<div class=\"sentence\"><b>Я не устал вчера.</b></div>",
                        "<div class=\"sentence\"><b>Мы были счастливы.</b></div>"
                    ]'>
                    </div>
                </div>
            </div>
            <div class="button-container">
                <button class="card-button correct-button" onclick="markCard(this, true, 4)">
                </button>
                <button class="card-button incorrect-button" onclick="markCard(this, false, 4)">
                </button>
            </div>
        </div>

        <!-- Card 5 -->
         <div class="card-row">
            <div class="card" onclick="flipCard(this, 5)">
                <div class="card-inner">
                    <div class="card-front">
                        <div class="sentence" data-number="1"><b>He went to the store.</b></div>
                        <div class="sentence" data-number="2"><b>Did she eat an apple?</b></div>
                        <div class="sentence" data-number="3"><b>They didn’t see a movie.</b></div>
                        <div class="sentence" data-number="4"><b>I wrote a letter.</b></div>
                    </div>
                    <div class="card-back" data-original-sentences='[
                       "<div class=\"sentence\"><b>Он пошел в магазин.</b></div>",
                        "<div class=\"sentence\"><b>Она съела яблоко?</b></div>",
                        "<div class=\"sentence\"><b>Они не смотрели фильм.</b></div>",
                        "<div class=\"sentence\"><b>Я написал письмо.</b></div>"
                    ]'>
                    </div>
                </div>
            </div>
            <div class="button-container">
                <button class="card-button correct-button" onclick="markCard(this, true, 5)">
                </button>
                <button class="card-button incorrect-button" onclick="markCard(this, false, 5)">
                </button>
            </div>
        </div>

        <!-- Card 6 -->
         <div class="card-row">
            <div class="card" onclick="flipCard(this, 6)">
                <div class="card-inner">
                    <div class="card-front">
                        <div class="sentence" data-number="1"><b>She will visit her grandma.</b></div>
                        <div class="sentence" data-number="2"><b>Will they go to the beach?</b></div>
                        <div class="sentence" data-number="3"><b>I won’t call you later.</b></div>
                        <div class="sentence" data-number="4"><b>We will finish the project.</b></div>
                    </div>
                    <div class="card-back" data-original-sentences='[
                        "<div class=\"sentence\"><b>Она навестит свою бабушку.</b></div>",
                        "<div class=\"sentence\"><b>Они пойдут на пляж?</b></div>",
                        "<div class=\"sentence\"><b>Я не позвоню тебе позже.</b></div>",
                        "<div class=\"sentence\"><b>Мы закончим проект.</b></div>"
                    ]'>
                     </div>
                </div>
            </div>
            <div class="button-container">
                <button class="card-button correct-button" onclick="markCard(this, true, 6)">
                </button>
                <button class="card-button incorrect-button" onclick="markCard(this, false, 6)">
                </button>
            </div>
        </div>

        <!-- Card 7 -->
        <div class="card-row">
            <div class="card" onclick="flipCard(this, 7)">
                <div class="card-inner">
                    <div class="card-front">
                        <div class="sentence" data-number="1"><b>There is a dog in the yard.</b></div>
                        <div class="sentence" data-number="2"><b>Is there a problem here?</b></div>
                        <div class="sentence" data-number="3"><b>There isn’t a book on the table.</b></div>
                        <div class="sentence" data-number="4"><b>There is a park nearby.</b></div>
                    </div>
                    <div class="card-back" data-original-sentences='[
                        "<div class=\"sentence\"><b>Во дворе есть собака.</b></div>",
                        "<div class=\"sentence\"><b>Здесь проблема?</b></div>",
                        "<div class=\"sentence\"><b>На столе нет книги.</b></div>",
                        "<div class=\"sentence\"><b>Рядом есть парк.</b></div>"
                    ]'>
                    </div>
                </div>
            </div>
            <div class="button-container">
                <button class="card-button correct-button" onclick="markCard(this, true, 7)">
                </button>
                <button class="card-button incorrect-button" onclick="markCard(this, false, 7)">
                </button>
            </div>
        </div>

        <!-- Card 8 -->
        <div class="card-row">
            <div class="card" onclick="flipCard(this, 8)">
                <div class="card-inner">
                    <div class="card-front">
                        <div class="sentence" data-number="1"><b>There are apples in the basket.</b></div>
                        <div class="sentence" data-number="2"><b>Are there flowers in the garden?</b></div>
                        <div class="sentence" data-number="3"><b>There aren’t many people in the room.</b></div>
                        <div class="sentence" data-number="4"><b>There are two cats on the roof.</b></div>
                    </div>
                    <div class="card-back" data-original-sentences='[
                        "<div class=\"sentence\"><b>В корзине есть яблоки.</b></div>",
                        "<div class=\"sentence\"><b>В саду есть цветы?</b></div>",
                        "<div class=\"sentence\"><b>В комнате немного людей.</b></div>",
                        "<div class=\"sentence\"><b>На крыше два кота.</b></div>"
                    ]'>
                     </div>
                </div>
            </div>
            <div class="button-container">
                <button class="card-button correct-button" onclick="markCard(this, true, 8)">
                </button>
                <button class="card-button incorrect-button" onclick="markCard(this, false, 8)">
                </button>
            </div>
        </div>

        <!-- Card 9 -->
        <div class="card-row">
            <div class="card" onclick="flipCard(this, 9)">
                <div class="card-inner">
                    <div class="card-front">
                        <div class="sentence" data-number="1"><b>There was a cat in the garden.</b></div>
                        <div class="sentence" data-number="2"><b>Was there a party at her house?</b></div>
                        <div class="sentence" data-number="3"><b>There wasn’t a storm last night.</b></div>
                        <div class="sentence" data-number="4"><b>There was a mistake in the report.</b></div>
                    </div>
                    <div class="card-back" data-original-sentences='[
                        "<div class=\"sentence\"><b>В саду была кошка.</b></div>",
                        "<div class=\"sentence\"><b>В ее доме была вечеринка?</b></div>",
                        "<div class=\"sentence\"><b>Вчера вечером не было шторма.</b></div>",
                        "<div class=\"sentence\"><b>В отчете была ошибка.</b></div>"
                    ]'>
                       </div>
                </div>
            </div>
            <div class="button-container">
                <button class="card-button correct-button" onclick="markCard(this, true, 9)">
                </button>
                <button class="card-button incorrect-button" onclick="markCard(this, false, 9)">
                </button>
            </div>
        </div>

        <!-- Card 10 -->
        <div class="card-row">
            <div class="card" onclick="flipCard(this, 10)">
                <div class="card-inner">
                    <div class="card-front">
                        <div class="sentence" data-number="1"><b>She is the smartest in the class.</b></div>
                        <div class="sentence" data-number="2"><b>Is this book more interesting than that one?</b></div>
                        <div class="sentence" data-number="3"><b>He isn’t taller than his brother.</b></div>
                        <div class="sentence" data-number="4"><b>This is the best movie I saw.</b></div>
                    </div>
                    <div class="card-back" data-original-sentences='[
                        "<div class=\"sentence\"><b>Она самая умная в классе.</b></div>",
                        "<div class=\"sentence\"><b>Эта книга интереснее той?</b></div>",
                        "<div class=\"sentence\"><b>Он не выше своего брата.</b></div>",
                        "<div class=\"sentence\"><b>Это лучший фильм, который я видел.</b></div>"
                    ]'>
                    </div>
                </div>
            </div>
            <div class="button-container">
                <button class="card-button correct-button" onclick="markCard(this, true, 10)">
                </button>
                <button class="card-button incorrect-button" onclick="markCard(this, false, 10)">
                </button>
            </div>
        </div>

         <!-- Card 11 -->
        <div class="card-row">
            <div class="card" onclick="flipCard(this, 11)">
                <div class="card-inner">
                    <div class="card-front">
                        <div class="sentence" data-number="1"><b>She can play the piano.</b></div>
                        <div class="sentence" data-number="2"><b>Can they speak French?</b></div>
                        <div class="sentence" data-number="3"><b>I can’t swim.</b></div>
                        <div class="sentence" data-number="4"><b>We can go now.</b></div>
                    </div>
                    <div class="card-back" data-original-sentences='[
                        "<div class=\"sentence\"><b>Она умеет играть на пианино.</b></div>",
                        "<div class=\"sentence\"><b>Они могут говорить по-французски?</b></div>",
                        "<div class=\"sentence\"><b>Я не умею плавать</b></div>",
                        "<div class=\"sentence\"><b>Мы можем идти сейчас.</b></div>"
                    ]'>
                    </div>
                </div>
            </div>
            <div class="button-container">
                <button class="card-button correct-button" onclick="markCard(this, true, 11)">
                </button>
                <button class="card-button incorrect-button" onclick="markCard(this, false, 11)">
                </button>
            </div>
        </div>

        <!-- Card 12 -->
        <div class="card-row">
            <div class="card" onclick="flipCard(this, 12)">
                <div class="card-inner">
                    <div class="card-front">
                        <div class="sentence" data-number="1"><b>She could sing beautifully.</b></div>
                        <div class="sentence" data-number="2"><b>Could they help us?</b></div>
                        <div class="sentence" data-number="3"><b>I couldn’t run fast when I was young.</b></div>
                        <div class="sentence" data-number="4"><b>We could visit them tomorrow.</b></div>
                    </div>
                    <div class="card-back" data-original-sentences='[
                       "<div class=\"sentence\"><b>Она могла петь красиво.</b></div>",
                        "<div class=\"sentence\"><b>Они могли бы нам помочь?</b></div>",
                        "<div class=\"sentence\"><b>Я не мог быстро бегать, когда был молодым.</b></div>",
                        "<div class=\"sentence\"><b>Мы могли бы навестить их завтра.</b></div>"
                    ]'>
                     </div>
                </div>
            </div>
            <div class="button-container">
                <button class="card-button correct-button" onclick="markCard(this, true, 12)">
                </button>
                <button class="card-button incorrect-button" onclick="markCard(this, false, 12)">
                </button>
            </div>
        </div>
    </div>

    <script>
        function flipCard(card, cardIndex) {
            card.classList.toggle('flipped');
            const back = card.querySelector('.card-back');
            let sentences = JSON.parse(back.getAttribute('data-original-sentences'));

            if (card.classList.contains('flipped')) {
                sentences = shuffleArray(sentences.map(s => {
                    if (s && typeof s === 'string') {
                        return s.replace(/(<div class="sentence">)(.*)(<\/div>)/, '$1<b>$2</b>$3');
                    }
                    return s;
                }));
            }
            back.innerHTML = '';
            for (let i = 0; i < sentences.length; i++) {
                back.innerHTML += sentences[i];
            }
        }

        function shuffleArray(array) {
            const newArray = [...array];
            for (let i = newArray.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [newArray[i], newArray[j]] = [newArray[j], newArray[i]];
            }
            return newArray;
        }

        function markCard(button, isCorrect, cardIndex) {
            const buttonContainer = button.parentNode;
            const buttons = buttonContainer.querySelectorAll('.card-button');
            // Reset all button styles
            buttons.forEach(btn => {
                btn.classList.remove('active');
            });
            // Set styles for the button
            button.classList.add('active');
            console.log(`Card ${cardIndex} marked as ${isCorrect ? 'correct' : 'incorrect'}`);
        }
    </script>
</body>
</html>
