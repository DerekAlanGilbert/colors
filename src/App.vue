<template>
  <div id="app">
    <div class="main-container">
      <h1>Element Forge</h1>
      <hr>
      <div class="row">
        <div class="col-md-6 hidden-overflow">
          <!-- button text, text size, and text color -->
          <div class="form-row">
            <div class="form-group col-md-4">
              <label for="buttonText">Button Text</label>
              <input type="text" class="form-control" id="buttonText" v-model="buttonText">
            </div>
            <div class="form-group col-md-2">
              <label for="buttonText">Color</label>
              <input type="color" class="form-control" id="buttonText" v-model="backgroundColor">
            </div>
            <div class="form-group col-md-4">
              <label for="textSize">Text Size</label>
              <input type="number" class="form-control" id="textSize" v-model="textSize">
            </div>
            <div class="form-group col-md-2">
              <label for="buttonText">Color</label>
              <input type="color" class="form-control" id="textColor" v-model="textColor">
            </div>
          </div>
          <!-- border thickness, color and shadow  -->
          <div class="form-row">
            <div class="form-group col-md-3">
              <label for="buttonPaddingV">Border Size</label>
              <input type="number" class="form-control" v-model="borderThickness">
            </div>
            <div class="form-group col-md-3">
              <label for="buttonPaddingH">Color</label>
              <input type="color" class="form-control" v-model="borderColor">
            </div>
            <div class="form-group col-md-3">
              <label for="buttonPaddingH">Shadow</label>
              <input type="number" class="form-control" v-model="borderShadow">
            </div>
            <div class="form-group col-md-3">
              <label for="buttonPaddingH">Color</label>
              <input type="color" class="form-control" v-model="borderShadowColor">
            </div>
          </div>
          <div class="form-row">
            <div class="form-group col-md-6">
              <label for="buttonPaddingH">Border radius</label>
              <input type="number" class="form-control" v-model="borderRadius">
            </div>
            <div class="form-group col-md-6">
              <label for="borderType">Border Type</label>
              <select id="borderType" class="form-control" v-model="borderType">
                <option selected>solid</option>
                <option>none</option>
              </select>
            </div>
          </div>
          <!-- button padding,  -->
          <div class="form-row">
            <div class="form-group col-md-6">
              <label for="buttonPaddingV">Button padding vertrical</label>
              <input type="number" class="form-control" v-model="paddingVertical">
            </div>
            <div class="form-group col-md-6">
              <label for="buttonPaddingH">Button padding horizontal</label>
              <input type="number" class="form-control" v-model="paddingHorizontal">
            </div>
          </div>
          <!-- button padding,  -->
          <!-- <div class="form-row">
            <div class="form-group col-md-6">
              <label for="buttonPaddingV">Button padding vertrical</label>
              <input type="number" class="form-control" v-model="paddingVertical">
            </div>
            <div class="form-group col-md-6">
              <label for="buttonPaddingH">Button padding horizontal</label>
              <input type="number" class="form-control" v-model="paddingHorizontal">
            </div>
          </div>-->
          <!-- button padding,  -->
          <!-- <div class="form-row">
            <div class="form-group col-md-6">
              <label for="buttonPaddingV">Button padding vertrical</label>
              <input type="number" class="form-control" v-model="paddingVertical">
            </div>
            <div class="form-group col-md-6">
              <label for="buttonPaddingH">Button padding horizontal</label>
              <input type="number" class="form-control" v-model="paddingHorizontal">
            </div>
          </div>-->
          <!-- button padding,  -->
        </div>
        <div class="col-md-6">
          <div class="d-flex flex-column justify-content-center h-100 forge">
            <div class="d-flex justify-content-center">
              <button class :style="computedClass">{{buttonText}}</button>
            </div>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-md-12">
          <textarea name id class="textarea-css" :value="computedClass"></textarea>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  data() {
    return {
      buttonText: 'Welcome',
      borderRadius: 3,
      paddingVertical: 10,
      paddingHorizontal: 10,
      backgroundColor: '',
      textColor: '',
      textSize: 16,
      borderThickness: 1,
      borderShadow: 0,
      borderShadowColor: 0,
      borderType: 'solid',
      borderColor: ''
    }
  },
  computed: {
    computedClass() {
      return `
      border-radius:${this.borderRadius}px;
      padding:${this.paddingVertical}px ${this.paddingHorizontal}px;
      background-color:${this.backgroundColor};
      color:${this.textColor};
      font-size:${this.textSize}px;
      border:${this.borderType} ${this.borderThickness}px ${this.borderColor};
      box-shadow:0px 0px  ${this.borderShadow}px ${this.borderShadowColor};
      `
    }
  },
  components: {
  }
}
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css?family=Lato:300,400,700");
html,
body,
#app {
  font-family: "Lato", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  box-sizing: border-box;
  background: #ff7e5f;
  background: -webkit-linear-gradient(to right, #feb47b, #ff7e5f);
  background: linear-gradient(to right, #feb47b, #ff7e5f);
  margin: 0px;
  padding: 0px;
  height: 100%;
  width: 100%;
}
h1,
h2,
h3,
h4,
h5 {
  font-weight: 100;
}
label {
  // padding: 5px;
}
textarea:focus,
input[type="text"]:focus,
input[type="password"]:focus,
input[type="datetime"]:focus,
input[type="datetime-local"]:focus,
input[type="date"]:focus,
input[type="month"]:focus,
input[type="time"]:focus,
input[type="week"]:focus,
input[type="number"]:focus,
input[type="email"]:focus,
input[type="url"]:focus,
input[type="search"]:focus,
input[type="tel"]:focus,
input[type="color"]:focus,
select:focus,
.uneditable-input:focus {
  border-color: #feb47b;
  box-shadow: 0 0 11px rgba(33, 33, 33, 0.2);
  outline: none;
}
.main-container {
  margin: 100px auto;
  padding: 25px 50px;
  width: 100%;
  max-width: 1200px;
  min-height: 600px;
  // height: 100%;
  background-color: whitesmoke;
  box-shadow: 0 0 11px rgba(33, 33, 33, 0.2);
  border-radius: 8px;
  color: #4c4c4c;
}
.forge {
  border: 1px solid #4c4c4c;
  border-radius: 6px;
}
.textarea-css {
  width: 100%;
  height: 250px;
  margin: 25px 0px;
}
.hidden-overflow {
  overflow-y: scroll;
}
.number-input {
  width: 30px;
}
</style>
