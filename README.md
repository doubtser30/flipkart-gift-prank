<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Flipkart Gift Voucher</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f1f3f6;
      margin: 0;
      text-align: center;
    }
    header {
      background-color: #2874f0;
      color: white;
      padding: 1rem;
      font-size: 1.5rem;
    }
    .box-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      margin: 2rem;
    }
    .gift-box {
      background: #fff;
      border: 2px solid #ccc;
      border-radius: 10px;
      width: 120px;
      height: 120px;
      margin: 1rem;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 2rem;
      transition: transform 0.2s;
    }
    .gift-box:hover {
      transform: scale(1.05);
    }
    .popup, .final-popup {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background: white;
      padding: 2rem;
      box-shadow: 0 0 10px rgba(0,0,0,0.3);
      display: none;
      z-index: 10;
      border-radius: 10px;
    }
    .popup h2 {
      color: green;
    }
    .overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0,0,0,0.4);
      display: none;
      z-index: 5;
    }
    button {
      margin-top: 1rem;
      padding: 0.6rem 1.2rem;
      background-color: #2874f0;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    .joker {
      font-size: 3rem;
    }
  </style>
</head>
<body>
  <header>Flipkart Gift Voucher</header>
  <div class="box-container">
    <div class="gift-box">?</div>
    <div class="gift-box">?</div>
    <div class="gift-box">?</div>
    <div class="gift-box">?</div>
    <div class="gift-box">?</div>
    <div class="gift-box">?</div>
  </div>  <div class="overlay"></div>  <div class="popup" id="popup">
    <h2>CONGRATULATIONS!</h2>
    <p>You have won the iPhone 13!</p>
    <button onclick="showFinalPopup()">Redeem Gift</button>
  </div>  <div class="final-popup" id="finalPopup">
    <div class="joker">JOKER FACE</div>
    <p>Shubadhinam and a smile :)</p>
  </div>  <script>
    let clicked = false;
    const boxes = document.querySelectorAll(".gift-box");
    const popup = document.getElementById("popup");
    const overlay = document.querySelector(".overlay");
    const finalPopup = document.getElementById("finalPopup");

    boxes.forEach((box) => {
      box.addEventListener("click", () => {
        if (!clicked) {
          clicked = true;
          popup.style.display = "block";
          overlay.style.display = "block";
        }
      });
    });

    function showFinalPopup() {
      popup.style.display = "none";
      finalPopup.style.display = "block";
    }
  </script></body>
</html>
