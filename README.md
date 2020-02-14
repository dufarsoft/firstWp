# Conheçendo o Polymer e suas peculiaridades

## Instalando o Polymer CLI

- Antes de mais nadas temos que ter instalado o nodejs e o gerenciador de packages NPM.

- Agora instalamos o CLI do polymer . via terminal rodar o seguinte comando: " DEMORA UM POUCO A INSTALAÇÃO CLI "

				npm install -g polymer-cli

- Instalar o gerenciador de dependencia Bower.

				npm install -g bower

## Intalaçao do Polymer e Polyfill,  através do gerenciador bower

-  primeiramente , criar um diretorio para o projeto.

				mkdir testano-polymer

- dentro do diretório criado, startar o bower via terminal:

				bower init

- agora vamos instalar o polymer :

				bower install polymer/polymer --save


### Criando o primeiro component

- Dentro do diretório do projeto criaremos nosso componente via terminal (ou de algum editor de texto).

				touch hello-world.html

- Agora jogamos dentro do componente um link que instalará o Polymer lá.

				<link rel="import" href="bower_components/polymer/polymer.html">

### Criando o DOM do nosso elemento, o qual vai encapsular tudo que for implementado por nós, ou seja o SHADOW DOM

- Criar uma tag do polymer, contendo um id com o nome do nosso component.

				<dom-module id="hello-world">

				</dom-module>

- Tudo que for colocado dentro da tag criada a cima, irá fazer parte de nosso element e vai estar encapsulado no SHADOW DOM

- Definir o template do nosso component,então tudo que criarmos dentro da "tag" <template> se tornará reutilizável... ou seja podendo
ser replicado em vários lugares de uma forma muito DINÂMICA. E também tornando a performace no navegador exelente pois HTTP2 " É OUTRO NÍVEL ".

				dom-module id="tagname">
					<template>
							<h1>Hello World</h1>
					</template>
				</dom-module

- Agora registramos o nosso component/element , dentro do dom-module setando uma tag script :

				<script>
						Polymer({          /* Chamando um recurso do Polymer*/
							is: 'hello-world' /* Registrando custom element referenciado com o nome do component*/
						});
				</script>

- Agora Vamos criar um novo arquivo html com a estrutura HTML5 para ultilzar nosso componente. via terminal:

				touch index.html

- Importar no cabeçalho do index.html, um script que vai vir do seguinte caminho:

				<script src="bower_components/webcomponentsjs/webcomponents-lite.js></script>

- Também importar nosso elemento da seguinte forma:

				<link rel="import" href="hello-world">

- Agora ultilzamos nosso component/element , no formato de uma tag que referencia o custom element, no corpo da página. Ex:

					<body>
					<hello-world> </hello-world>  / * ULTILIZAÇÃO DO COMPONENTE NO INDEX.HTML * /
					</body>

- Para testar nosso componente no browser, startamos o servidor do Polymer que foi adquirido quando baixado o Polymer CLI. via terminal :

					polymer serve --open

### DICAS

- A tag <link> usada para importar o styles da página, fonts etc.. Também pode trazer uma pagina html. Ex:

					<link rel="import" href="ijdsujdiosdjodsjoijdsojdo".html>


- Para criar nossos Components/Custom Elements , sempre precisamos usar um dash para separar , Ex:

					my-first-component			
