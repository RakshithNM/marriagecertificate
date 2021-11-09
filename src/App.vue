<template>
  <div id="app">
    <Header class="no-print" title="MARRIAGE CERTIFICATE" subText="SHREE PERNE MUCHILOT BHAGAVATHI KSHETHRA"/>
    <Form
      class="no-print"
      type="groom"
      @name-change="updateNameGroom($event, 'groomName')"
      @address1-change="updateAddress1Groom($event, 'groomAddress1')"
      @address2-change="updateAddress2Groom($event, 'groomAddress2')"
      @address3-change="updateAddress3Groom($event, 'groomAddress3')" />
    <Form
      class="no-print"
      type="bride"
      @name-change="updateNameBride($event, 'brideName')"
      @address1-change="updateAddress1Bride($event, 'brideAddress1')"
      @address2-change="updateAddress2Bride($event, 'brideAddress2')"
      @address3-change="updateAddress3Bride($event, 'brideAddress3')" />

    <form class="no-print center">
      <div class="col-md-6 col-sm-12 col-xs-12 form-group">
        <label for="date">DATE OF MARRIAGE</label>
        <input
          class="form-control" placeholder="YYYY-MM-DD"
          id="date" name="date" type="text"
          v-model="date" />

        <label for="registernumber">REGISTER NUMBER</label>
        <input
          class="form-control" placeholder="REGISTER NUMBER"
          id="registernumber" name="registernumber" type="text"
          v-model="registerNumber" />
      </div>
    </form>

    <div class="containerd">
      <div class="centered">
        <div>
          <h1><strong>{{ nameGroom }}</strong></h1>
          <h3>{{ address1Groom }}</h3>
          <h3>{{ address2Groom }}</h3>
          <h3>{{ address3Groom }}</h3>
        </div>
        <h3 class="and" v-show="nameGroom && nameBride">AND</h3>
        <div>
          <h1><strong>{{ nameBride }}</strong></h1>
          <h3>{{ address1Bride }}</h3>
          <h3>{{ address2Bride }}</h3>
          <h3>{{ address3Bride }}</h3>
        </div>
      </div>
      <h3 class="date">{{ date }}</h3>
      <h3 class="registerNumber">{{ registerNumber }}</h3>
      <img src="./assets/base.jpg" alt="certificate base image" />
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Form from './components/Form.vue'

export default {
  name: 'App',
  components: {
    Header,
    Form
  },
  data() {
    return {
      nameGroom: "",
      address1Groom: "",
      address2Groom: "",
      address3Groom: "",
      nameBride: "",
      address1Bride: "",
      address2Bride: "",
      address3Bride: "",
      date: "",
      registerNumber: ""
    }
  },
  methods: {
    updateNameGroom(inName, inType) {
      if(inType === 'groomName') {
        this.nameGroom = inName;
      }
    },
    updateAddress1Groom(inAddress1, inType) {
      if(inType === 'groomAddress1') {
        this.address1Groom = inAddress1;
      }
    },
    updateAddress2Groom(inAddress2, inType) {
      if(inType === 'groomAddress2') {
        this.address2Groom = inAddress2;
      }
    },
    updateAddress3Groom(inAddress3, inType) {
      if(inType === 'groomAddress3') {
        this.address3Groom = inAddress3;
      }
    },
    updateNameBride(inName, inType) {
      if(inType === 'brideName') {
        this.nameBride = inName;
      }
    },
    updateAddress1Bride(inAddress1, inType) {
      if(inType === 'brideAddress1') {
        this.address1Bride = inAddress1;
      }
    },
    updateAddress2Bride(inAddress2, inType) {
      if(inType === 'brideAddress2') {
        this.address2Bride = inAddress2;
      }
    },
    updateAddress3Bride(inAddress3, inType) {
      if(inType === 'brideAddress3') {
        this.address3Bride = inAddress3;
      }
    },
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.containerd {
  position: relative;
  text-align: center;
  color: black;
  width: 21cm;
  height: 29.7cm;
}

.containerd > h3 {
  font-size: 18px;
}

.centered {
  position: absolute;
  top: 45%;
  left: 50%;
  transform: translate(-50%, -50%);
}

h1 {
  font-size: 26px;
}

.centered > div > h3 {
  margin: 0;
  font-size: 24px;
}

.centered > div > h1 {
  margin: 10px;
}

.date {
  position: absolute;
  top: 66%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.registerNumber {
  position: absolute;
  top: 71%;
  left: 50%;
  transform: translate(-50%, -50%);
}

#registernumber {
  margin-bottom: 20px;
}

.center {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 0 auto;
}

input {
  margin-bottom: 20px;
}

.and {
  margin-top: 10px;
  font-size: 20px;
}

@page {
  margin: 0;
}

@media print {
  html, body {
    height: 100%;
    margin: 0 !important;
    padding: 0 !important;
    overflow: hidden;
  }

  .no-print, .no-print * {
    display: none !important;
  }
}
</style>
