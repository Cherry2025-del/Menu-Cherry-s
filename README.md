
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Cherry's - Menu</title>
  <style>
    :root{
      --red:#E50914;
      --black:#000;
      --white:#fff;
      --grey:#f5f5f5;
    }
    *{
      box-sizing:border-box;
      margin:0;
      padding:0;
      font-family:'Poppins',sans-serif;
    }
    html{
      scroll-behavior:smooth;
    }
    body{
      background:var(--white);
      color:var(--black);
      line-height:1.4;
    }
    #home{
      height:100vh;
      display:flex;
      flex-direction:column;
      align-items:center;
      justify-content:center;
      background:var(--black);
      text-align:center;
    }
    #logo{
      max-width:90vw;
      max-height:40vh;
      filter:drop-shadow(0 0 12px var(--red));
    }
    #menuBtn{
      margin-top:30px;
      padding:14px 40px;
      font-size:1.3rem;
      font-weight:600;
      background:var(--red);
      color:var(--white);
      border:none;
      border-radius:30px;
      cursor:pointer;
      transition:.3s;
    }
    #menuBtn:hover{
      background:#ff0c18;
      transform:scale(1.05);
    }
    #menu{
      padding:60px 20px 40px;
      background:var(--grey);
    }
    #menu h1{
      text-align:center;
      margin-bottom:40px;
      font-size:2rem;
    }
    #categories{
      display:grid;
      gap:25px;
      grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
    }
    .card{
      background:var(--white);
      border-radius:12px;
      overflow:hidden;
      box-shadow:0 4px 10px rgba(0,0,0,.08);
      transition:.3s;
    }
    .card:hover{
      transform:translateY(-5px);
      box-shadow:0 8px 20px rgba(0,0,0,.15);
    }
    .card img{
      width:100%;
      height:160px;
      object-fit:cover;
    }
    .card h2{
      padding:15px 20px 0;
      font-size:1.3rem;
    }
    .card ul{
      list-style:none;
      padding:0 20px 20px;
    }
    .card li{
      display:flex;
      justify-content:space-between;
      padding:6px 0;
      font-size:.95rem;
    }
    .card .price{
      font-weight:600;
      color:var(--red);
    }
    .card .order{
      display:block;
      margin:0 20px 20px;
      padding:10px;
      text-align:center;
      background:var(--red);
      color:var(--white);
      border-radius:6px;
      text-decoration:none;
      font-weight:600;
      transition:.3s;
    }
    .card .order:hover{
      background:#ff0c18;
    }
    footer{
      text-align:center;
      padding:30px 10px;
      font-size:.85rem;
      background:var(--black);
      color:var(--white);
    }
    footer a{
      color:var(--red);
      text-decoration:none;
      font-weight:600;
    }
  </style>
</head>
<body>
  <section id="home">
    <img id="logo" src="img/logo.webp" alt="Cherry's Logo">
    <button id="menuBtn">Menu</button>
  </section>

  <section id="menu">
    <h1>Nos Catégories</h1>
    <div id="categories"></div>
  </section>

  <footer>
    WhatsApp : 84 12 47 48 <br>
    © 2025 Cherry's Fast Food – Tous droits réservés
  </footer>

  <script>
    const menu=[
      {cat:"Fast-food",img:"img/fastfood.webp",items:[
        {name:"Gyros poulet",price:3000},
        {name:"Gyros bœuf",price:2000},
        {name:"Gyros Cherry's",price:4500},
        {name:"Sandwich viande",price:1000},
        {name:"Sandwich poulet",price:1500},
        {name:"Chawarma poulet",price:2000},
        {name:"Chawarma viande",price:1500},
        {name:"Hamburger",price:2500},
        {name:"Chicken burger",price:3000},
        {name:"Cherry's burger",price:4000},
        {name:"KFC",price:4000},
        {name:"Plat de Nems (4 pcs)",price:2500},
        {name:"Tacos viande",price:2500},
        {name:"Tacos poulet",price:3500},
        {name:"Tacos Cherry's",price:4500}
      ]},
      {cat:"Big Menus",img:"img/fastfood.webp",items:[
        {name:"Big Sandwich",price:7500},
        {name:"Big Burgers",price:7500}
      ]},
      {cat:"Pizzas",img:"img/pizza.webp",items:[
        {name:"Pizza Cherry's",price:7000},
        {name:"Pizza Margherita",price:5000},
        {name:"Pizza Orientale",price:6000},
        {name:"Pizza Végétarien",price:6000},
        {name:"Pizza Kiss",price:6500}
      ]},
      {cat:"Grillades",img:"img/grillades.webp",items:[
        {name:"Brochette bœuf",price:6000},
        {name:"Brochette poulet",price:6000},
        {name:"Brochette capitaine",price:7000},
        {name:"1/2 poulet",price:6000}
      ]},
      {cat:"Mixtes à partager",img:"img/mixtes.webp",items:[
        {name:"Mixte fast-food",desc:"Tacos viande, Chawarma poulet, Nems, KFC, Gyros Cherry's",price:15000},
        {name:"Mixte grillé",desc:"Brochette bœuf, capitaine et 1/2 poulet",price:15000}
      ]},
      {cat:"Glaces",img:"img/glace.webp",items:[
        {name:"Une boule",price:1000},
        {name:"Deux boules",price:1500},
        {name:"Trois boules",price:2000},
        {name:"Cornet 2 boules",price:2000},
        {name:"Cornet 3 boules",price:2500},
        {name:"Cornet Américain 1 boule",price:1000},
        {name:"Cornet Américain 2 boules",price:1500},
        {name:"Waffles bowls 1 boule",price:2000},
        {name:"Waffles bowls 2 boules",price:2500}
      ]},
      {cat:"Café",img:"img/cafe.webp",items:[
        {name:"Nespresso",price:1500},
        {name:"Cappuccino",price:2000},
        {name:"Frappuccino glacé",price:2500}
      ]},
      {cat:"Thé",img:"img/the.webp",items:[
        {name:"Thé mixte",price:1500},
        {name:"Thé Cherry's",price:1500},
        {name:"Thé malien",price:1000}
      ]},
      {cat:"Mocktails",img:"img/mocktail.webp",items:[
        {name:"Ener Cherry's",price:2000},
        {name:"Virginie Colada",price:4000},
        {name:"Virginie Mojito",price:4000},
        {name:"Bora Bora",price:4000},
        {name:"San Francisco",price:4000},
        {name:"Coco lait",price:5000}
      ]}
    ];

    const categoriesDiv=document.getElementById('categories');
    const menuBtn=document.getElementById('menuBtn');

    menuBtn.addEventListener('click',()=>{
      document.getElementById('menu').scrollIntoView({behavior:'smooth'});
    });

    menu.forEach(cat=>{
      const card=document.createElement('div');
      card.className='card';
      card.innerHTML=`
        <img src="${cat.img}" alt="${cat.cat}">
        <h2>${cat.cat}</h2>
        <ul>
          ${cat.items.map(i=>`
            <li>
              <span>${i.name}${i.desc?` - ${i.desc}`:''}</span>
              <span class="price">${i.price.toLocaleString('fr-FR')} F CFA</span>
            </li>
          `).join('')}
        </ul>
        <a class="order" href="https://wa.me/22684124748" target="_blank">Commander sur WhatsApp</a>
      `;
      categoriesDiv.appendChild(card);
    });
  </script>
</body>
</html>
