<html>
<head>
	<title>Javascript Demo</title>
	<style>
		body {
			background-color:black;
			font-family: monospace;
			color:white;
			font-size:50px;
			text-align: center;
			margin-top:20%;
		}

		#magic{
			color: #777;
			border-right: 1px solid #777;
			/*padding-right: 7px;*/
			display: inline;
		}
	</style>
</head>
<body>

	Coding is <div id="magic"></div>

	<script>

		( function() {

			var words = ["fun", "exciting", "about not giving up", "being helpful", "being open", "what I learned at CodingDojo!"],
				el = document.getElementById('magic'),
				word_counter = 0,
				character_counter = 0;
				next_char = '';

			function updateText()
			{

				if(character_counter == (words[word_counter].length))
				{
					console.log('next word');
					word_counter++; 	//choose a different word
					character_counter = 0;	//start over with the first character of the word
					el.innerHTML = '';  //set the html to be blank

					//if we're displaying the last word, go back to the first word
					if(word_counter == words.length)
						word_counter = 0;
				}

				next_char = words[word_counter][character_counter++];
				if (next_char ===' ')
					next_char =  '&nbsp';
				el.innerHTML = el.innerHTML+next_char;

			}

			setInterval(updateText,300);

		} ) ();

		console.log('word count'+word_counter);


	</script>

</body>

</html>