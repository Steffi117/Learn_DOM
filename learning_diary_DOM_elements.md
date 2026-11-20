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
