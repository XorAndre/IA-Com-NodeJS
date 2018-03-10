# IA-Com-NodeJS
Destinado para quem aprender um pouco sobre Inteligência artificial com um exemplo de Chatbot usando Node-JS
O que é Inteligência Artificial?
Similar a inteligência humana, a IA é demonstrada através de mecanimos e softwares. Também muito estudada no meio acadêmico. Vários pesquisadores e registros didáticos definem o campo como: “ Estudos de agentes inteligentes”. Caso não saiba agentes inteligentes são sistemas capazes de identificar o ambiente e tomar atitudes. 

## Tipos de IA
 Existem três tipos de inteligência artificial, mas antes de citar seus nomes gostaria de dizer que robốs não são IA. Robốs são máquinas programadas para fazer tarefas repetidas, mas não tarefas de modo “inteligente” a ponto de indenticar algo sozinho e fazer, mas nada impede que um robô possa ter um comportamento a partir de uma IA.
   
## Artificial Narrow Intelligence
Esse é o mais baixo nível de inteligência artificial. Elas conseguem identificar um determinado ambiente, mas não vão muito além do que o que foi estabelecido conhecer. São exemplos: anti-spans, busca do Google, conversores de aúdio em texto (tradutores). 
## Artificial General Intelligence
 Chamada de inteligência forte. Essa IA tenta se igualar a inteligência humana ao realizar tarefas intelectuais. Criar esse tipo de Inteligência artificial não é uma tarefa fácil como a Narrow. Seu desenvolvimento envolve conhecimento muito além. E chegar a este nível digamos que por “inteiro”, ainda vai demorar um tempinho. 
## Artificial Superintelligence
 Este é o ultimo nível que uma IA pode chegar. Este tipo de inteligência supera as mais brilhantes mentes humanas. Alguns pesquisadores acreditam que criar tal IA seria por em risco a raça humana (não só pesquisadores srsr), e outros acreditam que seria a chava para entender imortalidade. Mas claro que isso está longe de ser criado. 
Uma pequena IA com NodeJS
  Você certamente já ouviu falar dessa maravilha chamada NodeJS, mas se não ouviu falar aí vai uma breve explicação do que é. O Node nada mais é que uma plataforma para desenvolvimento Serve-Side que utiliza como sua base JavaScript. Atualmente estamos na versão 9 da plataforma. O NodeJS é compatível com Linux, Windows e Mac-OS. Para instalar acesse esse link: link aqui.   


### Espera falta algo ainda!
 Antes de começamos a escrever nosso código precisamos entender como funciona uma rede neural.  Nosso cérebro possuí 10 milhões de neurốnios. Todas as funções de nosso organismo são ralacionadas com estas células. Os neurônios se conectam uns ao outros através de sinapses, juntos formam a chamada Rede Neural. Está rede possibilita a nós seres humanos uma enorme capacidade de armazenamento e processamento de dados.
 
  
### Redes Neurais Artificiais
 A primeira Rede Neural Artificial (RNA) foi iniciada 1943 através de artigos dos neuroanatomista e psiquiatra Warren McCulloch, do Instituto Tecnológico de Massachusetts, e do matemático Walter Pitts, os autores fizeram uma analogia entre células nervosas e processos eletrônicos. A RNAs aprendem através da fase de aprendizagem. A RNA possui várias vantagens entre elas facilidade:
Tolerância a falhas; 
bom desempenho em tarefas pouco ou mal definidas;
confiabilidade do conjunto de treinamento;
integridade do conjunto de treinamento

   
## Alguns modelos de neurônios artificiais

![Neuronio artifical](http://www.cerebromente.org.br/n05/tecnologia/image11.gif)

## Criando um Chatbot
Bom depois de uma introdução do que é IA, vamos então a nosso projetinho. Criaremos um Chatbot. Chatbots são muito usados em lojas online, redes sociais como Facebook, jogos e acredite estão virando febre no mercado. Seu funcionamento é bem simples! O usuário manda uma mensagem pelo canal que é atendido por um bot. Uma observação os chatbots estão dentro do nível de Artificial Narrow Intelligence nada mais é que uma IA de nível fraco.    

Para facilitar o trabalho de desenvolvimento de Chatbots, hoje temos várias bibliotecas que ajudam desenvolvedores a fazer seus projetos tais como: Facebook, Bot Builder SDK (que usaremos), Tegram entre outros… 

O Bot Builder é um SDK open source desenvolvido pela Microsoft. Isto mesmo amiguinho a MS que fez! Com ele é possível criar chatbots a partir de NodeJS para multiplataformas e também com C# . Uma das coisas legais é que ele disponibiliza um emulador para que você teste seu projeto localmente ou se preferir remoto.  

### Algumas das razões na qual vale a pena usar o Bot Builder SDK
1. A primeira pelo fato de possuir uma documentação bem feita 
2. Possibilidade de publicarmos em serviços Cloud como a Heroku
3. Se conecta em diversos canais 
4. Flexível com outras APIs de IA que não são da Microsoft

## Nosso projeto 
![Imagem tropa de elite](http://geradormemes.com/media/created/sbaqiy.jpg)
Abra o terminal ou CMD, e crie uma pasta chamada exemplo-bot. Logo depois abra o diretório

```
mkdir primeiro-bot
cd primeiro-bot
```
Feita as etapas digite os seguintes códigos npm init e touch index.js



Instale as seguintes dependências: 
```
npm install –save botbuilder 
npm install –save restify 
```
Abra seu editor de código e adicione a seguinte linha de código no arquivo index.js:
```
console.log(“Olá amigo!”);
```
Execute o arquivo no terminal através do comando: node index.js, que irá retornar a string que escrevemos.
Bom agora que testamos nosso Node vamos por o nosso Bot em sua primeira ação. Apaque a linha que foi escrita no index.js e coloque as seguintes linhas:
```
let reatify = require(‘restify’); 
let builder = require(‘botbuilder’);
```
 Se vocốe é novato no mundo de JavaScript e Node o código acima é nada mais que importação de nossas depedências em nosso arquivo.  
Criando o servidor que irá rodar o bot
  Usaremos o restify para criar um objeto que irá nos permitir rodar nosso bot em um servidor, mas antes vai uma breve explicação sobre o que é o restify. O resify é um framework que ajuda no desenvolvimento de APIs Rest. Caso queira usar o Express também é possível já que o Bot é compatível. 
  
``` 
 let  server = restify.createServer();
server .listen(process.env.port || process.env.PORT || 3978, function (){
	console.log(‘%s listening to %s’, server.name, server.url);
});
```
Criando um ChatConnector:

```
let connector = new builder .ChatConnector({
	appId: process.env.MICROSOFT_APP_ID,
	appPassworld: process.env.MICROSOFT_APP_PASSWORD
});
```
 O Chatonnector é usado na comunicação com o Bot Framework Connector Service, o serviço responsável por gerenciar conexão com múltiplos canais suportados pelo framework.
