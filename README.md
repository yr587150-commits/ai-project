<!DOCTYPE html>
<html>
<head>
    <title>AI Chatbot</title>
    <link rel="stylesheet" href="/static/style.css">
</head>
<body>

<h2>🤖 AI Chatbot</h2>

<div id="chatbox"></div>

<input type="text" id="userInput" placeholder="Type a message...">
<button onclick="sendMessage()">Send</button>

<script>
function sendMessage() {
    let input = document.getElementById("userInput");
    let message = input.value;

    fetch("/chat", {
        method: "POST",
        headers: {"Content-Type": "application/json"},
        body: JSON.stringify({message: message})
    })
    .then(res => res.json())
    .then(data => {
        let chatbox = document.getElementById("chatbox");
        chatbox.innerHTML += "<p><b>You:</b> " + message + "</p>";
        chatbox.innerHTML += "<p><b>Bot:</b> " + data.reply + "</p>";
        input.value = "";
    });
}
</script>

</body>
</html>
