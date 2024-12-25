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