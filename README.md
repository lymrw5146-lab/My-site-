# My-site-
<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Vibration Site</title>

<style>
body{
    margin:0;
    background:black;
    color:white;
    font-family:Arial;
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
    flex-direction:column;
}

h1{
    font-size:40px;
    animation: shake 0.05s infinite;
}

button{
    padding:15px 30px;
    font-size:18px;
    border:none;
    background:red;
    color:white;
    cursor:pointer;
    margin-top:20px;
}

@keyframes shake{
    0%{transform:translate(2px,1px)}
    25%{transform:translate(-2px,-1px)}
    50%{transform:translate(2px,-2px)}
    75%{transform:translate(-1px,2px)}
    100%{transform:translate(1px,-1px)}
}
</style>
</head>

<body>

<h1>SYSTEM ACTIVE</h1>

<button onclick="startVibration()">
START 15 MIN
</button>

<script>
function startVibration(){

    const pattern = [
        200, 30,
        200, 30,
        400, 40,
        600, 50
    ];

    const interval = setInterval(() => {
        navigator.vibrate(pattern);
    }, 1330);

    // 15 دقيقة = 900000 ms
    setTimeout(() => {
        clearInterval(interval);
        navigator.vibrate(0);
    }, 15 * 60 * 1000);
}
</script>

</body>
</html>
