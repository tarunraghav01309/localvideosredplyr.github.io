<!DOCTYPE html>
<html lang="en">
  <head>
  <link rel="icon" type="image/png" href="Images/Local-Red_Player_Logo.png"/>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>LOCAL-Red Video Plyr v1.2</title>
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/js/bootstrap.min.js"></script>
</head>
<body>
<meta name="viewport" content="width=device-width, initial-scale=1">
<div class="container">
  <!-- Modal -->
  <div class="modal fade" id="myModal" role="dialog">
    <div class="modal-dialog modal-lg">
      <div class="modal-content">
        <div class="modal-header">
          <button type="button" class="close" data-dismiss="modal">&times;</button>
          <h4 class="modal-title">Select & Play-</h4>
        </div>
        <div class="modal-body">
       <ul class="nav-links"></ul>
        </div>
        <div class="modal-footer">
          <button type="button" class="btn btn-default" data-dismiss="modal">OK-Close</button>
        </div>
      </div>
    </div>
  </div>
</div>

</body>
</html>

<!DOCTYPE html>
<html lang="en">
  <head>
  
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Local Videos Red Plyr v1.2</title>
   <link rel="stylesheet" href="https://cdn.plyr.io/3.6.8/plyr.css" />
   <link rel="stylesheet" href="https://cdn.plyr.io/3.6.2/demo.css" />
   </head>
   <body>
<style>
  ul{
  display:inline-block;
  border:1px solid black;
  padding:100px;
  margin:4px, 4px; 
  
  padding:2px; 
  
  background-color: #00CCFF;
  
  width: 100%; 
  
  height: 200px; 
  
  overflow-x: hidden; 
  
  overflow-y: auto; 
  
  text-align:justify; 
  }
  
  li{
  margin-top: 10px;
  border:1px solid black;
  background:#333333;
  color:silver;
  float: up;
  cursor: pointer;
  scroll-behavior: auto;
  padding: 6px;
  border-top: 0px;
  border-left: 0px;
  border-right: 0px;
  border-radius: 5px;
  }
  
  li:hover {
  cursor: pointer; 
  scroll: auto;
  
  box-sizing: border-box;
  width: 100%;
  padding: 8px;
  border-top: 0px;
  border-left: 0px;
  border-right: 0px;
  /*
  letter-spacing: 1%;
  */
  color: white;
  background-color: black;
  border:3px solid orange;
  }
  
  li:module {
  scroll-behavior: [ auto ];
  }
  
  li:first-child {
  margin-top:0;
  }
  
  * {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
  }
  
  body {
  background-color: none;
  width: 100%;
  hight: 100%;
  display:inline-block;
  margin:4px, 4px; 
  padding: 0%; 
  }
  
  .nav-links {
  display: ;
  justify-content: space-between;
  width: 100%;     
  }
  
  .nav-links li {
  list-style: none;
  }
  
  .nav-links {
  text-decoration: none;
  font-family: Poppins;
  color: ;
  letter-spacing: 0px;
  font-weight: bold;
  font-size: auto;
  margin: -11px;
  }
  
  </style>
<style>
</style>
<video controls crossorigin playsinline
     data-poster="https://cdn.plyr.io/static/demo/View_From_A_Blue_Moon_Trailer-HD.jpg" class="vid1" id="player"
     
<video controls PictureInPicture width="100%" height="100%" preload="metadata" controlslist="download" autoplay></video>
<input type="file" multiple>
<a class='fadeout' href="#">Open Files</a>
<!-- Trigger the modal with a button -->
  <button type="button" class="btn btn-info btn-lg" data-toggle="modal" data-target="#myModal">Open Video Playlist</button>
<script>
	// get DOM elements
	const video = document.querySelector('video');
	const filesInput = document.querySelector('input[type=file]');
	const speedInput = document.querySelector('input[type=text]');
	const filesButton = document.querySelector('a');
	const playlist = document.querySelector('ul');

	// redirect filesButton click to hidden filesInput
	filesButton.addEventListener('click', e => {
		filesInput.click();
		e.preventDefault();
		return false;
	});

	filesInput.addEventListener('change', function (e) {
		

		// go through all selected files
		for (const file of Array.from(this.files)) {

			// create list item and object url for the video file
			const listItem = document.createElement('li');
			listItem.objUrl = URL.createObjectURL(file);
			listItem.textContent = file.name;

			// give list item a click event listener for the corresponding video
			listItem.addEventListener('click', function (e) {
				this.classList.add('played');
				video.src = this.objUrl;
				video.playbackRate = Number(speedInput.value);
			});

			// append li to the list
			playlist.appendChild(listItem);
            
		};

		// show the playlist for a moment
		playlist.classList.add('fadeout');
	}, false /* don't capture */);

	// remove playlist fadeout after the animation ends, so it can be retriggered
	playlist.addEventListener('animationend', e => {
		playlist.classList.remove('fadeout');
	});
 
	// handle changes to speed input
	speedInput.addEventListener('change', e => {
		video.playbackRate = Number(speedInput.value);
		// write actual playback rate value back to input
		speedInput.value = Number(video.playbackRate);
	});

	// add keyboard shortcuts for pause (space) and 5 sec jump (left/right arrow)
	document.addEventListener('keydown', e => {
		// console.log(e.keyCode);
		switch (e.keyCode) {
			case 32: // space
				video.paused ? video.play() : video.pause();
				break;
			case 37: // left arrow
				video.currentTime += -5;
				break;
			case 39: // right arrow
				video.currentTime += 5;
				break;
		}
	});
</script>
<script src="https://cdn.plyr.io/3.6.8/plyr.js"></script>
<script src="https://cdn.plyr.io/3.6.2/demo.js" crossorigin="anonymous"></script>
<script>
Notification.requestPermission().then(function(getperm) 

{ 

	console.log('Perm granted', getperm) 

});
</script>
<script>
  var controls =
[
    'play-large', // The large play button in the center
   'restart', // Restart playback
   'duration', // The full duration of the media
   'rewind', // Rewind by the seek time (default 10 seconds)
    'play', // Play/pause playback
    'fast-forward', // Fast forward by the seek time (default 10 seconds)
    'progress', // The progress bar and scrubber for playback and buffering
    'current-time', // The current time of playback
    'mute', // Toggle mute
    'volume', // Volume control
    //'captions', // Toggle captions
    'settings', // Settings menu
    'pip', // Picture-in-picture (currently Safari only)
    'airplay', // Airplay (currently Safari only)
    'download', // Show a download button with a link to either the current source or a custom URL you specify in your options
    'fullscreen'// Toggle fullscreen
];

  const player = new Plyr('.vid1',{controls});
</script>

<style>
  :root {
  --plyr-color-main: red;
    --plyr-video-control-color  :white;
}

</style>
<p></p>
 </body>
</html>
