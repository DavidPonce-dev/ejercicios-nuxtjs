<template>
  <div class="wrap">
    <header>
      <div class="logo">
        LOGO
      </div>
      <div class="menu">
        <ul>
          <li><a href="#">Home</a></li>
          <li><a href="#">About</a></li>
          <li><a href="#">Partners</a></li>
          <li><a href="#">Faq</a></li>
          <li><a href="#">Blog</a></li>
        </ul>
      </div>
    </header>
    <div class="content">
      <h1>Dream home is ready for upcoming booking</h1>
      <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Id cumque quis, minima neque laborum magnam quia soluta, fugit sint, eligendi expedita! Hic reprehenderit qui cumque aspernatur tenetur odit eligendi quae.</p>
      <div class="btn-group">
        <a href="#" class="color1">Book Now</a>
        <a href="#">Learn more</a>
      </div>
    </div>
    <!-- wave -->
    <!-- https://getwaves.io -->
    <svg class="wave" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320">
      <path fill="#fff" fill-opacity="1" d="M0,0L48,37.3C96,75,192,149,288,170.7C384,192,480,160,576,133.3C672,107,768,85,864,101.3C960,117,1056,171,1152,176C1248,181,1344,139,1392,117.3L1440,96L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z" />
    </svg>
  </div>
</template>

<script>
export default {
  layout: 'landing'
}
</script>

<style>
.wrap{
  background: rgba(0,0,0,0.5) url(../assets/atumn-tree.png) no-repeat;
  background-position: center;
  background-size: cover;
  min-height: 100vh;
  overflow: hidden;
  background-blend-mode: overlay;
}
.wave{
  position: absolute;
  width: 100%;
  bottom: 0px;
  color: #fff;
  opacity: 1;
}
@media (min-aspect-ratio: 8/5) {
  .wave{
    bottom: -80px;
  }
}
header{
  position: fixed;
  top: 0;
  left:0;
  width: 100%;
  padding: 25px 80px;
  background: linear-gradient(to top, transparent, rgba(0,0,0,0.6));
}
header .logo{
  font-size: 28px;
  font-weight: 700;
  color:#fff;
  float: left;
}
header .menu{
  float: right;
  margin-top: 5px;
}
header ul li{
  display: inline-block;
}
header ul li a{
  text-decoration: none;
  font-size: 16px;
  color: #fff;
  margin: 0 25px;
  font-weight: 300;
  letter-spacing: 1px;
}
</style>
