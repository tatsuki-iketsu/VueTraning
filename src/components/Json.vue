<script>
export default {
  name: 'Home',
  setup() {
    // setupで次のように宣言された変数はリアクティブではない
    let name = '山田' 
    let age = 50

    const clickAnswer = (a) => {
      alert(`Clicked:${a}`);
    }

    // return { name: name, age: age} //左がtemplate、右がsetupで宣言した変数
    return { name, age, clickAnswer} //上のように同じ場合はこのように省略できる
  },

  data() {
    return {
      age: 45, //リアクティブ
      learnGroup:{
        question:[{
          question:"CSSで同じフォルダ内にある\ncommon.cssファイルをインポートする際の\n正しい記述を選択してください。",
          choices:["@import url(common.css);","import{common.css} ;","import.common.css);","import-url(common.css);",],
          answer:"@import url(common.css);",
          input:"",        }
        ]
      }
    }
  }

}

</script>
<template>
  <div v-for="(learn,i) in learnGroup.question">
    <div class="question">
     <h2>問題{{i+1}}</h2><p>{{learn.question}}</p>
    </div>
    <!-- <div>
      {{learn.choices[0]}}
      {{learn.choices[1]}}
      {{learn.choices[2]}}
    </div> -->
    
    <div v-for="(choice,i) in learn.choices" class="answer">
      <input type="radio"  id={{choice}} :value="choice" />
      {{i+1}}：<label>{{choice}}</label>
    </div>
    <button @click="clickAnswer(`{{learn}}`)">回答を見る</button>
</div>

</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    align-items: center;
  }
.question{
  white-space: pre-wrap	
}
}

</style>
