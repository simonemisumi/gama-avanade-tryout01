# Avanade Angular Academy by Gama - Simulado #1

Primeiro simulado para testar suas habilidades de HTML, CSS e Javascript do programa Avanade Angular Academy (AAA) By Gama. Neste simulado o objetivo é testar sua habilidade para desenvolver usando Bootstrap 4 e JQuery 3. 

Eu sei, você nunca usou Bootstrap 4 né! Eu também fiquei bem empolgado com isso. Mas fica frio, se você já conhece outras versões não vai ser difícil se adaptar. E, cá entre nós, é sempre legal aprender uns paranauê novo né!?

Agora chega de conversa e vamos codar!

Mas antes, você precisa instalar os seguintes componentes na sua máquina:


## Instalando dependências no MacOS

A maneira mais fácil de instalar as dependências no Mac OS é usando o Homebrew. Para instalar basta executar os comandos abaixo no app Terminal:

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Depois do Homebrew instalado vamos instalar o pacote do Node.JS

```
brew install nodejs
```

Pra finalizar é só instalar as dependências do framework Canvas

```
brew install pkg-config cairo libpng jpeg giflib
```

Agora é fazer um clone do repositório do git e executar o comando abaixo para instalar todas as dependências do projeto.

```
npm install
```

Pronto! Agora é só começar a codar!


## Instalando dependências no Windows

Instale o pacote do Node.js pelo link a seguir e siga a instalação normalmente: [https://nodejs.org/en/download/](https://nodejs.org/en/download/)

As ferramentas de desenvolvimento do windows. Para isto você precisa abrir o terminal do node como Administrador, clicando com o botão direito em "Iniciar \> Node.js \> Node.js command prompt" e escolhendo a opção "Executar como Administrador". Quando o terminal abrir execute o comando abaixo:

```
npm install --global --production windows-build-tools
```

Usando o command prompt como usuário normal faça o clone do projeto no github e execute o comando abaixo para instalar as dependências do projeto:

```
npm install
```

Depois disso tem que executar mais um pequeno passo para instalar o executável do chromedriver no windows

```
node node_modules/chromedriver/install.js
```

Pronto! Agora é só começar a codar!


## Instalando dependências no Linux

Siga as instruções para instalar o Node.js através do gerenciador de pacotes da sua distribuição: https://nodejs.org/en/download/package-manager/

Instale as dependências externas:

```
$ sudo apt-get update 
$ sudo apt-get install libcairo2-dev libjpeg-dev libpango1.0-dev libgif-dev build-essential g++
```

Agora instale as dependências do npm:

`$ npm install`

Pronto! Agora é só começar a codar!


Dependências instaladas, faça o clone deste projeto do github e vamos entender a estrutura inicial. Você vai encontrar alguns arquivos já criados e trabalhar a partir daí. A ideia aqui é exercitar um pouco de TDD ([Test Driven Development](https://pt.wikipedia.org/wiki/Test_Driven_Development)). A primeira coisa que você precisa fazer é rodar na sua linha de comando o seguinte:

```
npm test
```

Para saber mais sobre testes de aceitação, leia sobre o framework Mocha. O primeiro teste irá passar e os demais irão falhar. Para terminar este simulado o seu objetivo é fazer todos os testes passarem.


## Condições dos testes

Você deve cumprir os seguintes requisitos para todos os testes passarem:


### Código HTML&CSS

#### O layout desktop deve ser igual ao gabarito

* Deve haver uma tag main com o id "main"
* O layout da página deve seguir exatamente o layout da imagem abaixo rodando no Chrome com resolução de 800x600 px.
![Layout Desktop](https://raw.githubusercontent.com/gamaacademy/gama-avanade-tryout01/master/test/darwin-assertion-desktop.png)

#### O layout mobile deve ser igual ao gabarito

* Deve haver uma tag main com o id "main"
* O layout da página deve seguir exatamente o layout da imagem abaixo rodando no Chrome com resolução de 376x667 px.
![Layout Mobile](https://raw.githubusercontent.com/gamaacademy/gama-avanade-tryout01/master/test/darwin-assertion-mobile.png)


### Formulário de inscrição

#### Deve inscrever no processo sem erros

* O botão que abre o formulário de inscrição deve ter o id "btn-apply-form"
* O modal com o formulário de inscrição deve ter o id "apply-modal"
* O campo do nome deve ter o id "name"
* O campo de email deve ter o id "email"
* O botão de inscrição deve ter o id "btn-apply"
* Deve mostrar um alert de sucesso com o id "apply-success"

#### Não deve se inscrever no processo com nome ou email em branco

* O botão que abre o formulário de inscrição deve ter o id "btn-apply-form"
* O modal com o formulário de inscrição deve ter o id "apply-modal"
* Os campos nome e email serão deixados em branco
* O botão de inscrição deve ter o id "btn-apply"
* Deverá aparecer um alert de erro com o id "apply-error"
* Deverá criar um elemento com o id "feedback-name" com o texto "Não pode estar vazio" abaixo do campo name
* Deverá criar um elemento com o id "feedback-email" com o texto "Não pode estar vazio\nNão é válido" abaixo do campo email

## Uso da API

Você tem que usar nossa API para enviar os dados do formulário de inscrição. Pra facilitar sua vida, vamos deixar um código já mastigado pra você não perder tempo com isso ;)

Você tem que colocar seu email de inscrição no campo "header" pra gente acompanhar sua evolução, sem isso a API não vai funcionar.

```javascript
$.ajax({
	method: 'POST',
	url: 'http://avanade.gama.academy/api/process_applications',
	dataType: 'json',
	headers: { EMAIL: null }, // coloque seu email que usou para se inscrever aqui!
	contentType: 'application/json',
	data: JSON.stringify({ process_application: { name: $('#name').val(), email: $('#email').val() } }),
	success: function(json) { 
		// Código de successo!
	},
	error: function(jqXHR, textStatus, errorThrown) {
		// Não esquece de tratar os erros
	}
});
```


Assim que você conseguir fazer todos os testes passarem faça um fork do nosso projeto no github e compartilhe!

Bom trabalho e nos falamos no próximo simulado!

Se tiver dúvidas, sugestões, correções, reclamações ou elogios, usa o sistema de issues do github que a gente se conversa: [https://github.com/gamaacademy/gama-avanade-tryout01/issues](https://github.com/gamaacademy/gama-avanade-tryout01/issues)
