<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Valentine 💖</title>

<style>
  body {
    margin: 0;
    height: 100vh;
    background: linear-gradient(120deg, #ff9a9e, #fad0c4);
    overflow: hidden;
    font-family: 'Segoe UI', sans-serif;
    text-align: center;
  }

  h1 {
    margin-top: 120px;
    font-size: 34px;
    color: #fff;
    text-shadow: 2px 2px 6px rgba(0,0,0,0.3);
  }

  .buttons {
    margin-top: 40px;
  }

  button {
    padding: 15px 35px;
    font-size: 20px;
    border: none;
    border-radius: 30px;
    cursor: pointer;
    transition: 0.3s;
  }

  #yes {
    background: #ff4d6d;
    color: white;
  }

  #yes:hover {
    transform: scale(1.1);
  }

  #no {
    background: white;
    color: #ff4d6d;
    position: absolute;
  }

  /* Floating hearts */
  .heart {
    position: absolute;
    font-size: 20px;
    animation: float 6s linear infinite;
  }

  @keyframes float {
    0% {
      transform: translateY(100vh);
      opacity: 1;
    }
    100% {
      transform: translateY(-10vh);
      opacity: 0;
    }
  }

  .celebrate {
    font-size: 38px;
    margin-top: 40px;
    animation: pop 0.6s ease-in-out infinite alternate;
  }

  @keyframes pop {
    from { transform: scale(1); }
    to { transform: scale(1.08); }
  }
</style>
</head>

<body>

<h1 id="text">ARJU, WILL YOU BE MY VALENTINE? 💖</h1>

<div class="buttons">
  <button id="yes">YES</button>
  <button id="no">NO</button>
</div>

<audio id="song">
  <source src="kasari.mp3" type="audio/mpeg">
</audio>

<script>
  const yes = document.getElementById("yes");
  const no = document.getElementById("no");
  const text = document.getElementById("text");
  const song = document.getElementById("song");

  song.volume = 0.25; // halka sound 🎵

  yes.onclick = () => {
    text.innerHTML = "I KNEW YOU LOVE ME 💃🕺";
    text.classList.add("celebrate");
    song.play();
  };

  no.onmouseover = () => {
    no.style.left = Math.random() * 80 + "vw";
    no.style.top = Math.random() * 80 + "vh";
  };

  // Hearts generator
  setInterval(() => {
    const heart = document.createElement("div");
    heart.className = "heart";
    heart.innerHTML = "💖";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.fontSize = Math.random() * 20 + 15 + "px";
    document.body.appendChild(heart);

    setTimeout(() => {
      heart.remove();
    }, 6000);
  }, 300);
</script>

</body>
</html>
