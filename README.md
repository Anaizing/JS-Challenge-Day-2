# JS-Challenge-Day-2
Its a clock
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>JS DAY2 Clock</title>
	<link rel="stylesheet" type="text/css" href="style.css">

	<script src="script.js"></script>
</head>
<body>
	<div class="boss">
		<div class="clock-face">
			<div id="hour" class=" hour-hand"></div>
			<div class="hand minute-hand"></div>
			<div class="hand second-hand"></div>
		</div>
	</div>
</body>
</html>

<style>
html {
	background-image: url("clock.jpg");
	background-size: cover;
	font-family: 'Helvetica';
	text-align: center;
	font-size: 10px;
}

body {
	margin: 0;
	font-size: ;
	display: flex;
	flex: 1;
	min-height: 100vh;
	align-items: center;
}

.boss{
	
	width: 30rem;
    height: 30rem;
    border:20px solid black;
    border-radius:50%;
    margin:50px auto;
    position: relative;
    padding:2rem;
    box-shadow:
      0 0 0 4px rgba(0,0,0,0.1),
      inset 0 0 0 3px #EFEFEF,
      inset 0 0 10px black,
      0 0 10px rgba(0,0,0,0.2);
}



.hand {
	width:50%;
	height: 15px;
	background: black;
	position: absolute;
	top: 50%;
	transform-origin: 100%;
	transform: rotate(90deg);
	transition: all 0.05s;
	transition-timing-function: cubic-bezier(0.1, 2.7, 0.58, 1);
}

#hour{
	width: 25%;
	height: 15px;
	background: black;
	position: absolute;
	top: 50%;
	transform-origin: 155% 120%;
	transform: rotate(90deg);
	transition: all 0.05s;
	transition-timing-function: cubic-bezier(0.1, 2.7, 0.58, 1);
}

.clock-face {
	position: relative;
    width: 100%;
    height: 100%;
    transform: translateY(-3px); /* account for the height of the clock hands */
}

</style>

<script>

function setDate() {

	const secondHand = document.querySelector('.second-hand');
	const minuteHand = document.querySelector('.minute-hand');
	const hourHand = document.querySelector('.hour-hand');

	const now = new Date();

	const seconds = now.getSeconds();
	const secondsDegrees = ((seconds / 60) * 360) + 90;
	secondHand.style.transform = `rotate(${secondsDegrees}deg)`;

	const minutes = now.getMinutes();
	const minutesDegrees = ((minutes / 60) * 360) + 90;
	minuteHand.style.transform = `rotate(${minutesDegrees}deg)`;

	const hours = now.getHours();
	const hoursDegrees = ((hours / 12) * 360) + 90;
	hourHand.style.transform = `rotate(${hoursDegrees}deg)`;



	console.log(hours);
}

setInterval(setDate, 1000);

</script>
