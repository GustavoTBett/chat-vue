<script>
export default {
  data() {
    return {
      messages: [],
      newMessage: "",
    };
  },
  methods: {
    sendMessage() {
      if (this.newMessage) {
        this.messages.push(this.newMessage);
        this.newMessage = "";
      }
    },
  },
}
</script>

<template>
  <div id="container">
      <div class="atendimento">
        <h1 style="margin-left: 5px;">Atendimento on-line</h1>
      </div>
      <div class="conteudo">
        <div id="chat">
          <div class="caixa1">
            <div>
              <p>Atendente diz:</p>
            </div>
            <div class="mensagemRecebida">
              <p style="margin-left: 5px;">Blablabla Blablabla</p>
            </div>
            <div class="atendenteDiz">
              <p>Atendente diz:</p>
            </div>
            <div class="mensagemRecebida">
              <p style="margin-left: 5px;">Blablabla Blablabla</p>
            </div>
          </div>

          <ul id="caixa2" style="list-style: none;">
            <li>
            <div class="voceDiz">
              <p>Você diz:</p>
            </div>
            <div class="mensagemEnviada">
              <p style="margin-left: 5px;">Blablabla Blablabla</p>
            </div>
            </li>

            <li>
            <div class="voceDiz">
              <p>Você diz:</p>
            </div>
            <div class="mensagemEnviada">
              <p style="margin-left: 5px;">Blablabla Blablabla</p>
            </div>
            </li>

            <div v-for="(message, index) in messages" :key="index">
            <li>
            <div class="voceDiz">
              <p>Você diz:</p>
            </div>
            <div class="mensagemEnviada">
              <p style="margin-left: 5px;">{{ message }}</p>
            </div>
            </li>
           </div>

          </ul>

        </div>
        
        <div class="textoBotao">
          <div class="inputMensagem">
            <input
              v-model="newMessage"
              id="inputTexto-enviarMensagem"
              type="text"
              placeholder="Digite sua mensagem..."
              size="45"
            />
          </div>
          <div class="enviarMensagem">
            <button type="button" id="botaoEnviar" @click="sendMessage">
              <strong>Enviar</strong>
            </button>
          </div>
        </div>
      </div>
    </div>
</template>

<style scoped>
*{
    margin: 0;
}

#container {
    display: flex;
    flex-direction: column;
    height: 100vh;
    justify-content: center;
    align-items: center;
}

.atendimento {
    display: flex;
    border: 1px solid white;
    font-size: 8px;
    font-weight: none;
    font-family: Comic Sans MS, Comic Sans, cursive;
    width: 500px;
    color: lightgreen;
}

.conteudo {
    display: flex;
    border: 1px solid white;
    flex-direction: column;
    height: 550px;
    width: 500px;
}

#chat {
    display: flex;
    flex-direction: column;
    border: 1px solid white;
    height: 480px;
    width: 488px;
    margin-top: 1%;
    margin-left: 1%;
    overflow: auto;
    padding-bottom: 10px;
}
.mensagemRecebida {
    display: flex;
    justify-content: flex-start;
    align-items: center;
    border: 1px solid white;
    width: 300px;
    height: 25px;
}

.atendenteDiz {
    display: flex;
    margin-top: 2%;
}

.mensagemEnviada {
    display: flex;
    justify-content: flex-start;
    align-items: center;
    border: 1px solid white;
    width: 300px;
    height: 25px;
}

.voceDiz {
    display: flex;
    margin-top: 2%;
}

 .caixa1 {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    margin-left: 2%;
    margin-top: 30%;
 }

 #caixa2 {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    margin-right: 2%;
    margin-top: 10%;
    margin-bottom: 0%;
 }

 .textoBotao {
    display: flex;
    flex-direction: row;
    gap: 10px;
}

.inputMensagem {
    display: flex;
    height: 30px;
    margin-top: 3.5%;
    margin-left: 1%;
    border: 1px solid white;
}

.enviarMensagem {
    display: flex;
    height: 30px;
    margin-top: 3.5%;
    width: 90px !important;
    font-family: Comic Sans MS, Comic Sans, cursive;
    border: 1px solid white;
}

#botaoEnviar {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 110px;
    color: green;
    font-size: 15px;
}
</style>