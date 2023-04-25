<script setup lang="ts">
  import { ref } from 'vue';
  import Title from '@/components/Title.vue';


  const isMenuOpen = ref(false);

  const toggleMenu = () => {
    isMenuOpen.value = !isMenuOpen.value;
    console.log(isMenuOpen.value);
  };

</script>

<template>
  <header>
    <div class="logo">
      <h1>Sneakers</h1>
    </div>
    <div
      @click="toggleMenu"
      class="hamburgerBtn"
      :class="{ open: isMenuOpen }"
    >
      <span></span>
      <span></span>
      <span></span>
    </div>
  </header>
  <div class="kv">
    <img src="../assets/sample.jpg" alt="">
  </div>
  <div class="title">
    <Title title="New Arrivals" />
  </div>
  <div class="gridArea">
    <div class="gridAreaImg">
      <img src="../assets/sample.jpg" alt="">
    </div>
    <div class="gridAreaImg">
      <img src="../assets/sample.jpg" alt="">
    </div>
    <div class="gridAreaImg">
      <img src="../assets/sample.jpg" alt="">
    </div>
    <div class="gridAreaImg">
      <img src="../assets/sample.jpg" alt="">
    </div>
    <div class="gridAreaImg">
      <img src="../assets/sample.jpg" alt="">
    </div>
    <div class="gridAreaImg">
      <img src="../assets/sample.jpg" alt="">
    </div>
  </div>
  <div class="contactArea">
    <form action="">
      <input type="text" placeholder="お名前">
      <input type="text" placeholder="メールアドレス">
      <input type="text" placeholder="お問い合わせ内容">
      <input type="submit" value="送信">
    </form>
  </div>
</template>

<style scoped lang="scss">

header{

  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 10px;

  .logo{

    p{
      font-size: 2rem;
      font-weight: 700;
    }

  }

  // .openが付いたらspanが×になる
  .hamburgerBtn{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    width: 2rem;
    height: 2rem;
    cursor: pointer;

    span{
      width: 100%;
      height: 0.25rem;
      background-color: #000;
      border-radius: 10px;
    }

    &.open{

      span{

        &:nth-child(1){
          transform-origin: 0% 0%;
          transform: rotate(45deg);
        }

        &:nth-child(2){
          opacity: 0;
        }

        &:nth-child(3){
          transform-origin: -25% 0%;
          transform: rotate(-45deg);
        }

      }

    }

  }

}

.kv{
  width: 100%;
  height: 80vh;
  background-color: #000;
  position: relative;

  img{
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
}

.title{
  text-align: center;
  margin: 10px;
}

.gridArea{
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: repeat(2, 1fr);
  gap: 10px;
  margin: 10px;

  .gridAreaImg{
    width: 100%;
    height: 100%;
    background-color: #000;
    border-radius: 10px;
    overflow: hidden;

    img{
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  }
}

.contactArea{

  width: 60%;
  margin: 0 auto;

  form{
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin: 10px;

    input{
      width: 100%;
      height: 2rem;
      margin: 10px;
      padding: 0 10px;
      border-radius: 10px;
      border: 1px solid #000;
    }

    input[type="submit"]{
      width: 50%;
      height: 2rem;
      margin: 10px;
      padding: 0 10px;
      border-radius: 10px;
      border: 1px solid #000;
      background-color: #000;
      color: #fff;
      cursor: pointer;
    }
  }

}


</style>
