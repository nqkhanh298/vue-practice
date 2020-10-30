<template>
  <section>
    <div class="mode-controll--res">
      <button @click="changeMode()"><i class="fal fa-angle-right fa-3x"></i></button>
    </div>

    <div style="width: calc((100vw - 800px)/2);">
      
    </div >

    <div class="mode-controll">
        <button :class="{'isActive': !edit}" @click="changeMode()">Edit</button>
        <button :class="{isActive: edit}" @click="changeMode()">View</button>
    </div>

    <div class="main-container">
      <keep-alive>
        <component :is="component"></component>
      </keep-alive>
    </div>
  </section>
</template>

<script>
import View from './components/form-view'
import Edit from './components/form-edit'

export default {
  components: {
    'form-view': View,
    'form-edit': Edit,
  },
  data () {
    return {
      component: 'form-view',
      edit: true,
      res: false,
    }
  },
  methods: {
    changeMode() {
      if(this.component == 'form-view') {
        this.component = 'form-edit'
      } else {
        this.component = 'form-view'
      }
      this.edit = !this.edit
    }
  }
}
</script>

<style>
:root {
  --main-color: #ea4815;
}

* {
  margin: 0;
  box-sizing: border-box;
  font-family: 'Roboto', sans-serif;
}

section {
  display:flex;
  background-color: thistle;
}

.hide {
  display: none !important;
}

.main-container {
  width: 100%;

  margin-top: 50px;
  margin-bottom: 50px;

  cursor: context-menu;
}

.mode-controll {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 150px;
  margin-left: 40px;
  position: fixed;
}

.mode-controll button {
  width: 150px;
  height: 150px;
  margin-top: 20px;
  /* position: fixed; */

  font-size: 40px;
  background-color: white;
  border: 2px solid black;
}

.mode-controll button:hover {
  cursor: pointer;
  background-color: var(--main-color);
}

.isActive {
  border-width: 8px !important;
  background-color: var(--main-color) !important;
}

.mode-controll--res {
  position: fixed;
  display: none;
}

.mode-controll--res button {
  margin-top: 45vh;
}

@media only screen and (max-width: 1232px) {
  .mode-controll {
    display: none;
  }

  .mode-controll--res {
    display: block; 
  }
 
}

</style>