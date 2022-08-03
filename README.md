# iotTask
Team work


التحويل من صوت الى نص:
<!DOCTYPE html>
<html lang="ar">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content=
    "width=device-width, initial-scale=1.0">
<button> start</button>
  <title>Speech to Text</title>
</head>

<body>
  <div class="words" contenteditable>
    <p id="p"></p>
  </div>

  <script>
    var speech = true;
    window.SpeechRecognition = window.SpeechRecognition
            || window.webkitSpeechRecognition;

    const recognition = new SpeechRecognition();
    recognition.interimResults = true;
    const words = document.querySelector('.words');
    words.appendChild(p);
	recognition.lang='ar';

    recognition.addEventListener('result', e => {
      const transcript = Array.from(e.results)
        .map(result => result[0])
        .map(result => result.transcript)
        .join('')

      document.getElementById("p").innerHTML = transcript;
      console.log(transcript);
    });
    
    if (speech == true) {
      recognition.start();
      recognition.addEventListener('end', recognition.start);
    }
  </script>
</body>

</html>
