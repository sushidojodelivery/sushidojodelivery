<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1"/>
  <title>Sushi Dojo Delivery - Culinária Japonesa</title>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css">
</head>
<body class="bg-white text-gray-800">

  <!-- HEADER -->
  <header class="p-4 text-center bg-gray-100">
    <h1 class="text-2xl font-bold">Sushi Dojo Delivery - Culinária Japonesa</h1>
    <p>Entrega grátis • Pedido mínimo R$13 • 25‑40 min</p>
    <p>4,8 ⭐ (1.589 avaliações)</p>
    <div class="mt-2 font-semibold text-red-600">Aproveite: compre qualquer combo e ganhe um Temaki</div>
  </header>

  <!-- PROMOÇÃO COM CONTAGEM -->
  <section class="p-6 text-center">
    <h2 class="text-xl font-bold mb-2">Promoção quase esgotada!</h2>
    <div id="timer" class="text-3xl font-mono mb-4">13:23</div>
  </section>

  <!-- DESTAQUES COM CHECKOUT -->
  <section class="p-6">
    <h2 class="text-xl font-semibold mb-4">Destaques — Quase Esgotado!</h2>
    <div class="grid grid-cols-1 gap-4">
      <div class="p-4 bg-white rounded shadow">
        <h3 class="font-semibold">Combo Kumo — 24 peças</h3>
        <p>Sashimi, Nigiri e Uramaki de salmão e atum – de R$59,80 por <strong>R$29,90</strong></p>
        <button onclick="checkout('Combo Kumo — R$29,90')" class="bg-green-600 text-white px-4 py-2 mt-2 rounded">Comprar</button>
      </div>
      <div class="p-4 bg-white rounded shadow">
        <h3 class="font-semibold">Combo Takashi — 32 peças (entrega grátis)</h3>
        <p>Variados sashimis e uramakis – de R$79,80 por <strong>R$39,90</strong></p>
        <button onclick="checkout('Combo Takashi — R$39,90')" class="bg-green-600 text-white px-4 py-2 mt-2 rounded">Comprar</button>
      </div>
      <div class="p-4 bg-white rounded shadow">
        <h3 class="font-semibold">Combo Hikari — 78 peças (mais vendido)</h3>
        <p>Seleção premium de sashimi, nigiri e uramaki – de R$149,80 por <strong>R$59,90</strong></p>
        <button onclick="checkout('Combo Hikari — R$59,90')" class="bg-green-600 text-white px-4 py-2 mt-2 rounded">Comprar</button>
      </div>
    </div>
  </section>

  <!-- FORMULÁRIO DE CHECKOUT -->
  <section id="checkout-form" class="hidden p-6 bg-gray-100">
    <h2 class="text-xl font-bold mb-4">Finalizar Pedido</h2>
    <form onsubmit="enviarPedido(); return false;" class="grid gap-4 max-w-md mx-auto">
      <input type="text" id="comboSelecionado" class="hidden">
      <input type="text" id="nome" placeholder="Seu nome" required class="border p-2 rounded">
      <input type="text" id="endereco" placeholder="Endereço de entrega" required class="border p-2 rounded">
      <input type="text" id="telefone" placeholder="Telefone para contato" required class="border p-2 rounded">
      <select id="pagamento" required class="border p-2 rounded">
        <option value="">Forma de pagamento</option>
        <option value="Pix">Pix</option>
        <option value="Dinheiro">Dinheiro</option>
        <option value="Cartão">Cartão</option>
      </select>
      <button type="submit" class="bg-red-600 text-white px-4 py-2 rounded">Confirmar Pedido</button>
    </form>
  </section>

  <!-- CONFIRMAÇÃO PIX -->
  <section id="confirmacao" class="hidden p-6 text-center">
    <h2 class="text-xl font-bold mb-2">Pedido Confirmado! 🍱</h2>
    <p class="mb-2">Faça o pagamento via <strong>PIX</strong> para:</p>
    <div class="text-lg font-mono bg-white border rounded p-2 inline-block mb-2">sushidojodelivery</div>
    <p class="text-sm text-gray-600">Após o pagamento, seu pedido será preparado e enviado.</p>
  </section>

  <!-- PROVA SOCIAL -->
  <section class="p-6 text-center">
    <h2 class="text-xl font-semibold mb-4">O que nossos clientes dizem</h2>
    <p>⭐⭐⭐⭐⭐ “Chegou fresquinho, bem embalado e do jeito que pedi.”</p>
    <p>⭐⭐⭐⭐⭐ “Melhor custo‑benefício que já vi! Sushi bom e preço sensacional.”</p>
    <p>⭐⭐⭐⭐⭐ “Achei pequeno, mas vem bem servido. Qualidade absurda.”</p>
  </section>

  <footer class="p-4 text-center text-sm text-gray-500">
    © 2025 Sushi Dojo Delivery. Todos os direitos reservados.
  </footer>

  <!-- SCRIPT TIMER + CHECKOUT -->
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

    function checkout(combo) {
      document.getElementById('checkout-form').classList.remove('hidden');
      document.getElementById('checkout-form').scrollIntoView({ behavior: 'smooth' });
      document.getElementById('comboSelecionado').value = combo;
    }

    function enviarPedido() {
      document.getElementById('checkout-form').classList.add('hidden');
      document.getElementById('confirmacao').classList.remove('hidden');
      document.getElementById('confirmacao').scrollIntoView({ behavior: 'smooth' });
    }
  </script>
</body>
</html>
