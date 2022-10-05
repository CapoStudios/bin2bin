<template>
  <form class="add-form">
    <div class="form-control">
      <label>Decimal</label>
      <input type="text" autocomplete="off" placeholder="100" id="dec" @input="Decimal"/>
    </div>
    <div class="form-control">
      <label>Binary</label>
      <input type="text" autocomplete="off" placeholder="1100100" id="bin" @input="Binary"/>
    </div>
    <div class="form-control">
      <label>Hexadecimal</label>
      <input type="text" autocomplete="off" placeholder="64" id="hex" @input="Hexadecimal"/>
    </div>
  </form>
</template>

<script>
export default {
  name: "Converter",
  data() {
    return {
      dec: "",
      bin: "",
      hex: "",
      decValue: document.getElementById("dec"),
      binValue: document.getElementById("bin"),
      hexValue: document.getElementById("hex"),
    };
  },
  methods: { 
    Decimal() {
        if (document.getElementById("dec").value == "") {
            return "";
        } else if(document.getElementById("dec").value != ""){
            document.getElementById("hex").value = (document.getElementById("dec").value >>> 0).toString(16).toUpperCase();
            document.getElementById("bin").value = (document.getElementById("dec").value >>> 0).toString(2);
        }
    },
    Binary(){
        if (document.getElementById("bin").value == "") {
            return "";
        } else if(document.getElementById("bin").value != ""){
            document.getElementById("hex").value = parseInt(document.getElementById("bin").value, 2).toString(16).toUpperCase();
            document.getElementById("dec").value = parseInt(document.getElementById("bin").value, 2);
        }
    },
    Hexadecimal(){
        if (document.getElementById("hex").value == "") {
            return "";
        } else if(document.getElementById("hex").value != ""){
            document.getElementById("bin").value = parseInt(document.getElementById("hex").value, 16).toString(2).padStart(0, '0');
            document.getElementById("dec").value = parseInt(document.getElementById("hex").value, 16);
        }
    },
  }
};
</script>

<style scoped>
.add-form {
  margin-bottom: 10px;
  font-weight: bold;
  font-family: "Poppins";
}
.form-control {
  margin: 20px 0;
}
.form-control label {
  display: block;
  margin-left: 7px;
  font-size: 1.1rem;
  cursor: text;
}
.form-control input {
  width: 97%;
  height: 40px;
  margin: 5px;
  font-size: 17px;
  font-family: "Poppins";
  border: 2px solid #1c1c1c;
  font-weight: 200;
  border-radius: 10px;
  padding: 0 10px;
}

.form-control input:focus {
  border: 2px solid #1c1c1c;
  outline: none;
}

@media only screen and (max-width: 600px)  {
  .form-control {
    margin: 10px 0;
  }
  .form-control label {
    font-size: 1rem;
  }
  .form-control input {
    width: 97%;
    height: 40px;
    margin: 5px;
    font-size: 17px;
    border: 2px solid #1c1c1c;
    font-weight: 400;
    border-radius: 10px;
    padding: 0 10px;
    -webkit-tap-highlight-color: rgba(0,0,0,0);
  }

  .form-control input:focus {
    border: 2px solid #1c1c1c;
    outline: none;
  }
}
</style>
