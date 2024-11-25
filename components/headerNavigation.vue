<template>
  <div class="container">




    <div class="overf" v-if="overlay">
  
</div>




<div class="mobileMenu">

  <div class="closeandopenicone">
  <img src="@/public/images/icon-close-menu.svg" alt="logo menu" v-if="open"  @click="change();changeoverlay()"  />
  <img src="@/public/images/icon-menu.svg" alt="logo menu"   v-else    @click="change();changeoverlay()"  />

   </div>
<transition name="fade">
   <div class="menumobilelement" v-if="open">


    <div class="menuelementmobile">
          <div class="features">
           <p   @click="changesubMenuopen">Features ˅</p> 
           <ul  v-for="feature in featuress" :key="feature.id" class="souslistemobile" v-if="subMenuopen">
            <li>  <img :src="feature.img" class="im"/></li>
            <li>  {{feature.label}}</li>
          </ul>


          </div> 
          
          <div class="Company">

            <p   @click="changesubMenuopencompany"          >Company ˅</p> 
           <ul  v-for="company in companys" :key="company.id" class="souslistemobile" v-if="changemenucompany">
         
            <li>  {{company.label}}</li>
          </ul>
          </div>
         <div class="menuelementmobil" >
          <p>Careers</p>
          <p>About</p>
        </div>

       
<div class="connectionn">
        <button>Login</button> <br>
        <button>Register</button>
      </div>
        
        </div>


   </div>
  </transition>


</div>


    <div class="headermenu">
      <div class="bloc1">
        <div class="logo">
          <img src="@/public/images/logo.svg" alt="logo menu" />
        </div>
        <div class="menuelement">
          <ul v-for="menuItem in menuItems" :key="menuItem.id" class="">
            <a href="">{{ menuItem.label }}</a>

            <ul class="sousmenu">
              <li
                v-for="submen in menuItem.submenu"
                :key="submen.id"
                class="sousmenuimg"
              >
                <div><img :src="submen.img" /></div>
                <div>{{ submen.label }}</div>
              </li>
            </ul>
          </ul>
        </div>
      </div>

      <div class="connection">
        <button>Login</button>
        <button>Register</button>
      </div>
    </div>
  </div>
</template>
    

    <style lang="scss" scoped>

.connectionn > button:first-child {
  background-color: transparent;
  border: none;
  color: black;
}
.connectionn{

  display:flex;
  margin-top:20px;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  button{
border:none;
background-color: transparent;
border:1PX SOLID black;
border-radius: 10px;
    font-size: 23px;
    width:65% ;
    padding:3px;
   
  }
}
.connecti0on{
  display:flex;
  flex-direction:column;
  justify-content: center;
  button{
    font-size: 25px;
    width:62% ;
    margin-left: 12px;
  }
}


.overf{
  background-color: rgba(0, 0, 0, 0.5); /* Overlay noir semi-transparent */
  position: absolute;
  top:0;
  height:100vh;
  width:100% ;
  z-index:0;
  
}


.menumobilelement{
   background-color: #ffffff;
  // background-color: rgba(255, 255, 255, 0.5);
  height: 100VH;
  position:fixed;
  top:00;
  right: 0;
  width:50% ;
  cursor: pointer;

  
}


.menuelementmobile{
  font-size:25PX;
  display:flex;
  flex-direction: column;
  z-index: 2;
  padding-left: 5%;
   gap: 10px;
   margin-top: 40%;



}
.souslistemobile{
  display:flex;
  align-items:center;


 
}
.im{
margin-right: 5PX;
  margin-left: 9px;
}
.Company {
  li{
    margin-left: 9px;
  }
}

.menuelement{
  display:flex;

  gap:10px;
}

.closeandopenicone{
  // background-color: blue;
 top:10px;
  right:20px;
 margin-top:15px;
 z-index: 5;
 position: fixed;
}

.mobileMenu{
  // background-color:grey;
  display: NONE;
    // position:absolute;
  // margin-bottom: 65px;

padding: 0  15px;
  width:67% ;

  
  height: 100vh;
}

@media(max-width:768px){
  .mobileMenu{
     display: block;
     position: absolute;   
     top:0;

  }
  .headermenu{
    .connection{
        display:none
    }
    .menuelement{
      background-color: yellow;
      display: none;
    }
    .bloc1{
      display: NONE;
    }
    


  }
}

