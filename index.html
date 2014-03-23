<!DOCTYPE html>
<html>
<head>
<script src="//ajax.googleapis.com/ajax/libs/jquery/1.11.0/jquery.min.js"></script>
<script src="http://cdn.peerjs.com/0.3/peer.js"></script>
<script src="bootstrap-modal.js"></script>
<script src="quotes.js"></script>
<link rel="stylesheet" href="//netdna.bootstrapcdn.com/bootstrap/3.1.1/css/bootstrap.min.css">
<link href="//netdna.bootstrapcdn.com/font-awesome/4.0.3/css/font-awesome.css" rel="stylesheet">
<link rel="stylesheet" href="shell.css">
<link href='http://fonts.googleapis.com/css?family=Audiowide' rel='stylesheet' type='text/css'>
<link href='http://fonts.googleapis.com/css?family=Sue+Ellen+Francisco' rel='stylesheet' type='text/css'>
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1, user-scalable=no">


<script type="text/javascript">

window.onerror = function(error) {
    alert(error);
};

$(document).ready(function(){

	var lastWord  			= "", 			// Used for auto correct detection
		startTimer			= 1, 			// Game start countdown
		score				= 0,			// Holds the final score		
		gameInProgress  	= false,
		completedQuotes		= new Array(), 	// Holds all the completed quotes to show @ gameover screen
		kareokeGap			= 30, 			// How much letters will the kareoke show
        secondsLabel 		= document.getElementById("game_seconds"),
        gameTime 			= 0, 			// Time left to play
		gameStartTime		= 10000, 		// Starting time on gameStart
		charsTyped			= 0,			// How many chars he typed overall **** NOT USED ****
		charBonus			= 500,
		sentenceBonus		= 5000,		
		autoCorrectBonus	= 1000,
		charPenalty			= 200,		
		autoCorrectPenalty	= 2000,
		pastePenalty		= 5000,
		currentVal,							// Used for auto correct detection
		gameTimer,							// Holding the interval of the game timer, to stop count when game over
		kareoke,							// Array of the current sentence chars
		kareokeFrom,						// Kareoke starting index
		kareokeTo,							// Kareoke ending index
		currentQuote;						// Current quote displaed
		
		
		
		
	
	console.log(quoteDatabase);

	
	//@TODO: this code should be used for "Settings", if they'll exist, since this switches between buttons.	
	// $('.game_type_btns').click(function(){
	
		// if(!$(this).hasClass("btn-primary")){
		
			// $('.game_type_btns').addClass("btn-default").removeClass("btn-primary");
			// $(this).removeClass("btn-default").addClass("btn-primary");
		// }

	
	// });
		
	$('#game_input').on('paste',function(){
	
		//autoCorrectDetected();
	
		$('#game_input').val('');
		gameTime -= pastePenalty;
		score -= pastePenalty;
		notify("<span style='color:red;'>-"+miliToString(pastePenalty)+"</span>");
	});	
	
	
	
	
    function setTime(){
	

		gameTime -= 100;
		if(gameTime < 2000){
			secondsLabel.innerHTML = miliToString(gameTime);
			secondsLabel.setAttribute('style', "color:red;");
			
		}
		else{
			secondsLabel.innerHTML = miliToString(gameTime);
			secondsLabel.setAttribute('style', "color: inherit;");
			}
		
		if(gameTime < 0.1)
			gameOver();
			
    }

	function resetTime(){
	
		gameTime 				= gameStartTime;
		secondsLabel.innerHTML 	= gameStartTime+".00";
		secondsLabel.setAttribute('style', "color: inherit;");

	}
	

	function getRandomString(){
	
		currentQuote = quoteDatabase[Math.floor(Math.random() * quoteDatabase.length)];
		//currentQuote = quoteDatabase[1];

		return currentQuote;

	}
	
	function getAutoCorrect(s1,s2){
		var string1 = new Array();
		var string2 = new Array();
		string1 = s1.split(" ");
		string2 = s2.split(" ");
		var diff = new Array();

		if(s1.length>s2.length){
			var long = string1;
		}
		else {
			var long = string2;
		}
		for(x=0;x<long.length;x++){
		   if(string1[x]!=string2[x]){
			  diff.push(string2[x]);
		   }
		}	
	
		return diff.join(" ");
	
	}
	

	function autoCorrectDetected(){
	
		var got 		= getAutoCorrect(lastWord,currentVal).trim();		
		var expected 	= currentQuote.quote.substring(lastWord.length-got.length,lastWord.length).trim();		

		setTimeout(function(){
			
			
			if(got.localeCompare(expected) == 0){
				//alert("Should fucking print!");
				gameTime += autoCorrectBonus;
				score += autoCorrectBonus;
				notify("+"+miliToString(autoCorrectBonus));
			}
			else{
			
				//The first check only fits some of auto completions. This is an ugly check and will probably bug at some point.
				var location = currentQuote.quote.indexOf(got);
				if( location != -1){
				
					gameTime += autoCorrectBonus;
					score += autoCorrectBonus;
					notify("+"+miliToString(autoCorrectBonus));
					// kareokeFrom = location+got.length;
					// kareokeTo = kareokeFrom + kareokeGap;
				
				}
				else{
					gameTime -= autoCorrectPenalty;
					score -= autoCorrectBonus;
					notify("<span style='color:red;'>-"+miliToString(autoCorrectPenalty)+"</span>");		
				}
			}
			//alert("AC Diff: "+diff+" Expected: "+expected+" Got: "+got);		

		},300);

	}
	

	
	function gameOver(){
		
		clearInterval(gameTimer);
		gameScore = calcScore();
		$('#game_end .score').html("Your score is:"+gameScore);
		var html = "";
		$.each(completedQuotes,function(index,item){
			
			html += "<li>\""+item.quote+"\" -- "+item.quote_by+"</li>";
		
		});
		console.log("HTML: "+html);
		$('#game_end .quotes-list').html(html);
		$('#game_end').modal("show");
		endGame();
	
	}
	
	function calcScore(){
	
		return Math.round(score / 1000);
	
	}
	
	function notify(html){
		var uniq = 'ff' + (new Date()).getTime();
		$('#flying_stuff').append("<span class='flying_stuff' id='"+uniq+"'>"+html+"</span>");
		$("#"+uniq).animate({
							bottom : $('#flying_stuff').offset().top
							},2000,'linear', function() {
								$("#"+uniq).slideDown().remove();
							});

	
	}	
	
	
	// function mobile_debug(object){
	// //alert(JSON.stringify(object, null, 4));
		// var output = '';
		// for (var property in object) {
		  // output += property + ': ' + object[property]+'; ';
		// }
		// alert(output);
	
	// }
	
	var newGameEvent = function(){
	
		$('#game_end').modal("hide");
		if(gameInProgress)
			endGame();
			
		var count = startTimer;
	    $('html, body').animate({
			scrollTop: $("#shb-start-countdown").offset().top
		}, 1000);
		$('#game_container').css('visibility', 'visible');
		$('#shb-start-countdown').show();
		var gameStartCountdown = setInterval(function() {

			
			if (count !== 0) {
			  $('#shb-start-countdown').html(count--);
			} else {
			  clearInterval(gameStartCountdown);
			  $('#shb-start-countdown').fadeOut('fast',function(){
				$('#string_to_match').css('visibility', 'visible');
				gameInProgress = true;
				startGame();
			  });
			  
			}
		}, 1000);		
	
	
	}
	
	$('.new_game').click(newGameEvent);

	$('#game_input').keyup(function(e){
		
		
		if(!gameInProgress){
			e.preventDefault();
			return;
		}
		

		currentVal = $(this).val();
		if(lastWord != ""){ //backspace & first type
			
			if((currentVal.indexOf(lastWord) == -1) || (currentVal.length - lastWord.length > 1)){
				
				autoCorrectDetected();
			}

			
			
		}
		lastWord = currentVal;
		charsTyped++;
		
	
		
		secondsLabel.innerHTML = miliToString(gameTime);

		
		
	});
	

	
	$('#game_input').keydown(function(e){

		if(e.keyCode == 8){
			e.preventDefault();
			e.stopPropagation();
			return;	
			
		}
	
	});
	
	$('#game_input').keypress(function(e){
	
		var charCode = (typeof e.which == "number") ? e.which : e.keyCode

		//console.log("Exp: "+$('#kareoke span').html().toUpperCase()+" Got: "+String.fromCharCode(charCode).toUpperCase());
		
		if( $('#kareoke span').html().toUpperCase() == String.fromCharCode(charCode).toUpperCase()){
		gameTime += charBonus;
		score += charBonus;
		if(score % 10000 == 0 && charBonus > 100)
			charBonus -= 100;
		notify("+"+miliToString(charBonus));
		}
		else{
			gameTime -= charPenalty;
			score -= charPenalty;
			notify("<span style='color:red;'>-"+miliToString(charPenalty)+"</span>");
	
		
		}
		
	
				
		updateKareoke(e);
		console.log(score);
	});


	function startGame(){
		resetTime();
		charsTyped	= 0;
		score		= 0;
		var quote 	= getRandomString();
		//$('#string_to_match blockquote').html(quote.quote);
		//$('#string_to_match .shb-quote-author').html(quote.quote_by);
		$('#game_input').prop('readonly',false);		
		initKareoke(quote);
		gameTimer = setInterval(setTime, 100);
	}
	
	
	
	function endGame(){
	
		gameInProgress = false;
		$('#game_container').css('visibility', 'hidden');
		$('#string_to_match').css('visibility','hidden');	
		$('#shb-start-countdown').empty();
		$('#game_input').val('');
		$('#game_input').prop('readonly',true);
		$('#kareoke').empty();
		resetTime(); 
		//$('#shb-start-countdown').show();
		
	}
	
	function initKareoke(quote){
		kareoke 	= quote.quote.split('');
		console.log(kareoke);
		
		kareokeFrom	= 0;
		if(quote.quote.length > kareokeGap)
			kareokeTo = kareokeGap;
		else
			kareokeTo = quote.quote.length;
		printKareoke(kareokeFrom,kareokeTo);
	
	}
	//if not valid key stroke, all the neglected keys
	function isKeyValid(keyCode){
		if( (keyCode < 48 && keyCode != 32 && keyCode != 8) || (keyCode >111 && keyCode < 124) 
			|| keyCode == 144 || keyCode == 155 || keyCode > 222)
			return false;
		return true;
	}
	
	/**
	 *  @brief Handles updating the kareoke, should be called every keydown
	 *  
	 *  @param [in] e event
	 *  @return void
	 *  
	 *  @details Details
	 */
	function updateKareoke(e){
		

		if(kareokeTo < kareoke.length)
			kareokeTo++;
		if(kareokeFrom < kareoke.length)
			kareokeFrom++;
		
		/* If the end of the sentence, bring a new one*/
		if(kareokeFrom == kareoke.length){

			sentenceCompleted();
			e.preventDefault();

		
		}		
		
		printKareoke(kareokeFrom,kareokeTo);
	}
	
	function miliToString(time){
		return (time / 1000).toFixed(2);
	}
	
	function sentenceCompleted(){
		console.log("Sentence Complete | Input : "+$('#game_input').val() +" Expected : "+kareoke.join(''));
		if($('#game_input').val().localeCompare(kareoke.join('')) == 0){
			console.log("Sentence is cool");
			gameTime += sentenceBonus;
			score += sentenceBonus;
			notify("+"+miliToString(sentenceBonus));
		
		}
			
		$('#game_input').val('');
		lastWord = "";
		completedQuotes.push(currentQuote);
		var quote 	= getRandomString();	
		initKareoke(quote);
	
	}
	
	/**
	 *  @brief Handles outputing the right chars in the kareoke
	 *  
	 *  @param [in] from Parameter_Description
	 *  @param [in] to Parameter_Description
	 *  @return Return_Description
	 *  
	 *  @details Details
	 */
	function printKareoke(from,to){
	
		if(to > kareoke.length){
			console.log("printKareoke 'to' index is bigger then array");
			return;
		}
		if(from == to)
			$('#kareoke').empty();
		else
			$('#kareoke').html("<span style='color:green;'>"+kareoke[from]+"</span>"+kareoke.slice(from+1,to).join(''));
		
		console.log("From: "+from);
		console.log("To: "+to);
	}
	
	
	
	
	
});
</script>
</head>

