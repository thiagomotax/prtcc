<template>
  <v-container>
    <FormHeaderNew
      boxColor="rgb(176, 161, 198)"
      textLeft1="INICIAL"
      textLeft2="2 DE 2"
      textRight1="FORMULÁRIO 2"
      textRight2="CLIENTE"
      textMiddle1="AVALIAÇÃO DE TECNOLOGIA ASSISTIVA- PREDISPOSIÇÃO AO USO"
      textMiddle2="ATD PA- Br"
      textMiddle3="Para Comparar Dispositivo e Obter Resultados Desejados"
    />

    <FormInfo
      name="Nome"
      age="Idade"
      shortGoals="Objetivos a curto prazo da T.A (6 meses)"
      date="Data de Avaliação"
      longGoals="Objetivos a longo prazo da T.A (1 ano +)"
      appraiser="Avaliador"
    />

    <h3>Instruções:</h3>
    <span>
      Escreva o nome de cada dispositivo que você está considerando no espaço
      abaixo de “Dispositivo”. Observe o exemplo dado. Classifique cada
      dispositivo de TA considerando os 12 (A-L)de acordo com a escala abaixo,
      depois circule os 3 itens (A-L) que quais importam para você. Escreva a
      classificação nos espaços apropriados.</span
    >
    <v-row>
      <v-col cols="12" sm="6" md="3">
        <p>5 = O tempo todo (100% do tempo)</p>
        <p>4 = Frequentemente (aproximadamente 75% do tempo)</p>
        <p>3 = Metade do tempo, neutro( aproximadamente 50% do tempo)</p>
      </v-col>
      <v-col cols="12" sm="6" md="3">
        <p>2 = Ás vezes (aproximadamente 25% do tempo)</p>
        <p>1 = Nunca (0% do tempo)</p>
        <p>0 = Não se aplica.</p>
      </v-col>
    </v-row>

    <v-row class="align-center pa-n10">
      <v-col cols="12" sm="6" md="1">
        <p></p>
      </v-col>

      <v-col cols="12" sm="6" md="4 ">
        <p>Questão</p>
      </v-col>

      <v-col cols="12" sm="6" md="1">
        <p>Exemplo: Bengala de 4 apoios</p>
      </v-col>

      <v-col cols="12" sm="6" md="2">
        <p>Dispositivo 1</p>
        <v-text-field placeholder="(nome do dispositivo)" disabled></v-text-field>
      </v-col>

      <v-col cols="12" sm="6" md="2">
        <p>Dispositivo 2</p>
        <v-text-field placeholder="(nome do dispositivo)" disabled></v-text-field>
      </v-col>

      <v-col cols="12" sm="6" md="2">
        <p>Dispositivo 3</p>
        <v-text-field placeholder="(nome do dispositivo)" disabled></v-text-field>
      </v-col>
    </v-row>

    <div v-for="(question, index) in questions" :key="question.id">
      <question-type-3
        :id="question.id"
        :text="question.text"
        :exampleNumber="question.exampleNumber"
        :color="index % 2 == 0 ? 'rgb(229, 223, 237)' : ''"
        :finalComment="questions.length-1 === index ? 'Revise cada pontuação total acima. Dispositivo com a pontuação mais alta é o mais elegível ( número máximo de pontos = 60). Entretanto, quando a pontuação total dos dispositivos for próxima, deverá ser dado maior peso a soma dos três itens marcados como mais importantes.': ''"
      />
      <!-- <question-type-3 finalComment="Revise cada pontuação total acima. Dispositivo com a pontuação mais alta é o mais elegível ( número máximo de pontos = 60). Entretanto, quando a pontuação total dos dispositivos for próxima, deverá ser dado maior peso a soma dos três itens marcados como mais importantes."/> -->
    </div>

    <h3>Comentários e Anotações:</h3>
    <br />
    <v-container fluid>
      <v-textarea
        label="Escreva aqui os comentários e anotações"
        auto-grow
        outlined
        rows="3"
        row-height="25"
      ></v-textarea>
    </v-container>
  </v-container>
</template>

<script>
import FormHeaderNew from "../components/FormHeaderNew";
import FormInfo from "../components/FormInfo";
import QuestionType3 from "../components/QuestionType3";

export default {
  components: {
    FormHeaderNew,
    FormInfo,
    QuestionType3
  },
  name: "Form2",
  data() {
    return {
      questions: [
          {
          id:"A",
          text:"Este dispositivo de TA me ajudará a alcançar meus objetivos (incluindo os objetivos primário da TA escritos acima)",
          exampleNumber:"5"
         },
          {
          id:"B",
          text:"Este dispositivo me beneficiará e melhorará minha qualidade de vida ",
          exampleNumber:"3"
         },
          {
          id:"C",
          text:" Eu estou confiante que eu sei como usar este dispositivo e suas variações",
          exampleNumber:"4"
         },
          {
          id:"D",
          text:"Eu me sentirei mais seguro ( em segurança, seguro de mim mesmo) usando este dispositivo de TA",
          exampleNumber:"5"
         },
         {
          id:"E",
          text:"Este dispositivo se encaixará bem à minha rotina diária.",
          exampleNumber:"4"
         },
          {
          id:"F",
          text:"Eu tenho capacidade e vigor para usar este dispositivo sem desconforto, estresse ou fadiga",
          exampleNumber:"3"
         },
          {
          id:"G",
          text:" há suporte, assistência e acomodações para o uso bem sucedido deste dispositivo",
          exampleNumber:"4"
         },
         {
          id:"H",
          text:"Este dispositivo se encaixará fisicamente em todos os ambientes desejados (carro, sala de estar etc…)",
          exampleNumber:"3"
         },
          {
          id:"I",
          text:"Eu vou me sentir confortável (não vou ficar constrangido) usando este dispositivo perto dos meus amigos ",
          exampleNumber:"4"
         },
         {
          id:"J",
          text:"Eu vou me sentir confortável (não vou ficar constrangido) usando este dispositivo perto dos meus familiares ",
          exampleNumber:"4"
         },
          {
          id:"K",
          text:"Eu me sentirei confortável (não vou ficar constrangido) usando este dispositivo na escola ou no trabalho",
          exampleNumber:"4"
         },  
          {
          id:"L",
          text:" Eu me sentirei confortável(e não vou me sentir constrangido ) usando este dispositivo na minha comunidade )",
          exampleNumber:"4"
         },
          {
          id:"L",
          text:" TOTAL (soma de A-L)",
          exampleNumber:"47"
         },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.mediumPurple {
  background-color: rgb(205, 192, 218);
}
</style>