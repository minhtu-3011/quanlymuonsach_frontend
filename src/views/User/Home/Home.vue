<template>
  <div class="containPage">
    <div class="titlePage">
      <h2 style="margin-bottom: 20px; font-size: 50px">
        Welcome to
        <span class="titleWeb">T<span class="text-dark">BOOKS</span></span>
      </h2>
    </div>
    <div class="contentPage">
      <!-- Section: Design Block -->
      <section class="">
        <!-- Jumbotron -->
        <div class="text-center text-lg-start">
          <div class="container">
            <div class="row gx-lg-5 align-items-center">
              <div class="col-lg-6 mb-5 mb-lg-0">
                <h1 class="my-5 fw-bold ls-tight titleIntro">
                  <br />
                  <span class="text-primary">Ann Patchett</span>
                </h1>
                <p style="color: hsl(217, 10%, 50.8%)">
                  “Đọc sách rất quan trọng. Đó là cách để chúng ta đặt mình vào
                  hoàn cảnh của người khác, từ đó gây dựng lòng đồng cảm sâu
                  sắc. Thế giới câu chuyện trong sách cho chúng ta khả năng tĩnh
                  lặng và độc lập, hai điều đang biến mất nhanh hơn nước băng
                  tan ở vùng cực.”
                </p>

                <router-link to="/about" class="text-decoration-none">
                  <button class="btnReadMore">Đặt hàng ngay</button>
                </router-link>
              </div>

              <div class="col-lg-6 mb-5 mb-lg-0">
                <div class="card">
                  <div class="imageCup">
                    <img
                      src="https://st5.depositphotos.com/35742636/65542/i/450/depositphotos_655429916-stock-photo-pile-books-bookshelves-library-closeup.jpg"
                      alt=""
                    />
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <!-- Jumbotron -->
      </section>
      <!-- Section: Design Block -->
    </div>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped>
@import "./Home.scss";
</style>