<body>
<a href="#faq_modal" data-toggle="modal" role="button" id="faq-button">
<i class="fa fa-question fa-2x"></i> 
</a>	
<div class="container-fluid">
	<div class="row">
		<div class="text-center shb-pannel">
			<h3>Auto Correct Challange</h3>
			<p class="shb-desc">Worst Auto Correct means that the winner is the one that didn't invoke his auto correct first,
			 while Best Auto Correct means that the winner is the one which invoked the most accurate auto corrections. In both
			 game types the objective is to write the sentences displaying without mistakes, including punctuation</p>
	
		</div>
	</div>
	<div class="row">
		<div class="text-center shb-pannel">
		
			<p style="margin-top:3em;">
			  <button type="button" class="btn btn-success new_game" id="main_new_game">New Game</button>
			</p>
			<div id="shb-start-countdown"></div>
			<div id="game_container">
				<div id="string_to_match" class="shb-quote" style="visibility:hidden;">
				<blockquote></blockquote>
				<span class="shb-quote-author"></span>
				</div>
				<div>
					<div id="kareoke"></div>
					
				</div>
				<input type="text" id="game_input" class="form-control" />
				<div id="game_timer"><label id="game_seconds">5.00</label><span id="flying_stuff"></span></div>
				<div id="debugger"></div>
			</div>
			
		</div>
	</div>
