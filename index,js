document.addEventListener("DOMContentLoaded", function () {
    let randomnumber = Math.floor(Math.random() * 100) + 1;
    let guess = 10;
    let guesspositiv = 0;
    console.log("Die zufällige Zahl ist: ", randomnumber);

    const input = document.getElementById("input");
    const checkButton = document.getElementById("check");
    const newGameButton = document.getElementById("newgame");
    const gameMessage = document.getElementById("gamemessage");
    const guessLeftDisplay = document.getElementById("versucheleft");
    const gifContainer = document.getElementById("gif");

    // Enter-Taste als Klick simulieren
    input.addEventListener("keydown", function (event) {
        if (event.key === "Enter") {
            guesschecker();
        }
    });

    // Event Listener für Buttons
    checkButton.addEventListener("click", guesschecker);
    newGameButton.addEventListener("click", gamereset);

    // Setzt die verbleibenden Versuche beim Start
    guessleft();

    function guesschecker() {
        let Usereingabe = parseInt(input.value, 10); // Konvertiere Eingabe in Zahl

        // Falls keine gültige Zahl eingegeben wurde
        if (isNaN(Usereingabe)) {
            gameMessage.innerHTML = "Bitte eine gültige Zahl eingeben!";
            return;
        }

        guess--;
        guesspositiv++;
        guessleft();

        if (Usereingabe === randomnumber) {
            gameMessage.innerHTML = `🎉 Gut geraten! Die richtige Zahl war: ${randomnumber}.<br>Du hast es in ${guesspositiv} Versuchen geschafft!`;
            gifContainer.innerHTML = "<img src='https://media1.giphy.com/media/JiC9wpHt3LhMNSlNAa/giphy.gif?cid=ecf05e472tot330tw8ihmnl2w53couctpx4j4g12s7hmodi4&rid=giphy.gif&ct=g' width='200'>";
            checkButton.disabled = true;
        } else if (Usereingabe > randomnumber) {
            gameMessage.innerHTML = "📉 Probier mal eine kleinere Zahl!";
        } else {
            gameMessage.innerHTML = "📈 Probier mal eine größere Zahl!";
        }

        if (guess <= 0) {
            gameMessage.innerHTML = `😢 Du hast leider verloren! Die gesuchte Zahl war ${randomnumber}.`;
            gifContainer.innerHTML = "<img src='https://media2.giphy.com/media/cr9vIO7NsP5cY/giphy.gif?cid=ecf05e47sgbct6b238r84dthol66xj4bmn2x604ezj2k1j7g&rid=giphy.gif&ct=g' width='200'>";
            checkButton.disabled = true;
        }
    }

    function guessleft() {
        guessLeftDisplay.innerHTML = guess;
    }

    function gamereset() {
        randomnumber = Math.floor(Math.random() * 100) + 1;
        console.log("Neue zufällige Zahl: ", randomnumber);
        guess = 10;
        guesspositiv = 0;
        input.value = "";
        gameMessage.innerHTML = "";
        gifContainer.innerHTML = "";
        checkButton.disabled = false;
        guessleft(); // Aktualisiert die Anzeige der verbleibenden Versuche
    }
});
