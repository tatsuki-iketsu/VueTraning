<script>
export default {
  name: 'Home',
  setup() {
    // setupで次のように宣言された変数はリアクティブではない
    let name = '山田' 
    let age = 50

    const handleClick = () => {
      console.log('Clicked');
    }

    // return { name: name, age: age} //左がtemplate、右がsetupで宣言した変数
    return { name, age, handleClick} //上のように同じ場合はこのように省略できる
  },
  data() {
    return {
      age: 45, //リアクティブ
      learnGroup:{
        question1:{
          question:"common.cssをインポートする記述は？",
          answer:"@import url(common.css);",
          input:"",        }
      }
    }
  }
}
</script>

<template>
  <div>
    <h1>Input!!!!!!</h1>
    <div>
    問題:{{learnGroup.question1.question}}
    </div>
    <div>
    回答:{{learnGroup.question1.answer}}
    </div>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
