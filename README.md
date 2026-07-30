# BOUSBAMOUR
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Pour Toi ❤️</title>
  <style>
    /* Styles globaux */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(135deg, #ffdde1 0%, #ee9ca7 100%);
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      overflow-x: hidden;
      color: #5a2a3a;
      text-align: center;
      padding: 20px;
    }

    /* Boîte principale */
    .container {
      background: rgba(255, 255, 255, 0.85);
      backdrop-filter: blur(8px);
      padding: 40px 30px;
      border-radius: 25px;
      box-shadow: 0 15px 35px rgba(238, 156, 167, 0.4);
      max-width: 500px;
      width: 100%;
      border: 2px solid #fff;
      transition: all 0.3s ease;
    }

    h1 {
      font-size: 1.8rem;
      color: #d63384;
      margin-bottom: 25px;
    }

    /* Boutons romantiques */
    .btn-love {
      background: linear-gradient(45deg, #ff4b2b, #ff416c);
      color: white;
      border: none;
      padding: 15px 30px;
      font-size: 1.1rem;
      font-weight: bold;
      border-radius: 50px;
      cursor: pointer;
      box-shadow: 0 5px 15px rgba(255, 65, 108, 0.4);
      transition: transform 0.2s, box-shadow 0.2s;
      outline: none;
    }

    .btn-love:hover {
      transform: scale(1.05);
      box-shadow: 0 8px 20px rgba(255, 65, 108, 0.6);
    }

    .btn-love:active {
      transform: scale(0.98);
    }

    /* Section Phrase d'amour */
    #love-message-section {
      display: none;
      animation: fadeIn 1s ease-in-out forwards;
    }

    .love-phrase {
      font-size: 1.5rem;
      font-weight: 600;
      color: #c2185b;
      margin-bottom: 25px;
      line-height: 1.4;
    }

    /* Section Vidéo */
    #video-container {
      display: none;
      margin-top: 20px;
      animation: fadeIn 1s ease-in-out forwards;
    }

    video {
      width: 100%;
      max-height: 450px;
      border-radius: 15px;
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
      border: 3px solid #ff416c;
    }

    /* Animation d'apparition */
    @keyframes fadeIn {
      from {
        opacity: 0;
        transform: translateY(15px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    /* Cœurs animés en arrière-plan */
    .heart {
      position: absolute;
      color: #ff416c;
      font-size: 20px;
      user-select: none;
      pointer-events: none;
      animation: floatUp 4s linear infinite;
      opacity: 0.7;
    }

    @keyframes floatUp {
      0% {
        transform: translateY(100vh) scale(0.5);
        opacity: 1;
      }
      100% {
        transform: translateY(-10vh) scale(1.2);
        opacity: 0;
      }
    }
  </style>
</head>
<body>

  <div class="container">
    <div id="intro-section">
      <h1>Une surprise pour toi... 💌</h1>
      <button class="btn-love" onclick="showLoveMessage()">Clique ici mon amour ❤️</button>
    </div>

    <div id="love-message-section">
      <p class="love-phrase">« Tu veux savoir à quel point je t'aime ? » ✨</p>
      <button class="btn-love" id="start-btn" onclick="startVideo()">▶ START</button>
    </div>

    <div id="video-container">
      <video id="myVideo" controls>
        <source src="FullSizeRender(7).mov" type="video/quicktime">
        <source src="FullSizeRender(7).mov" type="video/mp4">
        Votre navigateur ne supporte pas la lecture de cette vidéo.
      </video>
    </div>
  </div>

  <script>
    // Fonction pour afficher la phrase d'amour
    function showLoveMessage() {
      document.getElementById('intro-section').style.display = 'none';
      document.getElementById('love-message-section').style.display = 'block';
    }

    // Fonction pour lancer la vidéo
    function startVideo() {
      document.getElementById('start-btn').style.display = 'none';
      const videoContainer = document.getElementById('video-container');
      const video = document.getElementById('myVideo');
      
      videoContainer.style.display = 'block';
      video.play();
    }

    // Création automatique de petits cœurs volants
    function createHearts() {
      const heart = document.createElement('div');
      heart.classList.add('heart');
      heart.innerHTML = '❤️';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = (Math.random() * 2 + 3) + 's';
      document.body.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 5000);
    }

    setInterval(createHearts, 400);
  </script>
</body>
</html>
