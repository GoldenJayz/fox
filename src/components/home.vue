<template>
  <div id="a">
      <p id="uptime">
          Website is down!
      </p>
  </div>
</template>

<script>
    var oXHR = new XMLHttpRequest();


    oXHR.onreadystatechange = reportStatus;
    oXHR.open("GET", "https://jadend.xyz/", true);
    oXHR.send();



    function reportStatus() {
        if (oXHR.readyState == 4) {		
            document.getElementById('uptime').innerHTML = "Website is up!";
            document.getElementById("uptime").style.color = "green";
        } else {
            document.getElementById('uptime').innerHTML = "Website is down!";
            document.getElementById("uptime").style.color = "red";
        }
    }
</script>

<style>

</style>