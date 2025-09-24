<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Word Match Checker</title>
</head>
<body>
  <h2>Word Match Checker</h2>
  <textarea id="text1" rows="6" cols="40" placeholder="Enter first text..."></textarea><br><br>
  <textarea id="text2" rows="6" cols="40" placeholder="Enter second text..."></textarea><br><br>
  <button id="checkBtn">Check Matches</button>
  <p id="result"></p>

  <script>
    document.getElementById("checkBtn").onclick = function() {
        var t1 = document.getElementById("text1").value.toLowerCase().split(/\W+/);
        var t2 = document.getElementById("text2").value.toLowerCase().split(/\W+/);
        t1 = t1.filter(w => w.length > 0);
        t2 = t2.filter(w => w.length > 0);
        var matches = t1.filter(w => t2.indexOf(w) >= 0);
        var unique = [...new Set(matches)];
        document.getElementById("result").innerHTML =
            "Matching words: " + unique.length + "<br>" + unique.join(", ");
    };
  </script>
</body>
</html>
