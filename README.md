<!DOCTYPE html>
<html>
<head>
<title>AashHub</title>

<style>
body{
    font-family: Arial, sans-serif;
    margin:0;
    background:url('https://images.unsplash.com/photo-1506744038136-46273834b3fb') no-repeat center center/cover;
}

header{
    background:rgba(0,0,0,0.7);
    color:white;
    padding:15px;
    text-align:center;
}

nav{
    background:#222;
    text-align:center;
    padding:10px;
}

nav a{
    color:white;
    text-decoration:none;
    margin:15px;
    font-weight:bold;
}

.container{
    background:rgba(255,255,255,0.9);
    width:90%;
    max-width:500px;
    margin:20px auto;
    padding:20px;
    border-radius:15px;
    text-align:center;
}

.profile{
    width:120px;
    height:120px;
    border-radius:50%;
    object-fit:cover;
}

button{
    background:#28a745;
    color:white;
    border:none;
    padding:10px 20px;
    border-radius:8px;
    cursor:pointer;
}

button:hover{
    background:#218838;
}
</style>
</head>

<body>

<header>
<h1>AashHub App</h1>
</header>

<nav>
<a href="#">Home</a>
<a href="#">Upload</a>
<a href="#">Profile</a>
<a href="#">Contact</a>
</nav>

<div class="container">

<h2>Welcome to AashHub</h2>

<img src="https://via.placeholder.com/120"
class="profile" id="preview">

<br><br>

<input type="file" id="fileInput" accept="image/*">

<h3>Your Profile Picture</h3>

<p>Upload your photo and it will appear above.</p>

<button onclick="showMessage()">Click Me</button>

<p id="msg"></p>

</div>

<script>
function showMessage(){
    document.getElementById("msg").innerHTML =
    "Welcome to AashHub!";
}

document.getElementById("fileInput").addEventListener("change", function(e){
    let file = e.target.files[0];

    if(file){
        let reader = new FileReader();

        reader.onload = function(event){
            document.getElementById("preview").src =
            event.target.result;
        }

        reader.readAsDataURL(file);
    }
});
</script>

</body>
</html>
