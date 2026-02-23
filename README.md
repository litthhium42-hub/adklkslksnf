# school
<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Meow Language School</title>

<style>

body {
  margin: 0;
  font-family: "Arial", sans-serif;
  background: linear-gradient(135deg, #fff0f5, #ffe4ec);
  overflow-x: hidden;
  color: #555;
}

/* Мыльные круги */
.bubble {
  position: fixed;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(255,182,193,0.5), rgba(255,192,203,0.15));
  animation: float 25s infinite linear;
  z-index: -1;
}

@keyframes float {
  from { transform: translateY(100vh); }
  to { transform: translateY(-120vh); }
}

/* Золотые полоски */
.gold-line {
  height: 2px;
  background: linear-gradient(to right, transparent, gold, transparent);
  margin: 50px auto;
  width: 70%;
}

/* Лапки */
.paws {
  position: fixed;
  bottom: 15px;
  right: 15px;
  font-size: 28px;
  opacity: 0.15;
}

/* Шапка */
header {
  text-align: center;
  padding: 90px 20px 60px;
}

h1 {
  font-size: 46px;
  color: #ff69b4;
}

.sticker {
  display: inline-block;
  background: #ffb6c1;
  padding: 14px 28px;
  border-radius: 40px;
  font-size: 18px;
  color: white;
  margin-top: 20px;
  box-shadow: 0 5px 20px rgba(0,0,0,0.1);
}

/* Кнопки */
.buttons {
  display: flex;
  justify-content: center;
  gap: 20px;
  flex-wrap: wrap;
  margin-top: 40px;
}

button {
  padding: 15px 28px;
  border-radius: 30px;
  border: 1px solid gold;
  background: #ffffffcc;
  font-size: 18px;
  cursor: pointer;
  transition: 0.3s;
}

button:hover {
  background: #ffd6e8;
  transform: scale(1.05);
}

/* Разделы */
.section {
  padding: 70px 20px;
  text-align: center;
}

.section h2 {
  color: #ff69b4;
  margin-bottom: 30px;
}

.card {
  background: rgba(255,255,255,0.85);
  border: 1px solid #eee;
  border-radius: 20px;
  padding: 25px;
  margin: 15px auto;
  max-width: 500px;
  box-shadow: 0 5px 15px rgba(0,0,0,0.05);
}

/* Прайс */
.price-card {
  font-size: 20px;
  font-weight: bold;
  color: #444;
}

/* Статистика */
.stats {
  background: rgba(255,255,255,0.85);
  padding: 20px;
  border-radius: 20px;
  width: 320px;
  margin: 40px auto;
  border: 1px solid silver;
}

</style>
</head>

<body>

<!-- Мыльные круги -->
<div class="bubble" style="width:200px;height:200px;left:15%;animation-duration:30s;"></div>
<div class="bubble" style="width:150px;height:150px;left:75%;animation-duration:22s;"></div>
<div class="bubble" style="width:250px;height:250px;left:45%;animation-duration:35s;"></div>

<header>
<h1>Meow Language School 💗</h1>
<div class="sticker">💖 our ints: meowLanguage</div>

<div class="buttons">
<button onclick="clickLang('french')">🇫🇷 Французский</button>
<button onclick="clickLang('english')">🇬🇧 Английский</button>
<button onclick="clickLang('german')">🇩🇪 Немецкий</button>
</div>

<button style="margin-top:30px;background:#fff8dc;" onclick="consult()">Получить консультацию 💬</button>

</header>

<div class="gold-line"></div>

<div class="section">
<h2>Наши преподаватели</h2>
<div class="card">👩‍🏫 Носители языка с опытом 5+ лет</div>
<div class="card">🎓 Международные сертификаты</div>
</div>

<div class="gold-line"></div>

<div class="section">
<h2>Локация</h2>
<div class="card">📍 Центр города + уютные розовые аудитории</div>
</div>

<div class="gold-line"></div>

<div class="section">
<h2>Онлайн занятия</h2>
<div class="card">💻 Zoom / Google Meet / Индивидуальные уроки</div>
</div>

<div class="gold-line"></div>

<div class="section">
<h2>Прайс</h2>
<div class="card price-card">🇫🇷 Французский язык: 10$</div>
<div class="card price-card">🇩🇪 Немецкий язык: 10$</div>
<div class="card price-card">🇬🇧 Английский язык: 10$</div>
</div>

<div class="stats">
<h3>📊 Статистика</h3>
<p>Посетителей: <span id="visits"></span></p>
<p>Французский: <span id="frenchCount"></span></p>
<p>Английский: <span id="englishCount"></span></p>
<p>Немецкий: <span id="germanCount"></span></p>
<p>Консультации: <span id="consultCount"></span></p>
</div>

<div class="paws">🐾 🐾 🐾</div>

<script>

localStorage.visits = Number(localStorage.visits || 0) + 1;

function updateStats(){
  document.getElementById("visits").innerText = localStorage.visits || 0;
  document.getElementById("frenchCount").innerText = localStorage.french || 0;
  document.getElementById("englishCount").innerText = localStorage.english || 0;
  document.getElementById("germanCount").innerText = localStorage.german || 0;
  document.getElementById("consultCount").innerText = localStorage.consult || 0;
}

function clickLang(lang){
  localStorage[lang] = Number(localStorage[lang] || 0) + 1;
  updateStats();
  alert("Спасибо за интерес 💗 Мы скоро свяжемся с вами!");
}

function consult(){
  localStorage.consult = Number(localStorage.consult || 0) + 1;
  updateStats();
  alert("Консультация оформлена 💬");
}

updateStats();

</script>

</body>
</html>
