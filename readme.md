<header>

# Usando o GitHub Copilot com C#

O GitHub Copilot é a primeira ferramenta de IA em grande escala projetada para revolucionar a codificação, fornecendo sugestões inteligentes no estilo de autocompletar enquanto você escreve. Neste módulo, vamos explorar como aproveitar o GitHub Copilot para aumentar sua eficiência ao programar em C#.

Como desenvolvedor, maximizar a produtividade e agilizar o processo de codificação são objetivos-chave. O GitHub Copilot serve como seu par programador alimentado por IA, oferecendo sugestões contextuais adaptadas ao seu código. Ao final deste módulo, você aprenderá como configurar o GitHub Copilot no Codespaces e aproveitar suas capacidades para gerar e implementar sugestões de código com facilidade.

Prepare-se para um projeto prático! Você trabalhará na modificação de um repositório C# para criar um endpoint de API usando o GitHub Copilot. Este exercício proporcionará uma experiência valiosa na criação de uma aplicação web C# que serve uma API HTTP e gera dados de previsão meteorológica pseudo-aleatórios.

</header>

- **Para quem isso é:** Desenvolvedores, Engenheiros DevOps, Gerentes de Desenvolvimento de Software, Testadores.
- **O que você aprenderá:** Como usar o GitHub Copilot para criar código e adicionar comentários ao seu trabalho.
- **O que você construirá:** Arquivos C# que terão código gerado pelo Copilot AI para sugestões de código e comentários.
- **Pré-requisitos:** O GitHub Copilot está disponível para uso gratuito, inscreva-se para [GitHub Copilot](https://gh.io/copilot).
- **Duração:** Este curso pode ser concluído em menos de uma hora.

Ao final deste módulo, você adquirirá as habilidades para:

- Criar prompts para gerar sugestões do GitHub Copilot
- Aplicar o GitHub Copilot para melhorar seus projetos.

## Leitura prévia:
- [Introdução à engenharia de prompt com o GitHub Copilot](https://learn.microsoft.com/training/modules/introduction-prompt-engineering-with-github-copilot)

- [O que é a extensão do GitHub Copilot para o Visual Studio?](https://learn.microsoft.com/en-us/visualstudio/ide/visual-studio-github-copilot-extension?view=vs-2022)

## Requisitos

1. Ative seu [serviço GitHub Copilot](https://github.com/github-copilot/signup)

1. Familiarize-se com [este repositório com Codespaces](https://github.com/github/dotnet-codespaces)

## 💪🏽 Exercício

**Clique com o botão direito no botão abaixo do Codespaces para abrir seu Codespace em uma nova guia**

[![Abrir no GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/github/dotnet-codespaces)

O repositório "**GitHub Codespaces ♥️ .NET**" constrói uma API de previsão do tempo usando APIs Mínimas, abre o Swagger para que você possa chamar e testar a API, e exibe os dados em uma aplicação web usando Blazor com .NET.

Vamos revisar os passos para atualizar o Weather BackEnd App, adicionando um novo endpoint que solicita uma localização específica e retorna a previsão do tempo para essa localização.

### 🤔 Passo 0: Familiarize-se com o repositório "GitHub Codespaces ♥️ .NET"

Quando você abrir o repositório no Codespaces, encontrará uma nova janela de navegador com um Codespace totalmente funcional. Tudo neste repositório está contido neste único Codespace. Por exemplo, no painel de exploração, podemos ver o código principal para o projeto BackEnd e FrontEnd.

![novo Codespace com todos os repositórios em execução](./images/005OpenRepoInCodeSpaces.png)

Antes de executar o projeto, vamos usar o GitHub Copilot Chat para perguntar sobre o que o projeto faz e quais são os diferentes componentes.

1. Abra o **GitHub Copilot Chat** na barra de navegação principal.
1. Digite `O que este projeto está fazendo, e quais são os componentes principais?` e pressione **Enviar**

O GitHub Copilot Chat agora analisará o projeto inteiro e nos fornecerá um resumo sobre o que o projeto faz, quais tecnologias utiliza e quais são os componentes-chave.

![Copilot Chat descrevendo o projeto](./images/004AskCopilotAboutProject.png)

A partir daqui, você pode clicar em arquivos para navegar até eles e pode fazer perguntas de acompanhamento, como `Quais APIs estão disponíveis?`.

### 🚀 Passo 1: Execute os projetos

Agora que temos o contexto do que está no projeto, vamos executá-lo e vê-lo em ação.

Para executar o projeto BackEnd, vá até o painel "Run and Debug" e selecione o projeto "BackEnd".

![abrir program.cs no projeto BackEnd](./images/006RunBackEndProject.png)

Comece a depuração do projeto selecionado. O projeto Weather API, nosso projeto BackEnd, agora estará em execução na porta 8080. Podemos copiar a URL publicada do painel *Ports*.

![Copiar URL do app do painel de portas](./images/007ProjectRunningOpenInNewTab.png)

> Nota: Ao executar a aplicação, você verá a mensagem de erro "Esta página não está funcionando". Isso ocorre porque precisamos navegar até o endpoint, que está detalhado abaixo.

A aplicação BackEnd publicou um endpoint chamado `weatherforecast` que gera dados de previsão aleatórios. Para testar a aplicação em execução, você pode adicionar `/weatherforecast` à URL publicada. A URL final deve ser parecida com esta:

```bash
https://<seu url>.app.github.dev/weatherforecast
