# Ubuntu-nursing-colloquium-.github.io
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Digital Poster Hall</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 20px;
      text-align: center;
      background-color: #f5f5f5;
    }
    h1 {
      color: #333;
    }
    input, button {
      font-size: 16px;
      padding: 8px 12px;
      margin: 5px;
    }
    iframe {
      margin-top: 20px;
      border: 2px solid #ccc;
    }
    #posterDisplay p {
      color: red;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <h1>Welcome to the Digital Poster Hall</h1>
  <p>Type the number of the poster you want to view:</p>
  
  <input type="number" id="posterNumber" placeholder="Enter poster number">
  <button onclick="showPoster()">Go</button>
  
  <div id="posterDisplay"></div>
  
  <script>
    // 🔹 Add your poster files here
    const posters = {
      1: "poster1_intro.pdf",
      2: "poster2_methods.pdf",
      3: "poster3_results.pdf",
      4: "poster4_discussion.pdf",
      5: "poster5_conclusion.pdf"
      // Add more posters as needed
    };

    function showPoster() {
      const num = document.getElementById("posterNumber").value;
      const display = document.getElementById("posterDisplay");
      if(posters[num]){
        display.innerHTML = `
          <h2>Poster ${num}</h2>
          <iframe src="${posters[num]}" width="800" height="600"></iframe>
          <br><button onclick="goBack()">Back to Menu</button>
        `;
      } else {
        display.innerHTML = "<p>Poster not found. Check the number.</p>";
      }
    }

    function goBack() {
      document.getElementById("posterDisplay").innerHTML = "";
      document.getElementById("posterNumber").value = "";
    }
  </script>
</body>
</html>
