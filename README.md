# balck_jacklet sum = 0 ;
let cards = [];

console.log(cards);

 let hasBlackJack = false
 let isAlive = false
 let message = "";

let messageEl = document.getElementById('message-el');
let sumEl = document.getElementById("sum-el");
let cardEl = document.getElementById("card-el");

let player = {
name:Thiruna,
chips: 145
}


let payerEl = document.getElementById("player-el")
payerEl.textContent = player;

function getRandomCard() {
  let num = Math.floor(Math.random() * 13) + 1;
  if (num > 10) {
    return 10
 } else if (num === 1) {
    return 11
  }else {
    return num
  }
}


function startgame() {
isAlive = true;
let firstCard = getRandomCard();
let secondCard = getRandomCard()
cards = [firstCard,secondCard]
sum = firstCard + secondCard;
 rendergame();
}


function rendergame() {
  if (sum <= 20) {
    message = 'Do you want to draw a new card';
 
   } else if (sum === 21) {
    message = 'You got BlackJack';
    hasBlackJack = true;
  
   } else {
    message = 'Your out of the game';
    isAlive = false;
  }

 messageEl.textContent = message;
 cardEl.textContent = 'Card: '

for (let i = 0; i <cards.length; i++) {
   cardEl.textContent += cards[i] + " ";
}

 sumEl.textContent = 'Sum: ' + sum;

}

function newcard() {
if(isAlive === true && hasBlackJack === false) {
let card =  getRandomCard();
sum += card
cards.push(card);
console.log(cards); 
rendergame();
}

 }
