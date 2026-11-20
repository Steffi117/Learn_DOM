select/option:
select ist Auswahlfeld
Option ist Auswahlmöglichkeit

<select id="color">
  <option value="red">Red</option>
  <option value="green">Green</option>
  <option value="blue">Blue</option>
</select>
mit Select können Optionen abgefragt und geändert werden

Finden:
Zuerst zu ID/HTML:
const colorSelect = document.getElementById("color");
colorSelect.value - auf Eigenschaften Zugreifen und wenn danach = "green" wird die Eigenschaft geändert
colorSelect.selectedIndex – Position der Auswahl: 0 für die erste Option, 1 für die zweite,...
colorSelect.options – alle Optionen im Auswahlfeld

<option value="red">Red</option>
bei Option wird JavaScriptwert und Text des Auswahlfeldes extra behandelt



form:
form ist ein Formular
In einem Formular können Eingaben gesammelt und abgeschickt werden

<form id="contactForm">
  <label for="name">Name:</label>
  <input id="name" name="name" type="text">
  <button type="submit">Absenden</button>
</form>

Finden:
Zuerst zu ID/HTML:
const contactForm = document.getElementById("contactForm");

contactForm.elements - alle Eingabefelder und Buttons im Formular

Eingabefelder können über ihre ID oder ihren Namen gefunden werden:
const nameInput = document.getElementById("name");
nameInput.value - aktueller Text im Eingabefeld; mit = "Anna" wird er geändert

Formular absenden:
contactForm.addEventListener("submit", (event) => {
  event.preventDefault();
  const formData = new FormData(contactForm);
  const name = formData.get("name");
});

submit wird ausgelöst, wenn das Formular abgeschickt wird
event.preventDefault() verhindert das normale Abschicken und Neuladen der Seite
FormData sammelt die Formularwerte; dafür brauchen Eingabefelder ein name-Attribut



button:
button ist eine Schaltfläche, die angeklickt werden kann
Mit JavaScript kann auf einen Klick reagiert werden

<button id="helloButton" type="button">Klick mich</button>

Finden:
Zuerst zu ID/HTML:
const helloButton = document.getElementById("helloButton");

Auf Klick reagieren:
helloButton.addEventListener("click", () => {
  helloButton.textContent = "Geklickt!";
});

click wird ausgelöst, wenn die Schaltfläche angeklickt wird
textContent ist der Text auf der Schaltfläche und kann geändert werden

Button-Arten:
type="button" - normale Schaltfläche, führt beim Klicken keine Formularaktion aus
type="submit" - schickt ein Formular ab
type="reset" - setzt die Formularfelder auf ihre Anfangswerte zurück
Innerhalb eines Formulars sollte der gewünschte type angegeben werden



input:
input ist ein Eingabefeld
Je nach type können Text, Zahlen oder andere Werte eingegeben werden

<label for="email">E-Mail:</label>
<input id="email" name="email" type="email">

Finden:
Zuerst zu ID/HTML:
const emailInput = document.getElementById("email");

emailInput.value - aktueller Inhalt des Eingabefeldes
emailInput.value = "name@example.com" - ändert den Inhalt des Eingabefeldes

Auf Eingaben reagieren:
emailInput.addEventListener("input", () => {
  console.log(emailInput.value);
});

input wird ausgelöst, wenn der Inhalt des Eingabefeldes geändert wird
name wird zum Beispiel benötigt, damit der Wert beim Absenden des Formulars zugeordnet werden kann

Häufige input-Typen:
type="text" - einzeiliger Text
type="email" - E-Mail-Adresse
type="number" - Zahl
type="checkbox" - Kontrollkästchen; checked zeigt an, ob es ausgewählt ist



div:
div ist ein allgemeiner Bereich auf einer Webseite
Es gruppiert HTML-Elemente, hat aber selbst keine besondere Bedeutung - für Gruppierung und Gestaltung von Elementen

<div id="message">
  <p>Hallo!</p>
</div>

Finden:
Zuerst zu ID/HTML:
const messageDiv = document.getElementById("message");

Inhalt ändern:
messageDiv.textContent = "Nachricht geändert";

textContent - liest oder ändert den Text im div
innerHTML - liest oder ändert HTML-Inhalte innerhalb des div



table:
table ist eine Tabelle - zeigt Daten in Zeilen und Spalten
tr ist eine Zeile, th eine Überschriftzelle und td eine normale Zelle

<table id="fruitTable">
  <tr>
    <th>Obst</th>
    <th>Anzahl</th>
  </tr>
  <tr>
    <td>Apfel</td>
    <td>3</td>
  </tr>
</table>

Finden:
Zuerst zu ID/HTML:
const fruitTable = document.getElementById("fruitTable");

fruitTable.rows - alle Zeilen der Tabelle
fruitTable.rows[1] - die zweite Zeile (Positionen beginnen bei 0)
fruitTable.rows[1].cells[0] - die erste Zelle in der zweiten Zeile

Zelleninhalt lesen oder ändern:
fruitTable.rows[1].cells[0].textContent = "Birne";

textContent - liest oder ändert den Text einer Zelle



ul:
ul ist eine ungeordnete Liste - Einträge werden normalerweise mit Punkten angezeigt
ul eignet sich für Listen, bei denen die Reihenfolge keine besondere Bedeutung hat
Für nummerierte Listen wird ol statt ul verwendet
li ist ein einzelner Eintrag in der Liste

<ul id="fruitList">
  <li>Apfel</li>
  <li>Banane</li>
</ul>

Finden:
Zuerst zu ID/HTML:
const fruitList = document.getElementById("fruitList");

fruitList.children - alle Einträge (li-Elemente) in der Liste
fruitList.children[0] - der erste Eintrag (Positionen beginnen bei 0)

Eintrag ändern:
fruitList.children[0].textContent = "Birne";

Neuen Eintrag hinzufügen:
const newItem = document.createElement("li");
newItem.textContent = "Orange";
fruitList.append(newItem);



canvas:
canvas ist eine Zeichenfläche auf einer Webseite
Mit JavaScript können darauf Formen und Bilder gezeichnet werden

<canvas id="drawing" width="300" height="150"></canvas>

Finden:
Zuerst zu ID/HTML:
const drawing = document.getElementById("drawing");

Zeichenwerkzeug holen:
const context = drawing.getContext("2d");

Rechteck zeichnen:
context.fillStyle = "blue";
context.fillRect(20, 20, 100, 50);

getContext("2d") holt das Zeichenwerkzeug für zweidimensionale Zeichnungen
fillStyle legt die Füllfarbe fest
fillRect(x, y, breite, höhe) zeichnet ein ausgefülltes Rechteck

