<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Sushi Dojo Delivery</title>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css">

  <!-- Meta Pixel Code -->
  <script>
    !function(f,b,e,v,n,t,s)
    {if(f.fbq)return;n=f.fbq=function(){n.callMethod?
    n.callMethod.apply(n,arguments):n.queue.push(arguments)};
    if(!f._fbq)f._fbq=n;n.push=n;n.loaded=!0;n.version='2.0';
    n.queue=[];t=b.createElement(e);t.async=!0;
    t.src=v;s=b.getElementsByTagName(e)[0];
    s.parentNode.insertBefore(t,s)}(window, document,'script',
    'https://connect.facebook.net/en_US/fbevents.js');
    fbq('init', 'SEU_ID_PIXEL'); 
    fbq('track', 'PageView');
  </script>
  <noscript>
    <img height="1" width="1" style="display:none"
    src="https://www.facebook.com/tr?id=SEU_ID_PIXEL&ev=PageView&noscript=1"/>
  </noscript>
</head>
<body class="bg-white text-gray-800">

  <!-- HEADER -->
  <header class="flex items-center justify-between p-4 shadow-md bg-white">
    <img src="logo.png" alt="Sushi Dojo Logo" class="h-10">
    <a href="#pedido" class="bg-red-600 text-white px-4 py-2 rounded-md">Comprar Agora</a>
  </header>

  <!-- HERO -->
  <section class="text-center p-6">
    <img src="sushi-banner.jpg" alt="Banner Sushi" class="rounded-lg shadow-lg mx-auto mb-4 max-w-md">
    <h1 class="text-2xl font-bold mb-2">Sushi Fresco Entregue na Sua Casa</h1>
    <p class="mb-4">Receba em até 30 minutos, direto do chef para sua mesa.</p>
    <a href="#pedido" class="bg-green-500 text-white px-6 py-2 rounded-full text-lg">Ver Cardápio</a>
  </section>

  <!-- CARDÁPIO -->
  <section class="p-6 bg-gray-50">
    <h2 class="text-xl font-semibold mb-4">Cardápio Popular</h2>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
      <div class="bg-white p-4 rounded shadow">
        <img src="combinado2.jpg" alt="Combinado" class="w-full rounded mb-2">
        <h3 class="font-semibold">Combinado 40 Peças</h3>
        <p class="text-sm mb-2">Promoção do dia com entrega grátis!</p>
        <button onclick="abrirCheckout('Combinado 40 Peças')" class="bg-red-500 text-white px-4 py-2 rounded">Comprar</button>
      </div>
    </div>
  </section>

  <!-- CHECKOUT -->
  <section id="checkout" class="hidden p-6">
    <h2 class="text-xl font-bold mb-4">Finalizar Pedido</h2>
    <form onsubmit="enviarPedido(); return false;" class="grid gap-4 max-w-md mx-auto">
      <input type="text" id="produto" class="hidden">
      <input type="text" id="nome" placeholder="Seu nome" required class="border p-2 rounded">
      <input type="text" id="endereco" placeholder="Endereço de entrega" required class="border p-2 rounded">
      <input type="text" id="telefone" placeholder="Telefone para contato" required class="border p-2 rounded">
      <select id="pagamento" required class="border p-2 rounded">
        <option value="">Forma de pagamento</option>
        <option value="Pix">Pix</option>
        <option value="Dinheiro">Dinheiro</option>
        <option value="Cartão">Cartão</option>
      </select>
      <button type="submit" class="bg-green-600 text-white px-4 py-2 rounded">Confirmar Pedido</button>
    </form>
  </section>

  <!-- RESULTADO DO PEDIDO -->
  <section id="resumo" class="hidden p-6 bg-green-50 text-center">
    <h2 class="text-xl font-bold mb-2">Pedido Recebido com Sucesso! 🍣</h2>
    <p class="mb-2">Faça o pagamento via <strong>PIX</strong> para:</p>
    <div class="text-lg font-mono bg-white border rounded p-2 inline-block mb-2">sushidojodelivery</div>
    <p class="text-sm text-gray-600">Após o pagamento, seu pedido será preparado.</p>
  </section>

  <!-- CTA FINAL -->
  <section id="pedido" class="p-6 text-center bg-red-600 text-white">
    <h2 class="text-xl font-bold mb-2">Promoção válida por tempo limitado</h2>
    <p class="mb-4">Clique abaixo para garantir seu pedido</p>
    <a href="#checkout" onclick="document.getElementById('checkout').scrollIntoView({ behavior: 'smooth' });" class="bg-white text-red-600 px-6 py-2 rounded-full text-lg font-semibold">Comprar Agora</a>
  </section>

  <footer class="text-center p-4 text-sm text-gray-500">
    © 2025 Sushi Dojo Delivery. Todos os direitos reservados.
  </footer>

  <script>
    function abrirCheckout(produto) {
      document.getElementById('checkout').classList.remove('hidden');
      document.getElementById('checkout').scrollIntoView({ behavior: 'smooth' });
      document.getElementById('produto').value = produto;
    }

    function enviarPedido() {
      const nome = document.getElementById('nome').value;
      const endereco = document.getElementById('endereco').value;
      const telefone = document.getElementById('telefone').value;
      const pagamento = document.getElementById('pagamento').value;
      const produto = document.getElementById('produto').value;

      fbq('track', 'Purchase');

      document.getElementById('checkout').classList.add('hidden');
      document.getElementById('resumo').classList.remove('hidden');
      document.getElementById('resumo').scrollIntoView({ behavior: 'smooth' });
    }
  </script>

</body>
</html>
