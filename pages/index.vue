<template>
  <div class="entiresite">

    <div class="container">

<div class="gauche">

<h1>Make   <br class="mobile-hide"> remote work</h1>

<p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Veniam voluptatem facilis   <br>  recusandae cum expedita provident <br>  </p>
<div>
<button>Learn More</button>
</div>
<div class="homelogo">

   <img src="@/public/images/client-databiz.svg" alt="logo menu" />
  <img src="@/public/images/client-audiophile.svg" alt="logo menu" />
  <img src="@/public/images/client-meet.svg" alt="logo menu" />
  <img src="@/public/images/client-maker.svg" alt="logo menu" /> 
</div>
</div>
<div class="droite">

   <img src="@/public/images/image-hero-desktop.png" alt="logo menu"
   class="imgdekstop"
   
   />

   <img src="@/public/images/image-hero-mobile.png" alt="logo menu" class="imgmobile" /> 
</div>
</div>


  </div>
</template>

<script setup>



</script>

<style lang="scss" scoped>
.imgmobile{
  display:none;
}

.container{
 
  
  padding:0 5%;
  display: flex;
  justify-content: space-around;
  align-items:center;
  gap:10px;
  // position: relative;
}
.gauche{
 margin-top: -32PX;
  .homelogo{
    display: flex;
    align-items: center;
    gap:20px;
  }
  display: flex;
  flex-direction: column;
  gap:40px;
  // height: 55vh;

  button{
        background-color: transparent;
        color:black;
        border: 1px solid black;
        padding: 5px;
        border-radius:8px;
      }

h1{
  font-size: 50px;
}

}

.droite{
  .imgdekstop{
   margin-top: -110PX;
  }
  img{
    width:320px ;
  }
  // position:absolute;
  // right: 0;
  display: flex;
  // margin-top:-65px;

}


@media (max-width:826PX) {
  
.gauche {
  text-align: center;
   
h1{
  font-size: 30px;

}

P{
  font-size:13PX;
}
button{
  background-color: black;
  color:#ffffff;
  font-weight: bold;
  padding:10px;
}

}

.homelogo{

img{
  width:50px ;
}

}
}
@media (max-width:768PX){

.container{
  flex-direction: column-reverse;
  align-items: center;
margin-top: 25px;

}



  .imgdekstop{
    display:none;
  }
  .imgmobile{
    display:block;
    margin-bottom:30px;
  }

  .droite{
 
  }
  .gauche{
    align-items: center;
    gap:15px;
  }

  .mobile-hide{
    display: none;
  }

}

@keyframes menu {
  0% {
    transform: translateX(0); /* position initiale */
    opacity: 1;
  }

  100% {
    transform: translateX(0); /* retour à la position initiale */
    opacity: 1;
  }
}






</style>