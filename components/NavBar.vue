
<template>
  <div>
    <div class="edu-color h-20 flex flex-row justify-between items-center" style="padding-left: 20%; padding-right: 20%;">
      <div class="w-22 h-22 mb-3" style="">
        <nuxt-link :to="localePath('/')">  
          <img :src="logo" />
        </nuxt-link>
      </div>
      <div class=" flex flex-row items-center justify-start">
        <div class="flex flex-row items-center">
            <div class="flex items-center flex-row">
                <a class="text-white text-navbar-sm" href="tel:+43 1 890 89 48">+43 1 890 89 48</a> <p class="text-white text-navbar-sm" style="padding-left: 1vw;" > | Rennweg 9/6, 1030 Wien |</p>
            </div>
            <div class="flex items-center flex-row" style="margin-left:0.5vw">
                <a href="https://www.facebook.com/edustream.vienna" target="_blank">
                  <img style="width: calc(12px + 0.990625vw); height: auto" :src="facebookLogo" />
                </a>
                <a href="https://www.instagram.com/edustream.at" style="margin-left:0.5vw" target="_blank">
                  <img style="width: calc(12px + 0.990625vw); height: auto" :src="instagramLogo" />
                </a>
            </div>
        </div>
        <div class="flex flex-column items-start w-16 h-16 justify-center pt-4 ml-2 bg-white self-start rounded-b-md text-navbar-sm" style="margin-bottom:3vh;">
          <div class="nav-item dropdown">
            <a class="nav-link dropdown-toggle font-semibold flex flex-row items-center justify-start" style="margin-left:-1vw"  id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
              <country-flag :country="$t('flag')" size='small' /> {{this.$i18n.locale.toUpperCase()}}
            </a>
            <div class="dropdown-menu"  aria-labelledby="navbarAnchor">
              <nuxt-link class="dropdown-item text-navbar-sm flex flex-row items-center"  :to="switchLocalePath('en')"><country-flag size="small" country="gb" />EN</nuxt-link>
              <nuxt-link class="dropdown-item text-navbar-sm flex flex-row items-center"  :to="switchLocalePath('de')"><country-flag size="small" country="de" />DE</nuxt-link>
              <nuxt-link class="dropdown-item text-navbar-sm flex flex-row items-center"  :to="switchLocalePath('ru')"><country-flag size="small" country="ru" />RU</nuxt-link>
            </div>
          </div>
        </div>
      </div>
  </div>
  </div>
 
      
</template>

<style scoped>
.dropdown:hover .dropdown-menu {
    display: flex;
    flex-direction: column;
    width:1vw;
    margin-top: 0; 
 }
 .isHidden {
  display: none;
}

.text-navbar-sm{
  font-size:calc(1px + 0.730625vw);  
}

.menu-selected p{
  color:rgb(67, 44, 243);
  text-decoration: underline
}
 .bg-dark{
  background-color: rgba(59, 39, 239, 0.763);
 }
 .bg-blue{
  background-color: rgba(59, 39, 239, 0.763);
 }
 .topnavbar-list li{
  list-style-type:'';
  display:inline;
  color: rgba(255, 255, 255, 1);
 }
 .topnavbar-list li p{
  display:inline;
  color: rgba(255, 255, 255, 1);
 }

 .white-right-border{
  border-right: 1px solid white;
 }
 .bg-grey{
  background-color: rgba(82, 82, 82, 0.842);
 }
  .edu-color {
  background-color: #253984
  }
</style>

<script>

import logo from "~/assets/edu-stream_logo.png"
import frontpageWelcome from "~/assets/frontpage_welcome.png"
import facebookLogo from "~/assets/facebook_logo.svg"
import instagramLogo from "~/assets/instagram_logo.svg"
import countryFlag from 'vue-country-flag'


export default {
  components: {
    countryFlag
  },
  data: function () {
    return {
      logo: logo,      
      frontpageWelcome: frontpageWelcome,
      facebookLogo:facebookLogo,
      instagramLogo: instagramLogo,
      isSidebarOpen: false,
      examsIsSelected: false,
      aboutIsSelected: false,
      coursesIsSelected: false
    }
  },
  methods: {}
}

</script>



