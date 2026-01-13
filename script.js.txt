document.getElementById("appointmentForm").addEventListener("submit", function(event) {
  event.preventDefault();

  const name = document.getElementById("userName").value.trim();
  const phone = document.getElementById("userPhone").value.trim();
  const messageBox = document.getElementById("formMessage");

  if (name === "" || phone === "") {
    messageBox.style.color = "red";
    messageBox.textContent = "Please enter your name and phone number.";
  } else {
    messageBox.style.color = "green";
    messageBox.textContent = "Thank you! Our team will contact you soon.";
    this.reset();
  }
});

document.getElementById("medicineSearch").addEventListener("keyup", function() {
  const searchText = this.value.toLowerCase();
  const medicines = document.querySelectorAll("#medicineList li");

  medicines.forEach(medicine => {
    medicine.style.display = medicine.textContent.toLowerCase().includes(searchText)
      ? "block"
      : "none";
  });
});
