<template>
<div id="themeSetting">
  <v-toolbar dark>
    <v-toolbar-title>
      Configuracion de Interfaz
    </v-toolbar-title>
  </v-toolbar>
  <v-container>
    <v-layout column>
      <v-flex>
        <v-subheader class="px-1 my-2">
          Opciones de Color
        </v-subheader>
        <div class="color-option">
          <v-layout wrap>
            <label class="color-option--label flex xs6 pa-1" v-for="(option,index) in themeColorOptions" :key="index">
              <input type="radio" name="color" v-bind:value="option.key" v-model="themeColor">
              <span class="color-option--item bg">
                <span class="overlay">
                  <span class="material-icons">check</span>
                </span>
                <span class="color-option--item--header sideNav" :class="option.value.sideNav"></span>
                <span class="color-option--item--header mainNav" :class="option.value.mainNav"></span>
                <span class="sideMenu" :class="option.value.sideManu"></span>
              </span>
            </label>
          </v-layout>
        </div>       
      </v-flex>
    </v-layout>
  </v-container>
</div>
</template>

<script>
import colors from 'vuetify/es5/util/colors';
export default {
  data () {
    return {
      themeColor: 'blue',
      sideBarOption: 'light',
      colors: colors
    };
  },
  computed: {
    themeColorOptions () {
      return [
        {
          key: 'blue',
          value: {
            sideNav: 'blue',
            mainNav: 'blue',
            sideManu: 'white'
          }
        },
        {
          key: 'teal',
          value: {
            sideNav: 'teal',
            mainNav: 'teal',
            sideManu: 'white'
          }
        },
        {
          key: 'red',
          value: {
            sideNav: 'red',
            mainNav: 'red',
            sideManu: 'white'
          }
        },
        {
          key: 'orange',
          value: {
            sideNav: 'orange',
            mainNav: 'orange',
            sideManu: 'white'
          }
        },
        {
          key: 'purple',
          value: {
            sideNav: 'purple',
            mainNav: 'purple',
            sideManu: 'white'
          }
        },
        {
          key: 'indigo',
          value: {
            sideNav: 'indigo',
            mainNav: 'indigo',
            sideManu: 'white'
          }
        },
        {
          key: 'cyan',
          value: {
            sideNav: 'cyan',
            mainNav: 'cyan',
            sideManu: 'white'
          }
        },
        {
          key: 'pink',
          value: {
            sideNav: 'pink',
            mainNav: 'pink',
            sideManu: 'white'
          }
        },
        {
          key: 'green',
          value: {
            sideNav: 'green',
            mainNav: 'green',
            sideManu: 'white'
          }
        }
      ];
    }
  },  
  watch: {
    themeColor: {
      handler (val) {
        this.$vuetify.theme.primary = this.colors[val].base;
        
      },
      immediate: true
    }
  },  

};
</script>

<style scoped lang="css">

  .color-option--label {
    position: relative;
    display: block;
    cursor: pointer;
  }
  .color-option--label input[type="radio"] {
    display: none;
  }
  .color-option--label input[type="radio"]+span {
    position: relative;
  }
  .color-option--label input[type="radio"]+span>.overlay {
    display: none;
    position: absolute;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0,0,0,0.3);
    text-align: center;
    line-height: 30px;
    color: #fff;
  }
  .color-option--label input[type="radio"]:checked+span>.overlay {
    display: block;
  }
  .color-option--label .bg {
    background-color: #f1f1f1;
  }
  .color-option--item {
    overflow: hidden;
    display: block;
    box-shadow: 0 0 2px rgba(0,0,0,0.1);
    margin-bottom: 15px;
  }
  .color-option--item--header {
    height: 10px;
  }
  .color-option--item>span {
    display: block;
    float: left;
    width: 50%;
    height: 20px;
  }
  
</style>

