<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Proposal</title>
  <style>
    body {
      text-align: center;
      margin-top: 100px;
    }
    button {
      margin: 10px;
      padding: 10px;
      font-size: 18px;
    }
    #noButton {
      position: relative;
    }
  </style>
</head>
<body>
  <h1>Samahan mo ko sa Balik Sinta?</h1>

  <div id="initialState">
    <button id="yesButton">Oo</button>
    <button id="noButton">Hindi</button>
  </div>

  <div id="finalMessage" style="display: none;">
    <h2>Yay! Sama tayo!</h2>
    <img
      src="https://media.giphy.com/media/vtm4qejJIl1ERPIrbA/giphy.gif?cid=790b761161qbveksnfz3j3d8jybu4g8lo3najnw5i6i7tatv&ep=v1_gifs_search&rid=giphy.gif&ct=g"
      alt="Kinikilig"
      style="width: 300px; height: 300px;"
    />
    <audio controls autoplay>
      <source
        src="https://www.dropbox.com/scl/fi/p0b33ukgy9x8fg0ken1lv/James-Reid-and-Nadine-Lustre-Hanap-Hanap-Lyric-Video-with-Chords.mp3?rlkey=civw7lj94doubszp9svky8zxy&raw=1"
        type="audio/mpeg"
      />
      Your browser does not support the audio element.
    </audio>
  </div>

  <script>
    const yesButton = document.getElementById("yesButton");
    const noButton = document.getElementById("noButton");
    const initialState = document.getElementById("initialState");
    const finalMessage = document.getElementById("finalMessage");

    yesButton.addEventListener("click", () => {
      initialState.style.display = "none";
      finalMessage.style.display = "block";
    });

    noButton.addEventListener("mouseenter", () => {
      noButton.style.left = (noButton.style.left === "50px" ? "0px" : "50px");
    });
  </script>
</body>
</html>
