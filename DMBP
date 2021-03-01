// ==UserScript==
// @name         Dynamic Mouse Button Programmer
// @namespace    http://tampermonkey.net/
// @version      1.0
// @description  Add functions to mouse buttons, give them different abilities based on site.
// @author       GSRHackZ
// @match        *://*/*
// @grant        none
// @icon         https://www.flaticon.com/svg/3577/3577165.svg
// ==/UserScript==

let which,func,configuring=false;;

window.addEventListener("keyup",function(evt){
    if(evt.ctrlKey&&evt.altKey&&evt.keyCode==77){
        configuring=true;
        alert("Click anywhere on the screen using the button you want programmed!");
        window.addEventListener("mousedown",function(evt){
            if(which==undefined){
                which=evt.which;
                let ask=prompt(`Button Has Been Set! Type in function you would lke activated when button clicked... ⌨`);
                if(ask.trim().length>0){
                    func=ask;
                    localStorage.setItem(which,func);
                    localStorage.setItem("dmbp",true);
                    if(func!=="none"){
                        alert("Function has been set succesfully! 😊");
                    }
                    else{
                        alert("Button has been reset, click alt + M to set a function to it again. ⚠")
                    }
                }
                else{
                    alert("Please refresh and try again, there was no input...? 🤔");
                }
                configuring=false;
            }
        })
    }
})


if(localStorage.getItem("dmbp")!==null){
    window.addEventListener("mousedown",function(evt){
        if(configuring==false){
            if(localStorage.getItem(evt.which)!==null){
                if(localStorage.getItem(evt.which)!=="none"){
                    eval(localStorage.getItem(evt.which));
                }
                else{
                    localStorage.removeItem(evt.which);
                }
            }
        }
    })
}



//example functions....

function searchSel(){
    let param = window.getSelection().toString();
    if(param!==""){
        window.open(`https://www.google.com/search?q=${param}`);
    }
}

function duplicate(){
    window.open(location.href);
}

//add more functions below..... 😊
