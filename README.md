<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1"/>
  <title>Hokkai Delivery - Culinária Japonesa</title>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css">
</head>
<body class="bg-white text-gray-800">

  <!-- HEADER -->
  <header class="p-4 text-center bg-gray-100">
    <h1 class="text-2xl font-bold">Hokkai Delivery - Culinária Japonesa</h1>
    <p>Entrega grátis • Pedido mínimo R$13 • 25‑40 min</p>
    <p>4,8 ⭐ (1.589 avaliações)</p>
    <div class="mt-2 font-semibold text-red-600">Aproveite: compre qualquer combo e ganhe um Temaki</div>
  </header>

  <!-- PROMOÇÃO COM CONTAGEM -->
  <section class="p-6 text-center">
    <h2 class="text-xl font-bold mb-2">Promoção quase esgotada!</h2>
    <div id="timer" class="text-3xl font-mono mb-4">13:23</div>
  </section>

  <!-- DESTAQUES -->
  <section class="p-6">
    <h2 class="text-xl font-semibold mb-4">Destaques — Quase Esgotado!</h2>
    <div class="grid grid-cols-1 gap-4">
      <div class="p-4 bg-white rounded shadow">
        <h3 class="font-semibold">Combo Kumo — 24 peças</h3>
        <p>Sashimi, Nigiri e Uramaki de salmão e atum – de R$59,80 por <strong>R$29,90</strong></p>
      </div>
      <div class="p-4 bg-white rounded shadow">
        <h3 class="font-semibold">Combo Takashi — 32 peças (entrega grátis)</h3>
        <p>Variados sashimis e uramakis – de R$79,80 por <strong>R$39,90</strong></p>
      </div>
      <div class="p-4 bg-white rounded shadow">
        <h3 class="font-semibold">Combo Hikari — 78 peças (mais vendido)</h3>
        <p>Seleção premium de sashimi, nigiri e uramaki – de R$149,80 por <strong>R$59,90</strong></p>
      </div>
    </div>
  </section>

  <!-- COMBINADOS ESPECIAIS -->
  <section class="p-6 bg-gray-50">
    <h2 class="text-xl font-semibold mb-4">Combinados Especiais</h2>
    <ul class="space-y-3 list-disc list-inside">
      <li><strong>Senshi — 28 peças</strong> por R$149,90</li>
      <li><strong>Bushido — 48 peças</strong> por R$219,90</li>
      <li><strong>Imperador — 50 peças</strong> por R$319,90</li>
    </ul>
  </section>

  <!-- YAKISOBAS -->
  <section class="p-6">
    <h2 class="text-xl font-semibold mb-4">Yakisobas</h2>
    <ul class="space-y-2 list-disc list-inside">
      <li>Macarrão Frito – R$14,90</li>
      <li>Yakisoba Vegetariano – R$74,90</li>
      <li>Yakisoba Camarão – R$89,90</li>
      <li>Yakisoba Especial – R$84,90</li>
      <li>Yakisoba Mignon – R$89,90</li>
      <li>Yakisoba Lula – R$82,90</li>
      <li>Yakisoba Misto – R$82,90</li>
    </ul>
  </section>

  <!-- PROVA SOCIAL -->
  <section class="p-6 text-center">
    <h2 class="text-xl font-semibold mb-4">O que nossos clientes dizem</h2>
    <p>⭐⭐⭐⭐⭐ “Chegou fresquinho, bem embalado e do jeito que pedi.”</p>
    <p>⭐⭐⭐⭐⭐ “Melhor custo‑benefício que já vi! Sushi bom e preço sensacional.”</p>
    <p>⭐⭐⭐⭐⭐ “Achei pequeno, mas vem bem servido. Qualidade absurda.”</p>
  </section>

  <footer class="p-4 text-center text-sm text-gray-500">
    © 2025 Hokkai Delivery. Todos os direitos reservados.
  </footer>

  <!-- SCRIPT TIMER -->
  <script>
    let sec = 13*60+23;
    const timer = document.getElementById('timer');
    setInterval(() => {
      sec--;
      const m = String(Math.floor(sec/60)).padStart(2,'0');
      const s = String(sec%60).padStart(2,'0');
      timer.textContent = m+':' + s;
      if (sec<=0) sec=0;
    },1000);
  </script>

</body>
</html>