</div>

<div class="modal fade" role="dialog" id="faq_modal">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <button type="button" class="close" data-dismiss="modal" aria-hidden="true">&times;</button>
        <h4 class="modal-title">FAQ</h4>
      </div>
      <div class="modal-body">
        <p class="shb-faq-q">How to play?</p>
		<p class="shb-faq-a">Hit the "New Game" button, after selecting the game type you wish, and then simply write the sentences that appear 
		on your screen.</p>	  
        <p class="shb-faq-q">Why is there no leaderboard?</p>
		<p class="shb-faq-a">Well, we find it frustrating when you work really hard in an arcade game to then find out some guy did
		a million times.</p>

        <p class="shb-faq-q">Sometimes I get a sentence that's just unwriteable!</p>
		<p class="shb-faq-a">Ya, sorry about that. Just hit the refresh button and fetch another sentence</p>
		
		<p class="shb-faq-q">How can I contact you?</p>
		<p class="shb-faq-a">Our telepathy service is temporarily down for maintenance, so in the mean time you can mail us at 
			<a href="mailto:contact@shibby.co.il">
				contact@shibby.co.il
			</a>
		</p>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-primary" data-dismiss="modal">Close</button>
      </div>
    </div><!-- /.modal-content -->
  </div><!-- /.modal-dialog -->
</div><!-- /.modal -->




<div class="modal fade" role="dialog" id="game_end">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <button type="button" class="close" data-dismiss="modal" aria-hidden="true">&times;</button>
        <h4 class="modal-title">Game over</h4>
      </div>
      <div class="modal-body">
      <div class="score"></div>
	  <br><br>
	  <div>
		You have been given the following quotes:
		<ul class="quotes-list"></ul>
	  </div>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-primary" data-dismiss="modal">Close</button>
		<button type="button" class="btn btn-success new_game" >New Game</button>
      </div>
    </div><!-- /.modal-content -->
  </div><!-- /.modal-dialog -->
</div><!-- /.modal -->


</body>
</html>