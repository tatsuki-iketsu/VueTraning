<script>
export default {
  name: 'Home',
  setup() {
    // setupで次のように宣言された変数はリアクティブではない
    let name = '山田' 
    let age = 50

    const clickAnswer = (event,a) => {
//      alert(`Clicked:${a}`);

      alert(`Clicked:${a}`);
      // this.learnGroup.question[0].dispAnswer =`a`;
      
      // dispAnswer = `a`;
      
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
          selectAnswers:["@import url(common.css);","import{common.css} ;","import.common.css);","import-url(common.css);",],
          answer:"@import url(common.css);",
          dispAnswer:"ここに回答がでる",
          input:"",        }
        ]
      }
    }
  },
  methods: {
    clickAnswerB(event,a) {
      alert(`Clicked:${a}`);

      this.learnGroup.question[0].dispAnswer =this.learnGroup.question[0].answer;
},
//         const clickAnswer = (event,a) => {
// //      alert(`Clicked:${a}`);

//       alert(`Clicked:${a}`);
//       // this.learnGroup.question[0].dispAnswer =`a`;
      
//       // dispAnswer = `a`;
      
//     }
    }

}

// 案：ラジオボタンクリックでquestionに回答を代入するメソッド、最後に答え合わせ

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
    <div>
    <p v-for="(selectAnswers,i) in learn.selectAnswers" class="answer">
      <label><input type="radio" id={{selectAnswers}} :value="selectAnswers" name="1"/>
      {{i+1}}：{{selectAnswers}}</label>
    </p>
    <button @click="clickAnswerB($event,i+1)">回答を見る</button>
    {{learn.dispAnswer}}
    </div>
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
