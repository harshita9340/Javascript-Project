#Projects related to DOM


#Project link


[click here](https://stackblitz.com/edit/dom-project-chaiaurcode?file=1-colorChanger%2Findex.html)


#solution code

##project 1

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
##project 2

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
## project-3

```javascript

const clock=document.getElementById('clock')
//also use a queryselector
setInterval(function(){
let date=new Date();
//har moment pe run ho 
clock.innerHTML=date.toLocaleTimeString();
},1000)
```

