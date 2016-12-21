# JSBin-look-alike-
This is some code that replicates the functionality of JSBin - a website that is very popular amongst web developers. Feel free to edit this code to have the program run however you like! I will let you know that the 'RUN' button does not work, as that would require a eval command which would expose my servers. So I'll let you copy the code and write your own code to have the 'RUN' button function. 



<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>JSBin look-alike</title>
  <!--script type="text/javascript" src="jquery.min.js"></script-->
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.min.js"></script>
  
  <script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/jqueryui/1.12.1/jquery-ui.min.js"></script>
  
 	<style>
 		body {
 			margin:0;
 			padding:0;
 			font-family:Helvetica;
 		}
 		
 		#menuBar {
 			width:100%;
 			height:40px;
 			background-color:#e0e0e0;
 			border-bottom:1px solid grey;
 		}

		#logo {
			padding:10px 0 0 20px;
			font-weight:bold;
			font-size:120%;
			float:left;
			
		}
		
		#buttonDiv {
			float:right;
			padding:5px 10px 0 0;
		}
		
		#runButton {
			font-size:120%;
		}
		
		#toggles {
			width:200px;
			margin:0 auto;
			list-style:none;
			border:1px solid grey;
			border-radius:3px;
			height:27px;
			padding:0;
			position:relative;
			top:5px;
		}
		
		#toggles li {
			float:left;
			border-right:1px solid grey;
			padding:5px 7px;
		}
		
		.clear {
			clear:both;
		}
		
		.codeContainer {
			height:100%;
			width:50%;
			float:left;
			position:relative;
		}
		
		.codeContainer textarea {
			width:100%;
			height:100%;
			border:none;
			border-right:1px solid grey;
			box-sizing:border-box;
			font-family:monotype;
			font-size:90%;
			padding:5px;
		}
		
		.codeLabel {
			position:absolute;
			right:10px;
			top:10px;
		}
		
		#CSSContainer, #JSContainer {
			display:none;
		}
		
		iframe {
			height:100%;
			position:relative;
			left:20px;
			border:none;
		}
		
		.selected {
			background-color:grey;
		}
	</style>

</head>
	
<body>
	<div id="wrapper">		
		<div id="menuBar">
		
			<div id="logo">
				Code Player
			</div>
			
			<div id="buttonDiv">
			
				<button id="runButton">Run</button>
			
			</div>
			
			<ul id="toggles">
				<li class="toggle selected">HTML</li>
				<li class="toggle">CSS</li>
				<li class="toggle">JS</li>
				<li class="toggle selected" style="border:none">Result</li>				
			</ul>
			
		</div>
		
		<div class="clear"</div>
	
		<div class="codeContainer" id="HTMLContainer">
			
			<div class="codeLabel">Example</div>
			
			<textarea id="htmlCode"></textarea>
		
		</div>
		
		<div class="codeContainer" id="CSSContainer">
			
			<div class="codeLabel">CSS</div>
			
			<textarea id="cssCode">Example</textarea>
		
		</div>
		
		<div class="codeContainer" id="JSContainer">
			
			<div class="codeLabel">JS</div>
			
			<textarea id="jsCode">Example</textarea>
		
		</div>
		
		<div class="codeContainer" id="ResultContainer">
			
			<div class="codeLabel">Result</div>
			
			<iframe id="resultFrame"></iframe>
		
		</div>
		
	</div>	

   	 <script>
		
		var windowHeight=$(window).height();
		var menuBarHeight=$("#menuBar").height();
		
		var codeContainerHeight=windowHeight-menuBarHeight;
		
		$(".codeContainer").height(codeContainerHeight+"px");
		
		$(".toggle").click(function() {
			
			$(this).toggleClass("selected");
			
			var activeDiv=$(this).html();
			
			$("#"+activeDiv+"Container").toggle();
			
			var showingDivs=$(".codeContainer").filter(function() {
				
				return($(this).css("display")!="none");
				
			}).length;
			
			var width=100/showingDivs;
			
			$(".codeContainer").width(width+"%");
			
		});
		
		
	
	</script>


</body>

</html>
