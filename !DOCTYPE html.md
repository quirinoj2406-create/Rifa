<!DOCTYPE html>  
<html lang="es">  
<head>  
<meta charset="UTF-8">  
<title>Rifa entre Amigos</title>  
<meta name="viewport" content="width=device-width, initial-scale=1.0">  
  
<style>  
body {  
  margin: 0;  
  font-family: "Georgia", serif;  
  background: #0f0f0f;  
  color: #e6c36a;  
}  
  
header {  
  text-align: center;  
  padding: 35px 20px;  
  border-bottom: 1px solid #e6c36a;  
}  
  
header h1 {  
  margin: 0;  
  font-weight: normal;  
  letter-spacing: 2px;  
}  
  
header p {  
  margin-top: 8px;  
  font-size: 16px;  
}  
  
main {  
  max-width: 1000px;  
  margin: 30px auto;  
  padding: 20px;  
}  
  
article {  
  background: #151515;  
  padding: 30px;  
  border-radius: 8px;  
}  
  
.info p {  
  margin: 8px 0;  
  font-size: 16px;  
}  
  
h2 {  
  margin-top: 30px;  
  font-weight: normal;  
  letter-spacing: 1px;  
}  
  
.numbers {  
  display: grid;  
  grid-template-columns: repeat(auto-fill, minmax(55px, 1fr));  
  gap: 12px;  
  margin-top: 25px;  
}  
  
.number {  
  padding: 14px 0;  
  text-align: center;  
  border: 1px solid #e6c36a;  
  border-radius: 6px;  
  cursor: pointer;  
  background: transparent;  
  color: #e6c36a;  
  font-size: 16px;  
  user-select: none;  
}  
  
.number.vendido {  
  background: #e6c36a;  
  color: #0f0f0f;  
  text-decoration: line-through;  
  font-weight: bold;  
}  
  
footer {  
  margin-top: 35px;  
  text-align: center;  
  font-size: 13px;  
  opacity: 0.8;  
}  
</style>  
</head>  
  
<body>  
  
<header>  
  <h1>Rifa entre Amigos</h1>  
  <p>Arracadas de 10 kilates</p>  
</header>  
  
<main>  
<article>  
  
<div class="info">  
  <p><strong>Premio:</strong> Arracadas de 10 kilates</p>  
  <p><strong>Costo del boleto:</strong> $200 MXN</p>  
  <p><strong>Números disponibles:</strong> 100</p>  
  <p><strong>Fecha del sorteo:</strong> 1 de mayo</p>  
</div>  
  
<h2>Números</h2>  
  
<div class="numbers" id="numbers"></div>  
  
</article>  
  
<footer>  
  © 2026 — Rifa entre amigos  
</footer>  
</main>  
  
<script>  
const container = document.getElementById("numbers");  
  
for (let i = 1; i <= 100; i++) {  
  const div = document.createElement("div");  
  div.className = "number";  
  div.textContent = i;  
  
  if (localStorage.getItem("rifa_" + i) === "vendido") {  
    div.classList.add("vendido");  
  }  
  
  div.addEventListener("click", () => {  
    div.classList.toggle("vendido");  
  
    if (div.classList.contains("vendido")) {  
      localStorage.setItem("rifa_" + i, "vendido");  
    } else {  
      localStorage.removeItem("rifa_" + i);  
    }  
  });  
  
  container.appendChild(div);  
}  
</script>  
  
</body>  
</html>  
