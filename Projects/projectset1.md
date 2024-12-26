#Projects related to DOM


#Project link


[click here](https://stackblitz.com/edit/dom-project-chaiaurcode?file=1-colorChanger%2Findex.html)


#solution code

##project-1 (COLOR CHANGER)

```javascript
console.log("project-1")
const buttons=document.querySelectorAll('.button')
const body=document.querySelector('body')
buttons.forEach(function(button){
  console.log(button);
button.addEventlistener('click',function(e){
if(e.targetgrey.id==='grey'){
  body.style.backgroundcolor=e.target.id;
}
if(e.targetgrey.id==='white'){
  body.style.backgroundcolor=e.target.id;
}
if(e.targetgrey.id==='blue'){
  body.style.backgroundcolor=e.target.id;
}
if(e.targetgrey.id==='yellow'){
  body.style.backgroundcolor=e.target.id;
}


});

});
```
##project 2 (BMI CALCULATOR)

```javascript
const form =document.querySelector('form');
//this usecase will give you empty
//const height=parseInt(document.queryselector('#height').value) 
form.addEventListener('submit',function(e){
  e.preventDefault();
  const height=parseInt(document.querySelector('#height').value)   /*convert string to integer*/
  const weight=parseInt(document.querySelector('#weight').value)
  const results=document.querySelector('#results')
  if(height===''||height<0||isNaN(height)){
    results.innerHTML=`please give a valid height ${height}`;
  }
  else if(weight===''||weight<0||isNaN(weight)){
    results.innerHTML=`please give a valid weight ${weight}`;
  }else{
   const bmi= (weight/((height*height)/10000)).toFixed(2)
   //show the result
   results.innerHTML=`<span>${bmi}</span>`
  }

});

```
## project-3 DIGITAL CLOCK

```javascript

const clock=document.getElementById('clock')
//also use a queryselector
setInterval(function(){
let date=new Date();
//har moment pe run ho 
clock.innerHTML=date.toLocaleTimeString();
},1000)
```
## project-4 NUMBER GUESS

```javascript 


let randomNumber = parseInt(Math.random() * 100 + 1);

const submit = document.querySelector('#subt');
const userInput = document.querySelector('#guessField');
const guessSlot = document.querySelector('.guesses');
const remaining = document.querySelector('.lastResult');
const lowOrHi = document.querySelector('.lowOrHi');
const startOver = document.querySelector('.resultParas');

const p = document.createElement('p');

let prevGuess = [];
let numGuess = 1;

let playGame = true;

if (playGame) {
  submit.addEventListener('click', function (e) {
    e.preventDefault();
    const guess = parseInt(userInput.value);
    console.log(guess);
    validateGuess(guess);
  });
}

function validateGuess(guess) {
  if (isNaN(guess)) {
    alert('PLease enter a valid number');
  } else if (guess < 1) {
    alert('PLease enter a number more than 1');
  } else if (guess > 100) {
    alert('PLease enter a  number less than 100');
  } else {
    prevGuess.push(guess);
    if (numGuess === 11) {
      displayGuess(guess);
      displayMessage(`Game Over. Random number was ${randomNumber}`);
      endGame();
    } else {
      displayGuess(guess);
      checkGuess(guess);
    }
  }
}

function checkGuess(guess) {
  if (guess === randomNumber) {
    displayMessage(`You guessed it right`);
    endGame();
  } else if (guess < randomNumber) {
    displayMessage(`Number is TOOO low`);
  } else if (guess > randomNumber) {
    displayMessage(`Number is TOOO High`);
  }
}

function displayGuess(guess) {
  userInput.value = '';
  guessSlot.innerHTML += `${guess}, `;
  numGuess++;
  remaining.innerHTML = `${11 - numGuess} `;
}

function displayMessage(message) {
  lowOrHi.innerHTML = `<h2>${message}</h2>`;
}

function endGame() {
  userInput.value = '';
  userInput.setAttribute('disabled', '');
  p.classList.add('button');
  p.innerHTML = `<h2 id="newGame">Start new Game</h2>`;
  startOver.appendChild(p);
  playGame = false;
  newGame();
}

function newGame() {
  const newGameButton = document.querySelector('#newGame');
  newGameButton.addEventListener('click', function (e) {
    randomNumber = parseInt(Math.random() * 100 + 1);
    prevGuess = [];
    numGuess = 1;
    guessSlot.innerHTML = '';
    remaining.innerHTML = `${11 - numGuess} `;
    userInput.removeAttribute('disabled');
    startOver.removeChild(p);

    playGame = true;
  });
}
```
##project-5(keypress)

```javascript

const insert=document.getElementById('insert')
window.addEventListener('keydown',(e)=>{
  insert.innerHTML=`
  <div class='color'>
  <table>
  <tr>
    <th>key</th>
    <th>Keycode</th>
    <th>Code</th>
  </tr>
  <tr>
    <td>${e.key===" "?"space":e.key}</td>
    <td>${e.keycode}</td>
    <td>${e.code}</td>
  </tr>h
</table>

  </div>
  `
})
```
##project-6(BackgroundChanger)

```javascript

//generate a random color
const randomColor = function(){
  const hex="0123456789ABCDEF"
  let color='#'
  for(let i=0;i<6;i++){
    color+=hex[Math.floor(Math.random()*16)];
  }
  return color;
}
let interval;
const startChangingColor=function(){
  if(!interval){
   interval=setInterval(changebg,1000)
  }
  function changebg(){
    document.body.style.backgroundColor=randomColor();
  }
}
const stopChangingColor=function(){
clearInterval(interval)
interval=null;
}
document.querySelector('#start').addEventListener('click',startChangingColor)
document.querySelector('#stop').addEventListener('click',stopChangingColor)
```
