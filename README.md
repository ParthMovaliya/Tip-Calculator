# Frontend Mentor - Tip calculator app solution

This is a solution to the [Tip calculator app challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/tip-calculator-app-ugJNGbJUX). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
- [Author](#author)


## Overview

### The challenge
- Challange is to make Tip calculator using HTML,CSS,Js

Users should be able to:

- View the optimal layout for the app depending on their device's screen size
- See hover states for all interactive elements on the page
- Calculate the correct tip and total cost of the bill per person


Add a screenshot of your solution. The easiest way to do this is to use Firefox to view your project, right-click the page and select "Take a Screenshot". You can choose either a full-height screenshot or a cropped one based on how long the page is. If it's very long, it might be best to crop it.

Alternatively, you can use a tool like [FireShot](https://getfireshot.com/) to take the screenshot. FireShot has a free option, so you don't need to purchase it. 

Then crop/optimize/edit your image however you like, add it to your project, and update the file path in the image above.

**Note: Delete this note and the paragraphs above when you add your screenshot. If you prefer not to add a screenshot, feel free to remove this entire section.**

### Links

- Solution URL: (https://github.com/ParthMovaliya/Tip-Calculator)
- Live Site URL: (https://tip-calculator-one-omega.vercel.app/)

## My process
- I start my project by building HTML static website which look as similer as Given Design Website 
- After done this, i start work Css and start make website responsive
- after CSS part Done I simply Work on JS and My project is Done!!

### Built with

- Semantic HTML5 markup.
- CSS custom properties.
- Display flex and its properties.
- basic JS with document.getElementById,innerHTML,value,classList,hidden properties.

### What I learned
- use of display flex and its properties.
- basic Js properties and functions.


```html

<div class="main body">
    <div class="img_set">
      <img class="logo" src="images/logo.png" alt="">
    </div>
    <div class="container roundBig">
      <div class="left roundBig">
        <form action="post" class="flex_col">
          <label for="bill" class="txtLeft">Bill</label>
          <input type="number" name="" placeholder="0" id="bill" class="numRight round size">
          <label for="" class="txtLeft mtop">Select Tip %</label>
          <div class="flex_row " style="flex-wrap: wrap; justify-content: space-between;">
            <input type="button" value="5%" onclick="tipSelect(5)" class=" wid round size btn_bg">
            <input type="button" value="10%" onclick="tipSelect(10)" class=" wid marCen round size btn_bg">
            <input type="button" value="15%" onclick="tipSelect(15)" class=" wid round size btn_bg">
            <input type="button" value="25%" onclick="tipSelect(25)" class=" wid round size btn_bg">
            <input type="button" value="50%" onclick="tipSelect(50)" class=" wid marCen round size btn_bg">
            <input type="number" value="" id="custom" placeholder=" Custom " class="wid round size numRight btnCustom">
          </div>
          <div class="flex_space mtop">
            <label for="noOfPeople" class="txtLeft">Number of People</label>
            <label for="noOfPeople" class="txtLeft" id="cbz">Can't be Zero</label>
          </div>
          <input type="number" placeholder="0" id="nop" class="round numRight size">
        </form>
      </div>

      <div class="right roundBig">
        <!-- <div> -->
        <table class="tbl">
          <tr class="flex_space space">
            <td class="text_dark">
              <p class="text_light">Tip Amount</p> / person
            </td>
            <td>
              <p class="op" id="tipPerperson">$0.00</p>
            </td>
          </tr>
          <tr class="flex_space">
            <td class="text_dark">
              <p class="text_light">Total </p> / person
            </td>
            <td>
              <p class="op" id="bilPerPerson">$0.00</p>
            </td>
          </tr>
        </table>
        <!-- </div> -->
        <input type="button" class="round" id="rst" onclick="reset()" value="RESET">
      </div>
    </div>
  </div>

```

```css

@import url('https://fonts.googleapis.com/css2?family=Space+Mono:wght@700&display=swap');

    * {
      margin: 0px;
      padding: 0px;
      font-family: 'Space Mono';
      border: none;
    }

    .round {
      border-radius: 5px;
    }

    .roundBig {
      border-radius: 10px;
    }

    .wid {
      width: 30%;
      margin: 2% 0px;
      flex-wrap: wrap;
      height: 6vh;
    }

    .flex_col {
      display: flex;
      flex-direction: column;
    }

    .flex_row {
      display: flex;
      flex-direction: row;
    }

    .flex_space {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
    }

    .main {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background-color: hsl(185, 41%, 84%);
    }

    .logo {
      position: relative;
      bottom: 15%;
      margin-top: 10vh;
    }

    .size {
      font-size: 1.5rem;
    }

    .container {
      display: flex;
      flex-direction: row;
      padding: 2%;
      background-color: hsl(189, 41%, 97%);
    }

    .left {
      width: 30vw;
      margin: 10px;
    }

    .txtLeft{
      color: hsl(186, 14%, 43%);
      font-size: 0.9rem;
      padding-bottom: 1%;
    }

    .btnCustom{
      font-size: 1rem;
    }

    .mtop {
      margin-top: 8%;
    }

    .numRight {
      text-align: right;
    }

    #cbz{
      color: red;
    }

    .right {
      width: 25vw;
      background-color: hsl(183, 100%, 15%);
      margin: 10px;
      padding: 10px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }

    .op {
      font-size: 2.2rem;
      color: hsl(172, 67%, 45%);
      margin-block-start: -8%;
    }

    .tbl {
      width: 90%;
      margin: 5% auto;
    }

    .space {
      margin-bottom: 20px;
    }

    .text_light {
      color: hsl(189, 41%, 97%);
      font-size: 0.85rem;
    }

    .text_dark {
      color: hsl(184, 14%, 56%);
      font-size: 0.7rem
    }

    #rst {
      color: hsl(183, 100%, 15%);
      background-color: hsl(172, 67%, 45%);
      font-size: 20px;
      width: 90%;
      margin: 5% auto;
      height: 15%;
    }

    #rst:hover {
      background-color: hsl(185, 41%, 84%);
    }

    .btn_bg {
      background-color: hsl(183, 100%, 15%);
      color: hsl(185, 41%, 84%);
    }

    .btn_bg:hover {
      background-color: hsl(185, 41%, 84%);
      color: hsl(183, 100%, 15%);
    }
    .bred{
      border: 2px solid red;
    }

    @media (max-width: 376px) {
      .container {
        height: 100%;
        display: flex;
        flex-direction: column;
        flex-wrap: wrap;
        padding: 30px;
      }

      .left {
        width: 100%;
        margin: 0px;
      }

      .btnCustom {
        font-size: 1.5rem;
      }

      .right {
        width: 100%;
        margin: 7% 0px 0px 0px;
        padding: 2%;
        justify-content: center;
      }

      .wid {
        width: 47.5%;
      }

      .tbl {
        width: 90%;
        margin: 5% auto 7%;
      }
    }

```

```js

document.getElementById("custom").addEventListener('keypress',function(event){
      if(event.keyCode === 13){
        var y = document.getElementById("custom").value;
        tipSelect(y);
      }
    });

    document.getElementById("cbz").hidden = true;
    function tipSelect(x){
      var billVal = document.getElementById("bill").value;
      var noOfPeople = document.getElementById("nop").value;
      if(billVal == 0 ){
        alert("Enter Bill Value First")
      } else if(noOfPeople == 0){
        document.getElementById("cbz").hidden = false;
        document.getElementById("nop").classList.add("bred");
        // alert("Enter Number of people");
      }
      else{
        var ans = ((billVal*x)/100);
        document.getElementById("tipPerperson").innerHTML=ans;
        var total = (billVal/noOfPeople)+(ans/noOfPeople);
        document.getElementById("bilPerPerson").innerHTML=total;

      }
    }
    function reset(){
      document.getElementById("cbz").hidden = true;
      document.getElementById("nop").classList.remove("bred");
      document.getElementById("bill").value="";
      document.getElementById("nop").value="";
      document.getElementById("tipPerperson").innerHTML="0.00";
      document.getElementById("bilPerPerson").innerHTML="0.00";
      document.getElementById("custom").value="";
      // alert("Reset");
    }

```


### Continued development
- CSS display properties
- JS and jQuery 


## Author

- Frontend Mentor - [@ParthMovaliya](https://www.frontendmentor.io/profile/ParthMovaliya)
