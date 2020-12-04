**Requiring  an input**
<form action="/example.html" method="POST">
  <label for="allergies">Do you have any dietary restrictions?</label>
  <br>
  <input id="allergies" name="allergies" type="text" required>
  <br>
  <input type="submit" value="Submit">
</form>


**index**
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <title>Number Guessing</title>
    <link rel="stylesheet" href="style.css" type="text/css">
    <link href="https://fonts.googleapis.com/css?family=Spicy+Rice" rel="stylesheet">
  </head>
  <body>
    <section class="overlay">
      <h1>Guess the right number!</h1>
      <form action="check.html" method="GET">
        <!--Add a required attribute to the input element-->
        <label for="guess">Enter a number between 1-10:</label>
        <br>
        <input type="number" name="guess" id="guess" required>
        <br>
        <input type="submit" id="submission" value="Submit">
      </form>
    </section>
  </body>
</html>

**check.html**
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <title>Required</title>
    <link rel="stylesheet" href="style.css" type="text/css">
    <link href="https://fonts.googleapis.com/css?family=Spicy+Rice" rel="stylesheet">
    <script type="text/javascript" src="numCheck.js" defer></script>
  </head>
  <body>
    <section class="overlay">
      <h1 id="check"></h1>
      <a href="index.html">Go back</a>
    </section>
  </body>
</html>

**numCheck.js**
const check = document.getElementById('check');
const guess = new URLSearchParams(window.location.search);
const num = guess.get('guess');
// const randomNum = Math.floor(Math.random() * 10) + 1;

if(num === "3"){
  check.innerHTML = 'You guessed correctly!';
} else {
  check.innerHTML = `Try again...`;
}


**style.css**
body {
  background-color: #59CD90;
  color: #3FA7D6;
  font-family: Arial;
  padding-bottom: 20%;
}

form {
  line-height: 25px;
}

h1 {
  font-family: Spicy Rice, Arial;
  font-size: 4em;
  overflow: break;
}

.overlay {
  width: 80%;
  min-width: 30%;
  margin: 3% auto;
  display: block;
  padding: 2%;
  height: 90vh;
  background-color: rgba(255, 255, 255, 0.9);
  border-radius: 40px;
  text-align: center;
  overflow: auto;
}

@media only screen and (max-width: 440px) {
  h1 {
    font-size: 3.5em;
  }
}


---

**set min and max**
<form action="/example.html" method="POST">
  <label for="guests">Enter # of guests:</label>
  <input id="guests" name="guests" type="number" min="1" max="4">
  <input type="submit" value="Submit">
</form>


---

**checking text length**
<form action="/example.html" method="POST">
  <label for="summary">Summarize your feelings in less than 250 characters</label>
  <input id="summary" name="summary" type="text" minlength="5" maxlength="250" required>
  <input type="submit" value="Submit">
</form>


**matching a pattern**

We could use the regex: [0-9]{14,16} which checks that the user provided only numbers and that they entered at least 14 digits and at most 16 digits.
<form action="/example.html" method="POST">
  <label for="payment">Credit Card Number (no spaces):</label>
  <br>
  <input id="payment" name="payment" type="text" required pattern="[0-9]{14,16}">
  <input type="submit" value="Submit">
</form>

**index**
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <title>Sign Up Page</title>
    <link rel="stylesheet" href="style.css" type="text/css">
    <link href="https://fonts.googleapis.com/css?family=Fjalla+One" rel="stylesheet">
  </head>
  <body>
    <section class="overlay">
			<h1>Sign Up</h1>
      <p>Create an account:</p>
      <form action="submission.html" method="GET">
        <label for="username">Username:</label>
        <br>
				<!--Add the pattern attribute to the input below-->
				<input id="username" name="username" type="text" required minlength="3" maxlength="15" pattern="[a-zA-Z0-9]+">
        <br>
        <label for="pw">Password:</label>
        <br>
				<input id="pw" name="pw" type="password" required minlength="8" maxlength="15">
        <br>
        <input type="submit" value="Submit">
      </form>
    </section>
  </body>
</html>


**submission.html**
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <title>Required</title>
    <link rel="stylesheet" href="style.css" type="text/css">
    <link href="https://fonts.googleapis.com/css?family=Fjalla+One" rel="stylesheet">
    <script type="text/javascript" src="login.js" defer></script>
  </head>
  <body>
    <section class="overlay">
      <h1 id="message"></h1>
      <a href="index.html">Go back</a>
    </section>
  </body>
</html>


**login.js**
const message = document.getElementById('message');
const param = new URLSearchParams(window.location.search);
const username = param.get('username');
const pw = param.get('pw');

if(username.toLowerCase() === 'codecademy' && pw === 'ilovecoding'){
  message.innerHTML = 'We love coding too!';
} else if(!username || !pw){
  message.innerHTML = 'Add some client-side validation!';
} else {
  message.innerHTML = 'Hurray for client-side validation!';
}


**style.css**
body {
  background-color: #59CD90;
  color: #3FA7D6;
  font-family: "Fjalla One", Arial;
}

form {
  line-height: 25px;
}

h1 {
  font-size: 3em;
  overflow: break;
}

.overlay {
  width: 80%;
  min-width: 30%;
  margin: 3% auto;
  display: block;
  padding: 2%;
  height: 90vh;
  background-color: rgba(255, 255, 255, 0.9);
  border-radius: 40px;
  text-align: center;
}
