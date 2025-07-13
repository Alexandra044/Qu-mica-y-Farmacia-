<!DOCTYPE html><html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Malla Interactiva Química y Farmacia</title>
  <style>
    body {
      font-family: sans-serif;
      background-color: #f3f3f3;
      padding: 20px;
    }
    .grid {
      display: flex;
      gap: 20px;
      overflow-x: auto;
    }
    .semester {
      background: white;
      padding: 10px;
      border-radius: 10px;
      box-shadow: 0 0 5px rgba(0,0,0,0.1);
      min-width: 200px;
    }
    .semester h3 {
      text-align: center;
    }
    .course {
      background: #eee;
      padding: 5px;
      border-radius: 5px;
      margin: 5px 0;
      cursor: pointer;
      transition: background 0.2s;
    }
    .course:hover {
      background: #cce5ff;
    }
    .unlocked {
      background: #d4edda !important;
    }
    .locked {
      opacity: 0.5;
    }
  </style>
</head>
<body>
  <h1>Malla Interactiva Química y Farmacia - UCN</h1>
  <p>Haz clic en un ramo para ver cuáles desbloquea.</p>
  <div class="grid" id="malla"></div>  <script>
    const courses = {
      'Anatomía': ['Biología'],
      'Introducción a la Farmacia I': ['Introducción a la Farmacia II'],
      'Álgebra': ['Cálculo'],
      'Inglés 1': ['Inglés 2'],
      'Química General I': ['Química General II'],
      'Biología': ['Fisiopatología I'],
      'Química General II': ['Fisicoquímica Farmacéutica', 'Química Farmacéutica Org. I'],
      'Biofísica': ['Fisiopatología II'],
      'Fisiopatología I': ['Fisiopatología II', 'Inmunología'],
      'Fisicoquímica Farmacéutica': ['Bioquímica'],
      'Química Farmacéutica Org. I': ['Química Farmacéutica Org. II'],
      'Fisiopatología II': ['Microbiología'],
      'Analítica Farmacéutica': ['Taller Literatura Científica'],
      'Química Farmacéutica Org. II': ['Farmacología I'],
      'Bioquímica': ['Química Funcional'],
      'Inmunología': ['Microbiología'],
      'Taller Literatura Científica': ['Marketing Farmacéutico'],
      'Microbiología': ['Bioquímica Clínica'],
      'Química Funcional': ['Farmacoquímica II'],
      'Análisis Farmacéutico Instrume.': ['Tecnología Farmacéutica I'],
      'Farmacología I': ['Farmacología II'],
      'Bioquímica Clínica': ['Farmacia Asistencial'],
      'Tecnología Farmacéutica I': ['Tecnología Farmacéutica II'],
      'Farmacología II': ['Atención Farmacéutica', 'Bioestadística'],
      'Marketing Farmacéutico': ['Biofarmacia'],
      'Farmacoquímica I': ['Farmacoquímica II'],
      'Farmacia Asistencial': ['Legislación Farmacéutica'],
      'Tecnología Farmacéutica II': ['Farmacia Clínica'],
      'Atención Farmacéutica': ['Farmacia Asistencial'],
      'Biofarmacia': ['Farmacognosia'],
      'Integrador I: Taller de Empre.': ['Integrador II: Taller C.C.'],
      'Farmacia Clínica': ['Toxicología'],
      'Taller Farmacia Asistencial': ['Unidad de Investigación I'],
      'Farmacognosia': ['Toxicología'],
      'Integrador II: Taller C.C.': ['Integrador III: taller Atención.'],
      'Internado Farmacia Clínica': ['Unidad de Investigación II'],
      'Integrador III: taller Atención.': ['Unidad de Investigación II'],
      'Toxicología': ['Unidad de Investigación II'],
      'Unidad de Investigación I': ['Unidad de Investigación II']
    };

    const semesters = [
      ['Anatomía', 'Introducción a la Farmacia I', 'Álgebra', 'Inglés 1', 'Química General I', 'Introducción al Método Científico', 'Identidad, Univ. y Eq. de Género'],
      ['Biología', 'Introducción a la Farmacia II', 'Cálculo', 'Inglés 2', 'Química General II', 'Biofísica'],
      ['Fisiopatología I', 'Fisicoquímica Farmacéutica', 'Química Farmacéutica Org. I', 'Ser humano', 'Acondicionamiento Físico', 'Comunicación y desarrollo personal', 'Formación General Glob.'],
      ['Fisiopatología II', 'Formación Teológico', 'Analítica Farmacéutica', 'Química Farmacéutica Org. II', 'Bioquímica', 'Formación General Glob.', 'Inmunología'],
      ['Taller Literatura Científica', 'Microbiología', 'Química Funcional', 'Análisis Farmacéutico Instrume.', 'Farmacología I', 'Adm. Y Gestión en Farmacia'],
      ['Bioquímica Clínica', 'Tecnología Farmacéutica I', 'Farmacología II', 'Formación Profesional Electiva', 'Marketing Farmacéutico', 'Farmacoquímica I'],
      ['Farmacoquímica II', 'Tecnología Farmacéutica II', 'Atención Farmacéutica', 'Farmacia Asistencial', 'Biofarmacia', 'Integrador I: Taller de Empre.'],
      ['Farmacia Clínica', 'Bioestadística', 'Legislación Farmacéutica', 'Formación Profesional Electiva', 'Taller Farmacia Asistencial', 'Farmacognosia', 'Integrador II: Taller C.C.'],
      ['Formación General Electiva', 'Internado Farmacia Clínica', 'Formación General Teológica', 'Integrador III: taller Atención.', 'Toxicología', 'Unidad de Investigación I'],
      ['Unidad de Investigación II']
    ];

    const malla = document.getElementById('malla');

    semesters.forEach((sem, index) => {
      const semDiv = document.createElement('div');
      semDiv.className = 'semester';
      semDiv.innerHTML = `<h3>Semestre ${index + 1}</h3>`;

      sem.forEach(course => {
        const div = document.createElement('div');
        div.className = 'course';
        div.innerText = course;
        div.onclick = () => unlock(course);
        semDiv.appendChild(div);
      });

      malla.appendChild(semDiv);
    });

    function unlock(courseName) {
      document.querySelectorAll('.course').forEach(c => c.classList.remove('unlocked'));
      const unlocked = courses[courseName] || [];
      unlocked.forEach(name => {
        document.querySelectorAll('.course').forEach(div => {
          if (div.innerText === name) {
            div.classList.add('unlocked');
          }
        });
      });
    }
  </script></body>
</html>
