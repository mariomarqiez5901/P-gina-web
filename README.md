# P-gina-web
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Perfil Profesional - [Nombre Completo]</title>
  <link rel="stylesheet" href="css/styles.css">
</head>
<body>
  <header>
    <div class="profile-picture">
      <img src="img/profile.jpg" alt="Foto de perfil de [Nombre Completo]">
    </div>
    <h1 id="name">[Nombre Completo]</h1>
    <p id="position">[Posición Actual]</p>
    <p>Ubicación: <span id="location">[Ciudad, País]</span></p>
    <button id="contactButton">Mostrar información de contacto</button>
  </header>

  <section class="about">
    <h2>Acerca de mí</h2>
    <p id="about">[Breve descripción profesional o presentación personal]</p>
  </section>

  <section class="experience">
    <h2>Experiencia Profesional</h2>
    <ul id="experienceList">
      <!-- Las experiencias se cargarán desde JavaScript -->
    </ul>
  </section>

  <section class="skills">
    <h2>Habilidades</h2>
    <ul id="skillsList">
      <!-- Las habilidades se cargarán desde JavaScript -->
    </ul>
  </section>

  <section id="contactInfo" class="contact" style="display: none;">
    <h2>Contacto</h2>
    <p>Email: [correo@example.com]</p>
    <p>LinkedIn: <a href="https://linkedin.com/in/[nombre-perfil]" target="_blank">Visita mi perfil</a></p>
  </section>

  <script src="js/main.js"></script>
</body>
</html>body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f4f4f4;
  color: #333;
}

header {
  background-color: #0073b1;
  color: #fff;
  text-align: center;
  padding: 2rem 1rem;
}

.profile-picture img {
  border-radius: 50%;
  width: 150px;
  height: 150px;
  object-fit: cover;
  border: 4px solid #fff;
}

h1, h2 {
  margin-top: 0;
}

section {
  margin: 1rem 2rem;
}

.about, .experience, .skills, .contact {
  background-color: #fff;
  border-radius: 8px;
  padding: 1.5rem;
  margin-bottom: 1rem;
}  
// Datos de experiencia y habilidades
const experienceData = [
  {
    title: "Desarrollador Front-End",
    company: "Empresa XYZ",
    dates: "Enero 2020 - Presente",
    description: "Responsable del desarrollo de interfaces y optimización de UX."
  },
  {
    title: "Analista de Datos",
    company: "Empresa ABC",
    dates: "Mayo 2018 - Diciembre 2019",
    description: "Analicé datos de ventas y generé informes para mejorar la estrategia comercial."
  }
];

const skillsData = ["JavaScript", "HTML", "CSS", "React", "Análisis de datos"];

// Cargar experiencia y habilidades en el DOM
const experienceList = document.getElementById("experienceList");
experienceData.forEach(exp => {
  const listItem = document.createElement("li");
  listItem.innerHTML = `
    <strong>${exp.title}</strong> en <em>${exp.company}</em> <br>
    <small>${exp.dates}</small> <br>
    <p>${exp.description}</p>
  `;
  experienceList.appendChild(listItem);
});

const skillsList = document.getElementById("skillsList");
skillsData.forEach(skill => {
  const listItem = document.createElement("li");
  listItem.textContent = skill;
  skillsList.appendChild(listItem);
});

// Mostrar/Ocultar información de contacto
const toggleContactBtn = document.getElementById("toggleContactBtn");
const contactSection = document.getElementById("contact");

toggleContactBtn.addEventListener("click", () => {
  if (contactSection.classList.contains("hidden")) {
    contactSection.classList.remove("hidden");
    toggleContactBtn.textContent = "Ocultar información de contacto";
  } else {
    contactSection.classList.add("hidden");
    toggleContactBtn.textContent = "Mostrar información de contacto";
  }
});