.container {
  display: flex;
  justify-content: center;
  padding: 25px;
  
  
}

.headermenu {

  width: 95%;
  width: min(100%, 1300px);
  margin: 0 auto;
  display: flex;

  justify-content: space-between;
  .bloc1 {
    display: flex;
    gap: 30px;

    // border:1px solid yellowgreen;
    width: 50%;
  }

}
.menuelement {
  animation: menu 2s ease-in-out;
  display: flex;
  justify-content: space-between;
  cursor: pointer;
  // border:1px solid black;
  width: 90%;
  ul a li {
    text-decoration: none;
  }

  ul {
    &:hover {
      .sousmenu {
        opacity: 1;
      }
    }
  }

  .sousmenu {
    // display: none;
    opacity: 0;
    border-radius: 5px;
    background-color: #ffffff;
    margin-top: 15px;
    width: 110px;
    box-shadow: 5px 5px 15px rgba(0, 0, 0, 0.3);

    li {
      margin-bottom: 4px;
      color: black;
      font-weight: 500;
      text-align: center;
    }
    li a {
      font-size: 9px;
      color: black;
      font-weight: 500;
    }

    .sousmenuimg {
      display: flex;
      justify-content: center;
      align-items: center;
      //   opacity: 0;
      gap: 4px;
      padding: 5px;
      // border:1px solid black;
      img {
        margin-top: 4px;
      }
      //                 &:hover{
      //     opacity: 1;
      //  }
    }
    //  &:hover{
    //     opacity: 1;
    //  }
  }
}
.container {
  display: flex;
  
}

.connection > button:first-child {
  background-color: transparent;
  border: none;
  color: black;
}
.connection {
  button {
    background-color: transparent;
    color: black;
    border: 1px solid black;
    padding: 5px;
    font-size:14px;
    border-radius: 8px;
  }
}
@keyframes menu {
  0% {
    transform: translatey(-40px); /* position initiale */
    opacity: 1;
  }

  100% {
    transform: translatey(0px); /* retour à la position initiale */
    opacity: 1;
  }
}


.fade-enter-active, .fade-leave-active {
  transition: transform 0.5s ease, opacity 0.5s ease;
}

/* Entrée : commence hors écran à gauche */
.fade-enter {
  transform: translateX(-100%);
  opacity: 0;
}

/* Sortie : va hors écran à droite */
.fade-leave-to {
  transform: translateX(100%);
  opacity: 0;
}



</style>
    
    
    <script setup>


const overlay =ref(false);

function changeoverlay(){
  overlay.value=!overlay.value
}
const subMenuopen=ref(false);
 const open =ref(false);
 const changemenucompany=ref(false);
 function change () {
  open.value=!open.value;
  
 }   

 const changesubMenuopen =()=>{
  subMenuopen.value=!subMenuopen.value;

 }
 const changesubMenuopencompany =()=>{
  changemenucompany.value=!changemenucompany.value;

 }

// Méthodes pour gérer le survol et la sortie de la souris

const menuItems = ref([
  {
    label: "Features ˅ ",
    submenu: [
      { label: "Todo list", link: "#", img: "/images/icon-todo.svg" },
      { label: "Calendar", link: "#", img: "/images/icon-calendar.svg" },
      { label: "Reminder", link: "#", img: "/images/icon-reminders.svg" },
      { label: "Planning", link: "#", img: "/images/icon-planning.svg" },
    ],
  },
  {
    label: "Company ˅ ",
    submenu: [
      { label: "History", link: "#" },
      { label: "Our Team", link: "#" },
      { label: "Blog", link: "#" },
    ],
  },
  { label: "Careers", submenu: [] },

  { label: "About", submenu: [] },
]);


const companys=ref([
{ label: "History", link: "#" },
      { label: "Our Team", link: "#" },
      { label: "Blog", link: "#" },

])

const featuress=ref([

{label: "Todo list", link: "#", img: "/images/icon-todo.svg" },
{ label: "Calendar", link: "#", img: "/images/icon-calendar.svg" },
{ label: "Reminder", link: "#", img: "/images/icon-reminders.svg" },
{ label: "Planning", link: "#", img: "/images/icon-planning.svg" },

])



</script>