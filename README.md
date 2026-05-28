<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>

<title>Luxury Frame Store</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">

<style>

*{
  margin:0;
  padding:0;
  box-sizing:border-box;
}

body{
  font-family:'Inter',sans-serif;
  background:#04101d;
  color:white;
  overflow-x:hidden;
}

/* NAVBAR */

.navbar{
  position:fixed;
  top:0;
  width:100%;
  padding:22px 8%;
  display:flex;
  justify-content:space-between;
  align-items:center;
  z-index:1000;
  backdrop-filter:blur(14px);
  background:rgba(0,0,0,0.25);
}

.logo{
  font-size:28px;
  font-weight:800;
}

.nav-links{
  display:flex;
  gap:28px;
}

.nav-links a{
  color:white;
  text-decoration:none;
  opacity:0.8;
  transition:0.3s;
}

.nav-links a:hover{
  opacity:1;
}

/* HERO */

.hero-slider{
  width:100%;
  height:100vh;
  overflow:hidden;
  position:relative;
}

.slides{
  display:flex;
  width:300%;
  height:100%;
  animation:slide 14s infinite;
}

.slide{
  width:100%;
  height:100%;
  flex-shrink:0;
  position:relative;
}

.slide img{
  width:100%;
  height:100%;
  object-fit:cover;
}

.overlay{
  position:absolute;
  inset:0;
  background:linear-gradient(
    to bottom,
    rgba(0,0,0,0.2),
    rgba(0,0,0,0.7)
  );
}

.hero-content{
  position:absolute;
  top:50%;
  left:8%;
  transform:translateY(-50%);
  z-index:2;
}

.hero-content h1{
  font-size:90px;
  line-height:0.95;
  margin-bottom:24px;
}

.hero-content p{
  max-width:650px;
  opacity:0.8;
  line-height:1.8;
  font-size:18px;
}

.hero-btn{
  margin-top:35px;
  display:inline-block;
  padding:16px 34px;
  border-radius:999px;
  background:white;
  color:black;
  text-decoration:none;
  font-weight:700;
}

/* COLLECTIONS */

.collections{
  padding:100px 8%;
}

.section-title{
  font-size:54px;
  margin-bottom:50px;
  font-weight:800;
}

.collection-grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
  gap:30px;
}

.collection-card{
  position:relative;
  overflow:hidden;
  border-radius:30px;
  min-height:430px;
  transition:0.4s ease;
}

.collection-card:hover{
  transform:translateY(-10px) scale(1.02);
}

.collection-card img{
  position:absolute;
  width:100%;
  height:100%;
  object-fit:cover;
}

.collection-content{
  position:relative;
  z-index:2;
  padding:34px;
  display:flex;
  flex-direction:column;
  justify-content:space-between;
  height:100%;
}

.collection-title{
  font-size:42px;
  line-height:1.05;
  max-width:220px;
}

.collection-btn{
  display:inline-flex;
  align-items:center;
  gap:8px;
  width:max-content;
  padding:12px 24px;
  border-radius:999px;
  background:rgba(255,255,255,0.15);
  backdrop-filter:blur(10px);
  color:white;
  text-decoration:none;
}

/* PRODUCTS */

.products{
  padding:40px 8% 100px;
}

.product-grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
  gap:30px;
}

.product-card{
  background:#0d1a29;
  border-radius:24px;
  overflow:hidden;
  transition:0.4s;
}

.product-card:hover{
  transform:translateY(-8px);
}

.product-card img{
  width:100%;
  height:280px;
  object-fit:cover;
}

.product-info{
  padding:22px;
}

.product-info h3{
  font-size:22px;
  margin-bottom:10px;
}

.price{
  font-size:20px;
  font-weight:700;
  margin-bottom:18px;
}

.buy-btn{
  display:inline-block;
  padding:12px 22px;
  border-radius:999px;
  background:white;
  color:black;
  text-decoration:none;
  font-weight:700;
}

/* FOOTER */

.footer{
  text-align:center;
  padding:40px;
  opacity:0.6;
}

/* ANIMATION */

@keyframes slide{

  0%{
    transform:translateX(0);
  }

  30%{
    transform:translateX(0);
  }

  35%{
    transform:translateX(-100%);
  }

  65%{
    transform:translateX(-100%);
  }

  70%{
    transform:translateX(-200%);
  }

  100%{
    transform:translateX(-200%);
  }

}

/* MOBILE */

@media(max-width:768px){

  .hero-content h1{
    font-size:52px;
  }

  .section-title{
    font-size:36px;
  }

  .collection-title{
    font-size:30px;
  }

  .nav-links{
    display:none;
  }

}

