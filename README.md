    <!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Red Hacker Editor 🔴</title>

<style>
body {
    margin: 0;
    background: linear-gradient(135deg, #0a0a0a, #1a0000);
    font-family: sans-serif;
    color: #ff4d4d;
}

/* Header */
header {
    text-align: center;
    padding: 15px;
    font-size: 20px;
    background: rgba(255,0,0,0.1);
    backdrop-filter: blur(10px);
    border-bottom: 1px solid rgba(255,0,0,0.3);
}

/* Layout */
.container {
    display: flex;
    height: 85vh;
}

/* Editor */
textarea {
    width: 50%;
    height: 100%;
    background: rgba(0,0,0,0.6);
    color: #ff4d4d;
    border: none;
    padding: 15px;
    font-size: 14px;
    outline: none;
    backdrop-filter: blur(5px);
}

/* Preview */
iframe {
    width: 50%;
    height: 100%;
    border: none;
    background: white;
}

/* Controls */
.controls {
    text-align: center;
    padding: 10px;
}

/* Soft Buttons */
button {
    background: rgba(255,0,0,0.1);
    color: #ff4d4d;
    border: none;
    padding: 12px 18px;
    margin: 8px;
    border-radius: 50px;
    cursor: pointer;
    backdrop-filter: blur(10px);
    box-shadow: 0 0 10px rgba(255,0,0,0.4);
    transition: 0.3s;
}

button:hover {
    background: #ff4d4d;
    color: black;
}
</style>

</head>

<body>

<header>🔴 RED HACKER EDITOR</header>

<div class="controls">
    <button onclick="runCode()">▶ Run</button>
    <button onclick="clearCode()">Clear</button>
    <button onclick="downloadCode()">Download</button>
</div>

<div class="container">
    <textarea id="code"><!DOCTYPE html>
<html>
<body style="background:black; color:white; text-align:center;">
<h1>🔥 Working Perfectly 🔴</h1>
</body>
</html></textarea>

    <iframe id="preview"></iframe>
</div>

<script>
function runCode() {
    let code = document.getElementById("code").value;
    let iframe = document.getElementById("preview");

    // FIXED METHOD (Acode compatible)
    iframe.contentWindow.document.open();
    iframe.contentWindow.document.write(code);
    iframe.contentWindow.document.close();
}

function clearCode() {
    document.getElementById("code").value = "";
}

function downloadCode() {
    let code = document.getElementById("code").value;
    let blob = new Blob([code], { type: "text/html" });
    let a = document.createElement("a");
    a.href = URL.createObjectURL(blob);
    a.download = "code.html";
    a.click();
}
</script>

</body>
</html>
