# Simple-ChatPage
A Simple ChatPage


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
<style>

 html{
     background-color: cornflowerblue;
 }

 .middle{
    margin-top: 15px;
    margin-bottom: 15px;
    margin-left: 450px;

 }  
.textarea{
    width:30%;
    height:50px;
    margin-left: 450px;
}

.chat{
    margin-top: 15px;
    margin-bottom: 15px;
    margin-left: 450px;
    display: block;
}

#chat-wrap{
    margin-top: 15px;
    margin-bottom: 15px;
    margin-left: 450px;
    border: 2px solid black;
    width:30%;
    height: 250px;
    background-color:white;
}   

.red{
   color: red; 
}

.blue{
    color: blue;
}
</style>
<script>
    var input_array=[];

        
    
    function addArray(){
    
       var sender= document.getElementById("userwho").value;
       var message = document.getElementById("message").value;
        
        if(sender =="" || message ==""){
            alert("cannot be empty...")
        }
        
        var obj = {"user" : sender , "message" : message}
        input_array.push(obj)
        iterateArray();
        document.getElementById("userwho").value="";
        document.getElementById("message").value=""
       
    }
    
    function iterateArray(){
        var s ="--->"
        var temp="";
        for(i in input_array){
            if(i%2==0){
                temp+="<div><span class='red'>"+input_array[i].user+"</span> <span>"+s+"</span>  <span class='blue'>"+input_array[i].message+"</span></div>"
            }
            else{
                temp+="<div><span class='blue'>"+input_array[i].user+"</span> <span>"+s+"</span>  <span class='red'>"+input_array[i].message+"</span></div>"
            }

        }         
        document.getElementById("chat-wrap").innerHTML=temp;
    
    }
    function place(){
        const selected1 = document.getElementById("check1").value;
        const selected2 = document.getElementById("check2").value;

        var obj=[]
        var status={"box1":selected1, "box2":selected2}

   

        if(status.box1 == "selected-chennai"){
            console.log("user has selected chennai")
        }

        else if(status.box2 =="selected-madurai"){
            console.log("user has selected madurai")
        }

        obj.push(status);

        console.log(status);
        
    }
</script>
</head>

<body>


 <div id="chat-wrap"></div>   
<input type="text" id="userwho" placeholder="Who ?" class="chat">

<div>
    <textarea id="message"  class="textarea" cols="30" rows="10" placeholder="Message"></textarea>
    </div>

<input type="button" onclick="addArray()" value="Send" class="chat">




</body>
</html>
