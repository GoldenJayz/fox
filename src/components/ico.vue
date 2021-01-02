<template>
    <div class="container">
        <div class="card">
            <div class="face face1">
                <div class="content">
                    <img src="https://styles.redditmedia.com/t5_s1ps3/styles/profileIcon_jl68l7vd5fu31.png?width=256&height=256&crop=256:256,smart&frame=1&s=5d188748600ea24bb0bdf2e900b6a5909f16ed5e">
                    <h3>jadend.xyz</h3>
                </div>
            </div>
            <div class="face face2">
                <div class="content" id="uptime">
                    <p>Website is down!</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    var oXHR = new XMLHttpRequest();


    oXHR.onreadystatechange = reportStatus;
    oXHR.open("GET", "https://jadend.xyz/", true);
    oXHR.send();



    function reportStatus() {
        if (oXHR.readyState == 4) {		
            document.getElementById('uptime').innerHTML = "Website is up! 👍";
            document.getElementById("uptime").style.color = "green";
        } else {
            document.getElementById('uptime').innerHTML = "Website is down! 😢";
            document.getElementById("uptime").style.color = "red";
        }
    }
    //create an api that generates uptime then get it and display it here!
</script>

<style scoped>
.container {
    position: relative;
    width: 1000px;
    display: flex;
    justify-content: space-between;
    margin-left: 35%;
}

.container .card{
    position: relative;
    cursor: pointer;
}

.container .card .face{
    width: 300px;
    height: 200px;
    transition: 0.5s;
}

.container .card .face.face1{
    position: relative;
    background: rgb(68, 68, 68);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1;
    transform: translateY(100px);
}

.container .card:hover .face.face1{
    background: #ff0057;
    transform: translateY(0);
}

.container .card .face.face1 .content{
    opacity: 0.2;
    transition: 0.5s;
}

.container .card:hover .face.face1 .content{
    opacity: 1;
}

.container .card .face.face1 .content img{
    max-width: 100px;
}

.container .card .face.face1 .content h3{
    padding: 0;
    color: #fff;
    text-align: center;
    font-size: 1.5em;
}

.container .card .face.face2{
    background: #fff;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 20px;
    box-sizing: border-box;
    box-shadow: 0 20px 50px rgba(0, 0, 0, 0.8);
    transform: translateY(-100px);
}

.container .card:hover .face.face2{
    transform: translateY(0);
}

.container .card .face.face2 .content p{
    padding: 0;
}

.container .card .face.face2 .content a{
    display:  inline-block;
    text-decoration: none;
    font-weight: 900;
    color: rgb(255, 255, 255);
    padding: 5px;
    border: 1px solid #333;
}

.container .card .face.face2 .content a:hover{
    background: #333;
    color: #fff;
}

@import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');
#uptime {
    font-family: 'Roboto', sans-serif;
    font-size: 25px;
}
</style>