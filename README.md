
<html>
<head>
	<meta charset="utf-8">
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<title>Calculator</title>
	<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.4/jquery.min.js"></script>

	<style type="text/css">
		
	*{
	margin: 10;
	padding: 2px;
	box-sizing: border-box;
	background-color:red;
	font-family: initial;
	outline: none;
}

h1{
	text-align: center;
	font-size: 40px;
	font-style: italic;
	text-weight: 200;
	text-decoration: underline;
	color: white;
	font-family:serif;
	
}

.container{
    padding-bottom: 170px;
	height: 100vh;
	display: flex;
	justify-content: center;            
	align-items: center;         
}

.Calculator{

	background: linear-gradient(yellow,black,green);
	padding: 15px;
	border-radius: 30px;
	box-shadow: inset 5px 5px 12px #ffffff,    
	                  5px 5px 12px rgba(0, 0, 0, .16);
	display: grid;
	grid-template-columns: repeat(4, 68px)
}

input{

	grid-column: span 4;
	height: 70px;
	width: 265px;
	background-color:black;
	box-shadow: inset -5px -5px 12px #ffffff, 
	            inset 5px 5px 12px rgba(0, 0, 0, .16);
	border: 1px solid black;
	border-radius: 30px;
	color: rgb(80, 70, 90);
	font-size: 28px;
	text-align: right;
	margin: auto;
	margin-top: 40px;
	margin-bottom: 30px;
	padding: 20px;
	cursor: text;
}

#off{

    width: 60px;
	background-color: black;
	color: black;
	border-radius: 15px;
	font-size: 18px;
	font-style: italic;
	cursor: pointer;
}

#on{

	width: 60px;
	background-color: black;
	color: black;
	border: 1px soldi #b2b0b0;
	border-radius: 15px;
	font-size: 18px;
	font-style: italic;
	padding: 5px;
	float: right;

}

button{

	height: 50px;
	width: 50px;
	background-color: #ecf0f3;
	box-shadow: -5px -5px 12px white,     
	             5px 5px 12px rgba(0, 0, 0, 0.16);
	border: none;
	border-radius: 50px;
	margin: 10px;
	font-size: 17px;
	cursor: pointer;
}

.equal{

	width: 250px;
	border-radius: 40px;
	background-color: black;
	color: black;
	box-shadow: -5px -5px 12px white,     
	             5px 5px 12px rgba(0, 0, 0, 0.16);
	cursor: pointer;             
}
	</style>

</head>
<body>

	<h1>My Calculator</h1>

	
     
	<div class="container">
		<div class="Calculator">
			<input type="text" placeholder="0" id="output-screen">
			<button id="off" onclick="s_off()" style="color:white" >OFF</button>
			<button onclick="Clear()">C</button>
			<button onclick="del()">DEL</button>
			<button id="on" onclick="s_on()" style="color: white;" >ON</button>
			<button onclick="display('%')">%</button>
			<button onclick="display('/')">/</button>
			<button onclick="display('+')">+</button>
			<button onclick="display('*')">*</button>
			<button onclick="display('-')">-</button>
			<button onclick="display('+/-')">+/-</button>
			<button onclick="display('1')">1</button>
			<button onclick="display('2')">2</button>
			<button onclick="display('3')">3</button>
			<button onclick="display('4')">4</button>
			<button onclick="display('5')">5</button>
			<button onclick="display('6')">6</button>
			<button onclick="display('7')">7</button>
			<button onclick="display('8')">8</button>
			<button onclick="display('9')">9</button>
			<button onclick="display('0')">0</button>
			<button style="color:white;" onclick="Calculate()" class="equal">=</button>
		</div>
	</div>


	<script>
		let outputScreen = document.getElementById("output-screen");

		function display(num) {
			
			outputScreen.value += num;
		}

		function Calculate(){
			try{
				outputScreen.value = eval(outputScreen.value)
			}
			catch(err){
				alert("Invalid Value")
			}
		}

		function Clear(){
			outputScreen.value = "";
		}

		function del(){
			outputScreen.value = outputScreen.value.slice(0,-1);
		}

		function s_off() {

			("#output-screen").empty();
			document.getElementById("output-screen").style.background="#636361";
			document.getElementById("output-screen").style.border="1px solid #636361";
		        ('button').prop('disabled', true);
		}

</script>




</body>
</html>
