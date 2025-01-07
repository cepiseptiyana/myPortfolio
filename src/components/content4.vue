<script setup>
import { ref } from "vue";
import { Filter } from "bad-words";

// variable v-model
const username = ref("");
const email = ref("");
const message = ref("");

// FILTER KATA KASAR
const filter = new Filter();
filter.addWords(
  "babi",
  "anjing",
  "anjeng",
  "goblok",
  "bangsat",
  "tolol",
  "bagong",
  "careh",
  "tai",
  "brengsek",
  "monyet",
  "sia",
  "asu",
  "kontol",
  "memek",
  "tempe"
);

// REGEX EMAIL
function validateEmail(email) {
  return email.match(
    /^(([^<>()[\]\\.,;:\s@\"]+(\.[^<>()[\]\\.,;:\s@\"]+)*)|(\".+\"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
  );
}

// function Form
function form(event) {
  event.preventDefault();
  // cek username jika kosong / ga di isi
  if (username._value.length != 0) {
    // cek email
    if (!validateEmail(email._value)) return alert("email tidak diketahui !");

    // cek massage kosong
    if (message._value == 0) {
      // cek message apakah mengandung kata-kata kasar
      return alert("anda belum memasukan pesan");
    }

    // FILTER kataKasar
    let filterKataKasar = filter.clean(message._value);

    // PUSH KE WHATSAPP
    const nohp = "6285659519463";
    let encodeMessage = encodeURIComponent(
      `username : ${username._value} \n
email : ${email._value} \n
message : ${filterKataKasar}
`
    );

    let link = `https://web.whatsapp.com/send?phone=${nohp}&text=${encodeMessage}`;
    window.open(link, "_blank");
    console.log(encodeMessage);
  } else {
    alert("silahkan isi username");
  }
}
</script>

<template>
  <div id="contact" class="content4 container-fluid">
    <div class="container">
      <div class="row">
        <h1>- Contact Me -</h1>
      </div>

      <div class="row">
        <h1>Fill Out A Form :</h1>
      </div>

      <div class="row">
        <div class="col-lg">
          <form id="dataForm" action="" autocomplete="off">
            <input
              v-model="username"
              type="text"
              placeholder="username"
              name="username"
            />
            <br />
            <input
              v-model="email"
              type="text"
              placeholder="email"
              name="email"
            />
            <br />
            <input
              v-model="message"
              type="text"
              placeholder="message"
              name="message"
            />
            <br />
            <button @click="form($event)" type="submit">Hubungi</button>
          </form>
        </div>

        <div class="col-lg">
          <div class="row">
            <a href="mailto:cepifams3@gmail.com">
              <img src="../assets/content4/img/gmail.png" alt="" />
              <p>cepifams3@gmail.com</p>
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
