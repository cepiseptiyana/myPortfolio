<script setup>
import { ref } from "vue";
const messagePertanyaan = ref("");

function textMove() {
  // buat array = ["who are you","your project"]
  const optionPertanyaan = ["who are you", "your project"];

  // cek jika user ga masukan input
  if (messagePertanyaan._value !== "") {
    // // cek jika text input tidak sama
    if (optionPertanyaan.includes(messagePertanyaan._value)) {
      // jika value nya "#portofolio"
      if (messagePertanyaan._value === "who are you") {
        window.location.href = "#portofolio";
      }
      if (messagePertanyaan._value === "your project") {
        // jika value nya "myProject"
        window.location.href = "#myProject";
      }
    } else {
      // else alert('option yang di masukan salah')
      alert(`
      Option Salah :(
      Silahkan Pilih Option Yang Ada :)
      `);
    }
  } else {
    alert("Masukan Option :)");
  }
}
</script>

<template>
  <!-- Content 1 -->
  <div class="content-1">
    <div class="container text-center">
      <div class="row">
        <!-- BUKU -->
        <div class="col">
          <div class="buku"></div>
          <div class="pensil1"></div>
          <div class="pensil2"></div>
        </div>

        <!-- KOMPUTER -->
        <div class="col">
          <div class="komputer">
            <div class="kotak">Welcome My Portfolio</div>
            <div class="textPertanyaan">
              <p>ketik pertanyaan option :</p>
              <p>> who are you</p>
              <p>> your project</p>
              <textarea
                name=""
                id=""
                v-html="messagePertanyaan"
                disabled
              ></textarea>
            </div>
          </div>
        </div>

        <!-- GELAS -->
        <div class="col">
          <div class="gelas"></div>
          <div class="air1"></div>
          <div class="air2"></div>
          <div class="air3"></div>
        </div>
      </div>

      <!-- ROW 2 -->
      <!-- FORM INPUT -->
      <div class="row">
        <div class="col">
          <form action="" method="">
            <input
              v-model="messagePertanyaan"
              type="text"
              placeholder="ketikan pertanyaan"
            />
            <button
              class="button"
              @click="textMove()"
              type="submit"
              onclick="event.preventDefault();"
            >
              submit
            </button>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>
