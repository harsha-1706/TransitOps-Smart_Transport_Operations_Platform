# First-Project
<!DOCTYPE html>
<html>

<head>

<title>TransitOps Login</title>

<style>

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:'Segoe UI',sans-serif;
}


body{

    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;

    background:
    linear-gradient(135deg,#0f2027,#203a43,#2c5364);

}



.login-box{

    width:380px;

    padding:35px;

    background:rgba(255,255,255,0.15);

    backdrop-filter:blur(15px);

    border-radius:20px;

    color:white;

    box-shadow:0 20px 50px black;

}



.logo{

    text-align:center;

    margin-bottom:25px;

}



.logo h1{

    color:#00ffcc;
    font-size:32px;

}



.logo p{

    color:#ddd;

}



label{

    display:block;

    margin-top:15px;

    font-weight:bold;

}



input{

    width:100%;

    padding:12px;

    margin-top:8px;

    border-radius:10px;

    border:none;

    outline:none;

}



.captcha{

    margin-top:15px;

    padding:15px;

    background:#111;

    text-align:center;

    font-size:25px;

    letter-spacing:5px;

    color:#00ffcc;

    border-radius:10px;

}



button{

    width:100%;

    margin-top:25px;

    padding:14px;

    border:none;

    border-radius:30px;

    background:#00ffcc;

    color:#003333;

    font-size:17px;

    font-weight:bold;

    cursor:pointer;

}



button:hover{

    transform:scale(1.05);

}



.message{

    margin-top:15px;

    text-align:center;

    font-weight:bold;

}



</style>


</head>



<body>



<div class="login-box">


<div class="logo">

<h1>🚍 TransitOps</h1>

<p>Smart Transport Operations</p>

</div>




<label>
Username
</label>

<input id="username"
placeholder="Enter username">



<label>
Password
</label>

<input id="password"
type="password"
placeholder="Enter password">



<label>
Security Verification
</label>


<div class="captcha" id="captcha">

</div>


<input id="captchaInput"
placeholder="Enter CAPTCHA">



<button onclick="login()">

Login

</button>



<div class="message" id="message">

</div>



</div>





<script>


let num1;
let num2;



function generateCaptcha(){


num1=Math.floor(Math.random()*9)+1;

num2=Math.floor(Math.random()*9)+1;


document.getElementById("captcha")
.innerHTML =
num1+" + "+num2+" = ?";


}



generateCaptcha();





function login(){


let user=
document.getElementById("username").value;


let pass=
document.getElementById("password").value;



let captchaAnswer=
document.getElementById("captchaInput").value;



if(user=="" || pass==""){

showMessage("Enter username and password","red");

return;

}



if(Number(captchaAnswer)!=(num1+num2)){


showMessage(
"Incorrect CAPTCHA ❌",
"red"
);


generateCaptcha();


return;

}



// Demo login credentials

if(user=="admin" && pass=="12345"){


showMessage(
"Login Successful ✅",
"#00ff99"
);


// redirect demo

setTimeout(()=>{

window.location.href="dashboard.html";

},1500);



}


else{


showMessage(
"Invalid Login Details ❌",
"red"
);


}



}



function showMessage(text,color){

let msg=
document.getElementById("message");


msg.innerHTML=text;

msg.style.color=color;


}



</script>



</body>

</html>
