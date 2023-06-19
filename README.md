<!DOCTYPE html>
<html>
    <head>
        <title>Calculator</title>
        <style>
                body{
                    margin: 100px;
                    background-color:black;
                    height: 70vh;
                }
                .screen{
                    margin: 50px;
                    width: 350px;
                    max-height: 500px;
                    padding:2%;
                    text-align: center;
                    font-size:30px;
                    background-color: aliceblue;
                }
                .row{
                    margin-top: 20px;
                    display: flex;
                    justify-content: space-evenly;
                    max-width: 500px;
                    height: 13vh;
                }
                button{
                    border-style: none;
                    border-radius: 50%;
                    padding: 20px;
                    
                }
                button:hover{
                    background-color: aquamarine;
                    cursor: pointer;
                }
                .equ,.add,.minus,.mul,.div{
                    background-color: yellowgreen;
                }
        </style>
    </head>
    <body>
        <input class="screen" placeholder="0" id="screen">0</input>
        <div class="row">
            <div class="col"><button onClick="display('7')">7</button></div>
            <div class="col"><button onclick="display('8')">8</button></div>
            <div class="col"><button onclick="display('9')">9</button></div>
            <div class="col"><button id="div" onclick="display('/')">/</button></div>
        </div>
        <div class="row">
            <div class="col"><button onclick="display('4')">4</button></div>
            <div class="col"><button onclick="display('5')">5</button></div>
            <div class="col"><button onclick="display('6')">6</button></div>
            <div class="col"><button class="mul" id="mul" onclick="display('*')">*</button></div>
        </div>
        <div class="row">
            <div class="col"><button onclick="display('1')">1</button></div>
            <div class="col"><button onclick="display('2')">2</button></div>
            <div class="col"><button onclick="display('3')">3</button></div>
            <div class="col"><button class="minus" id="minus" onclick="display('-')">-</button></div>
        </div>
        <div class="row">
            <div class="col"><button onclick="display('0')">0</button></div>
            <div class="col"><button onclick="Clear()">AC</button></div>
            <div class="col"><button class="add" id="add" onclick="display('+')">+</button></div>
            <div class="col"><button class="equ" id="equal" onclick="Calculate()">=</button></div>
        </div>
        <script>
            let outputScreen="";
            function display(num){
                outputScreen+=num;
                document.getElementById("screen").value=outputScreen;
            }
            function Calculate(){
                try{
                    outputScreen=eval(outputScreen);
                    document.getElementById("screen").value=outputScreen;
                    
                }catch(err){
                    alert("Invalid");
                }
            }
            function Clear(){
                outputScreen="";
                document.getElementById("screen").value=outputScreen;
            }
        </script>
       </body>
</html>
