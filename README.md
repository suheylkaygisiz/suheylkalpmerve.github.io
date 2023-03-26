<!DOCTYPE html>
<html>
<head>
	<title>Flashback Uygulaması</title>
	<style>
		body {
			background-color: black;
			color: white;
			font-size: 32px;
			text-align: center;
			padding-top: 20%;
		}

		#flashback {
			display: none;
		}

		#heart {
			position: absolute;
			top: 50%;
			left: 50%;
			transform: translate(-50%, -50%);
			width: 100px;
			height: 100px;
			background-image: url("https://i.imgur.com/cIbIZ0F.png"); /* Kalp şekli */
			background-repeat: no-repeat;
			background-size: contain;
			cursor: pointer;
		}
	</style>
</head>
<body>
	<div id="heart"></div>
	<p id="flashback"></p>
	<script>
		var words = "Bu bir flashback uygulamasıdır.";
		var wordArray = words.split(" ");
		var i = 0;
		var speed = 1000; // kelime hızı

		document.getElementById("heart").addEventListener("click", function(){
			document.getElementById("heart").style.display = "none"; // kalbi gizle
			document.getElementById("flashback").style.display = "block"; // flashbacki göster
			startFlashback();
		});

		function startFlashback() {
			var timer = setInterval(function(){
				document.getElementById("flashback").innerHTML = wordArray[i];
				i++;
				if(i == wordArray.length){
					clearInterval(timer);
					setTimeout(function(){
						i = 0;
						document.getElementById("flashback").style.display = "none"; // flashbacki gizle
						document.getElementById("heart").style.display = "block"; // kalbi göster
					}, 3000); // 3 saniye bekle
				}
			}, speed);
		}
	</script>
</body>
</html>