</style>
</head>
<body>

<!-- NAVBAR -->

<nav class="navbar">

  <div class="logo">
    FRAMEVAULT
  </div>

  <div class="nav-links">
    <a href="#">Home</a>
    <a href="#">Collections</a>
    <a href="#">Products</a>
    <a href="#">Contact</a>
  </div>

</nav>

<!-- HERO SLIDER -->

<section class="hero-slider">

  <div class="slides">

    <!-- SLIDE 1 -->

    <div class="slide">

      <img src="https://images.unsplash.com/photo-1505693416388-ac5ce068fe85?q=80&w=1400&auto=format&fit=crop">

      <div class="overlay"></div>

      <div class="hero-content">

        <h1>
          Luxury<br>
          Wall Frames
        </h1>

        <p>
          Premium interior wall frames designed for modern homes and luxury spaces.
        </p>

        <a href="#" class="hero-btn">
          Explore Now
        </a>

      </div>

    </div>

    <!-- SLIDE 2 -->

    <div class="slide">

      <img src="https://images.unsplash.com/photo-1494526585095-c41746248156?q=80&w=1400&auto=format&fit=crop">

      <div class="overlay"></div>

    </div>

    <!-- SLIDE 3 -->

    <div class="slide">

      <img src="https://images.unsplash.com/photo-1513694203232-719a280e022f?q=80&w=1400&auto=format&fit=crop">

      <div class="overlay"></div>

    </div>

  </div>

</section>

<!-- COLLECTION SECTION -->

<section class="collections">

  <h2 class="section-title">
    Collections
  </h2>

  <div class="collection-grid">

    <!-- CARD 1 -->

    <div class="collection-card">

      <img src="https://images.unsplash.com/photo-1516321497487-e288fb19713f?q=80&w=1200&auto=format&fit=crop">

      <div class="overlay"></div>

      <div class="collection-content">

        <h3 class="collection-title">
          Modern Black Frames
        </h3>

        <a href="#" class="collection-btn">
          Explore →
        </a>

      </div>

    </div>

    <!-- CARD 2 -->

    <div class="collection-card">

      <img src="https://images.unsplash.com/photo-1505693416388-ac5ce068fe85?q=80&w=1200&auto=format&fit=crop">

      <div class="overlay"></div>

      <div class="collection-content">

        <h3 class="collection-title">
          Wooden Luxury Art
        </h3>

        <a href="#" class="collection-btn">
          Explore →
        </a>

      </div>

    </div>

    <!-- CARD 3 -->

    <div class="collection-card">

      <img src="https://images.unsplash.com/photo-1494526585095-c41746248156?q=80&w=1200&auto=format&fit=crop">

      <div class="overlay"></div>

      <div class="collection-content">

        <h3 class="collection-title">
          Premium Interior Frames
        </h3>

        <a href="#" class="collection-btn">
          Explore →
        </a>

      </div>

    </div>

  </div>

</section>

<!-- TOP SELLING -->

<section class="products">

  <h2 class="section-title">
    Top Selling Products
  </h2>

  <div class="product-grid">

    <!-- PRODUCT 1 -->

    <div class="product-card">

      <img src="https://images.unsplash.com/photo-1513519245088-0e12902e5a38?q=80&w=1200&auto=format&fit=crop">

      <div class="product-info">

        <h3>
          Black Minimal Frame
        </h3>

        <div class="price">
          ₹1,299
        </div>

        <a href="#" class="buy-btn">
          Buy Now
        </a>

      </div>

    </div>

    <!-- PRODUCT 2 -->

    <div class="product-card">

      <img src="https://images.unsplash.com/photo-1519710164239-da123dc03ef4?q=80&w=1200&auto=format&fit=crop">

      <div class="product-info">

        <h3>
          Wooden Art Frame
        </h3>

        <div class="price">
          ₹1,899
        </div>

        <a href="#" class="buy-btn">
          Buy Now
        </a>

      </div>

    </div>

    <!-- PRODUCT 3 -->

    <div class="product-card">

      <img src="https://images.unsplash.com/photo-1505693416388-ac5ce068fe85?q=80&w=1200&auto=format&fit=crop">

      <div class="product-info">

        <h3>
          Premium Gold Frame
        </h3>

        <div class="price">
          ₹2,499
        </div>

        <a href="#" class="buy-btn">
          Buy Now
        </a>

      </div>

    </div>

  </div>

</section>

<!-- FOOTER -->

<footer class="footer">
  © 2026 FRAMEVAULT. All rights reserved.
</footer>

</body>
</html>
