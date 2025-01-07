<script setup>
import { ref } from "vue";

function slide(event) {
  const btnSlide = document.getElementById("btnSlide");
  const slide_menu = document.getElementById("drop-menu");

  document.addEventListener("click", function (event) {
    if (event.target === btnSlide || event.target === slide_menu) {
      slide_menu.style.transform = "translateX(0%)";
    } else {
      slide_menu.style.transform = "translateX(-100%)";
    }
  });

  // console.log(event.target === btnSlide);
  // if (event.target === btnSlide) {
  //   slide_menu.style.transform = "translateX(100%)";
  // } else {
  //   slide_menu.style.transform = "translateX(-100%)";
  // }
}
</script>

<template>
  <div class="nav">
    <div class="container-fluid text-center">
      <div class="row">
        <div class="col">MY PORTOFOLIO</div>
        <div class="col">
          <div class="drop-down">
            <button
              @click="slide($event)"
              id="btnSlide"
              class="btn btn-success"
              type="button"
              aria-expanded="false"
            >
              Menu
            </button>

            <div class="nodrop">
              <a href="">HOME</a>
              <a href="#portofolio">PORTOFOLIO</a>
              <a href="#contact">CONTACT US</a>
            </div>

            <div id="drop-menu" class="drop-menu">
              <a href="">HOME</a>
              <a href="#portofolio">PORTOFOLIO</a>
              <a href="#contact">CONTACT US</a>
            </div>
          </div>
        </div>
        <div class="col">
          <div class="img"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
