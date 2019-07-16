# Jogo da velha

.![jogo da veha](https://abrilsuperinteressante.files.wordpress.com/2018/07/jogo_da_velha_-_tic_tac_toe.png?w=382&h=323)

## Objetivo

Projeto desenvolvido com o intuito de melhorar as habilidades com JavaScript

## Técnologias

- HTML
- CSS
- JavaScript

## HTML

`````html

<html>
<head>
<title>Jogo da Velha</title>
<meta charset="utf-8">
<style type="text/css">
body{
  margin-left: 36%;
  margin-top: 6%;
  font-family: cursive;
}
h1{
  text-align: center;
  width: 47%;
}
button{
  padding-top: 1%;
  padding-bottom: 1%;
  background: rgb(214,189,10);
}
.x{
width: 130px;
height: 130px;
background: rgb(211,48,5);
font-size: 80px;
color: rgb(214,189,10);
cursor: pointer;
}
.xy{
background: rgb(0,0,0)
}
table{
  display: inline-block;
}
#xxx{
  display: inline-block;
  width: 40%;
  font-size: 130%;
  font-weight: bold;
}
td{
  text-align: center;
}
</style>
</head>
<body>
  <h1>JOGO DA VELHA</h1>
  <table class="xy">
    <tr>
      <td id="cel11" class="x" onclick="xx(this.id);certeza();"></td>
      <td id="cel12" class="x" onclick="xx(this.id);certeza();"></td>
      <td id="cel13" class="x" onclick="xx(this.id);certeza();"></td>
    </tr> 
    <tr>
      <td id="cel21" class="x" onclick="xx(this.id);certeza();"></td>
      <td id="cel22" class="x" onclick="xx(this.id);certeza();"></td>
      <td id="cel23" class="x" onclick="xx(this.id);certeza();"></td>
    </tr>
    <tr>
      <td id="cel31" class="x" onclick="xx(this.id);certeza();"></td>
      <td id="cel32" class="x" onclick="xx(this.id);certeza();"></td>
      <td id="cel33" class="x" onclick="xx(this.id);certeza();"></td>
    </tr>
  </table>
  <p id="xxx">Esta na vez do jogador: <img id="imagem" src=""></p>
  <br><button onclick="novoGame();">NEW GAME</button> 
  <p id="bc">Numero de vitórioas jogador 1 (X): 0</p>
  <p id="jogadas">Numero de vitórioas jogador 2 (O): 0</p>
  <script>
    let jk=0;
    jk=parseInt(jk);
    let letra = "X";
    function xx(cliqueAq){
      let clique = document.getElementById(cliqueAq).innerHTML;
      imagem=document.getElementById("imagem");
      if (clique == "X" || clique == "O"){
       alert(".........ESSE NÃO PODE.........");
       jk--;
        }else{
          document.getElementById(cliqueAq).innerHTML = letra;
        if (letra == "X"){
            letra = "O";
            imagem.src="o.png"
        }else{
            letra = "X";
            imagem.src="x.png"
        }
        }
      }
      let c =0;
      let d=0;
    function certeza(){
      jk++;
      let c11 = document.getElementById('cel11').innerHTML;
      let c12 = document.getElementById('cel12').innerHTML;
      let c13 = document.getElementById('cel13').innerHTML;
      let c21 = document.getElementById('cel21').innerHTML;
      let c22 = document.getElementById('cel22').innerHTML;
      let c23 = document.getElementById('cel23').innerHTML;
      let c31 = document.getElementById('cel31').innerHTML;
      let c32 = document.getElementById('cel32').innerHTML;
      let c33 = document.getElementById('cel33').innerHTML;
      if (((c11 == 'O') && (c12 == 'O') && (c13 == 'O') && (c11 == c12) && (c12 == c13)) || ((c11 == 'O') && (c22 == 'O') && (c33 == 'O') && (c11 == c22) && (c22 == c33)) || ((c11 == 'O') && (c21 == 'O') && (c31 == 'O') && (c11 == c21) && (c21 == c31)) || ((c21 == 'O') && (c22 == 'O') && (c23 == 'O') && (c21 == c22) && (c22 == c23)) || ((c31 == 'O') && (c32 == 'O') && (c33 == 'O') && (c31 == c32) && (c32 == c33)) || ((c12 == 'O') && (c22 == 'O') && (c32 == 'O') && (c12 == c22) && (c22 == c32)) || ((c13 == 'O') && (c23 == 'O') && (c33 == 'O') && (c13 == c23) && (c23 == c33)) || ((c31 == 'O') && (c22 == 'O') && (c13 == 'O') && (c31 == c22) && (c22 == c13))){
          alert('Jogador 2 ganhou! Parabéns campeão!');
          let jogadas = document.getElementById("jogadas");
          c=parseInt(c);
          c++;
          jogadas.innerHTML="Numero de vitórioas jogador 2: "+ c;
          novoGame();
          jk=0;
        }else{
      if (((c11 == 'X') && (c12 == 'X') && (c13 == 'X') && (c11 == c12) && (c12 == c13)) || ((c11 == 'X') && (c22 == 'X') && (c33 == 'X') && (c11 == c22) && (c22 == c33)) || ((c11 == 'X') && (c21 == 'X') && (c31 == 'X') && (c11 == c21) && (c21 == c31)) || ((c21 == 'X') && (c22 == 'X') && (c23 == 'X') && (c21 == c22) && (c22 == c23)) || ((c31 == 'X') && (c32 == 'X') && (c33 == 'X') && (c31 == c32) && (c32 == c33)) || ((c12 == 'X') && (c22 == 'X') && (c32 == 'X') && (c12 == c22) && (c22 == c32)) || ((c13 == 'X') && (c23 == 'X') && (c33 == 'X') && (c13 == c23) && (c23 == c33)) || ((c31 == 'X') && (c22 == 'X') && (c13 == 'X') && (c31 == c22) && (c22 == c13))){
          alert('Jogador 1 ganhou! Parabéns campeão!');
          let bc = document.getElementById("bc");
          d=parseInt(d);
          d++;
          bc.innerHTML="Numero de vitórioas jogador 1: "+ d;
          novoGame();
          jk=0;
        }
      }
      if(jk==9){
        alert("EMPATE!!!");
        jk=0;
        novoGame();
      }
  }
    function novoGame(){
      for (let i=1; i<=3; i++){
        for (let c=1; c<=3; c++){
            let nomecelula = 'cel' + i + c;
            document.getElementById(nomecelula).innerHTML = '';
        }
      }
      jk=0;
    }
  </script>
</body>
</html>

`````
