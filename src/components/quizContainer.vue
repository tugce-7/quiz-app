<template>
  <!-- quiz container -->
  <div class="overflow-hidden bg-white flex-none container relative shadow-lg rounded-lg px-12 py-6" >
    <img
      src="@/assets/images/abstract.jpg"
      alt=""
      class="absolute -top-20 left-0 object-none"
    />

    <!-- contents -->
    <div v-if="quiz==true">
    <div
      v-for="(question, index) in questions.slice(a, b)"
      :key="index"
      class="relative z-20"
    >
      <!-- score container -->
      <div class="text-right text-gray-800">
        <p class="text-sm leading-3">Score</p>
        <p class="font-bold">{{score}}</p>
      </div>

      <!-- question container -->
      <div
        class="rounded-lg bg-gray-100 p-2 neumorph-1 text-center font-bold text-gray-800 mt-8"
      >
        <div class="bg-white p-5">
          {{ question.question }}
        </div>
      </div>

      <!-- options container -->

      <div class="mt-8">
        <!-- option container -->

        <div 
          v-for="(items, index) in question.propositions"
          :key="index"
          class="neumorph-1 option-default bg-gray-100 p-2 rounded-lg mb-3 relative"
          :class="select? check(items): ''"
          
          @click="selectResponse(items)"
        >
          <div
            class="bg-blue-700 p-1 transform rotate-45 rounded-md h-10 w-10 text-white font-bold absolute right-0 top-0 shadow-md"
          >
            <p class="transform -rotate-45">+10</p>
          </div>
          <div class="rounded-lg font-bold flex p-2">
            <!-- option ID -->
            <div class="p-3 rounded-lg">{{ items.choise }}</div>

            <!-- option name -->
            <div class="flex items-center pl-6">{{ items.props }}</div>
          </div>
        </div>
      </div>

      <!-- progress indicator container -->
      <div class="mt-8 text-center">
        <div class="h-1 w-12 bg-gray-800 rounded-full mx-auto"></div>
        <p class="font-bold text-gray-800">{{ b }}/{{ questions.length }}</p>
      </div>
    </div>
    </div>
    <!-- end of the quiz -->
    <div v-if="quiz==false " class="relative z-20">  
      <div class="rounded-lg bg-gray-100 p-2 neumorph-1 text-center font-bold text-gray-800 mt-8"     >
        <div class="bg-white p-5">
          Sınavı tamamladınız.  
    <div class="mt-8 text-center">
      <span class="sm:ml-3">
        <button
        @click="restartQuiz"
          type="button"
          class="inline-flex items-center px-8 py-2 border border-transparent rounded-md shadow-sm text-sm font-medium text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
        >
          Restart
        </button>
      </span>
         </div>


        </div>
    </div>
    </div>
    



    <div class="mt-8 text-center">
      <span class="sm:ml-3">
        <button
        @click="skipQuestion"
          type="button"
          class="inline-flex items-center px-8 py-2 border border-transparent rounded-md shadow-sm text-sm font-medium text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
        >
          Skip
        </button>
      </span>
      <span class="sm:ml-10">
        <button
        @click="backQuestion"
          type="button"
          class="inline-flex items-center px-8 py-2 border border-transparent rounded-md shadow-sm text-sm font-medium text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
        >
          Back
        </button>
      </span>
      <span class="sm:ml-1">
        <button
        @click="nextQuestion"
          type="button"
          class="inline-flex items-center px-8 py-2 border border-transparent rounded-md shadow-sm text-sm font-medium text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
        >
          Next
        </button>
      </span>
    </div>



  </div>
</template>
<script>
export default {
  data () {
    return {
      a: 0,
      b: 1,
      select: false,
      score:0,
      quiz:true,
      score_show:false,
      isFinish:false,
      questions: [
        {
          question: 'Javascript hangi HTML etiketi içerisinde yer alır?',
          propositions: [
            { props: '<script>', choise: 'A' ,correct:true},
            { props: '<js>', choise: 'B' },
            { props: '<scripting>', choise: 'C' },
            { props: '<javascript>', choise: 'D' }
          ]
        },
        {
          question: 'Bir AlertBox a nasıl "Merhaba Dünya" yazarsınız?',
          propositions: [
            { props: 'msg("Hello World")', choise: 'A' },
            { props: 'alertBox("Hello World")', choise: 'B' },
            { props: 'alert("Hello World")',correct:true, choise: 'C' },
            { props: 'msgBox("Hello World")', choise: 'D' }
          ]
        },
        
         {
          question:"Javascriptte IF Statement nasıl yazılır?",
          propositions:[
            {props:'if i = 5 then',choise: 'A'},
            {props:'if (i == 5)',correct:true, choise: 'B'},
            {props:'if i == 5 then', choise: 'C'},
            {props:'if i = 5', choise: 'D'},
            
            
          ]
          
        },
        {
          question:"For döngüsü başlatmak için hangisi yazılmalıdır ?",
          propositions:[
            {props:'for i = 1 to 5',choise: 'A'},
            {props:'for (i <= 5; i++)' ,choise: 'B'},
            {props:'for (i = 0; i <= 5)' ,choise: 'c'},
            {props:'for (i = 0; i <= 5; i++)', choise: 'D',correct:true},
            
          ]
          
        },
        {
          question:"Javascriptte yorum satırı nasıl eklenir?",
          propositions:[
            {props:"'Bu bir yorum satırı",choise: 'A'},
            {props:'//Bu bir yorum satırı',correct:true, choise: 'B'},
            {props:'<!--Bu bir yorum satırı-->', choise: 'C'},
            {props:'*Bu bir yorum satırı' ,choise: 'D'},
            
          ]
          
        }
      ]
    }
  },
  methods: {
    nextQuestion() {

      if(this.questions.length -1 == this.a){
        this.score=true;
        this.quiz=false;
      }
      else {
      this.a++ ; this.b++;
      this.select = false ;
      }    
      },
      backQuestion() {
        if(this.a == 0){
        alert("Sınava başladıktan sonra çıkış yapamazsınız!");
       
      
      }
      else {

      this.a-- ; this.b--;
      this.select = false ;
      }
      },
      skipQuestion() {

      if(this.questions.length -1 == this.a){
        this.score=true;
        this.quiz=false;
      }
      else {
      this.a++ ;
      this.b++;
      
      }
    
      },
      restartQuiz(){
        Object.assign(this.$data, this.$options.data()); //reset data
      },
      selectResponse(e){
        this.select= true;

        if(e.correct){
          this.score+=10;
        }
      },
      check(status){
        return (status.correct)? 'option-correct' : 'option-wrong';
      },
    
  }
}
</script>
