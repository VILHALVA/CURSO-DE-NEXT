# HELLO WORLD NO NEXT.JS
Vou te guiar através do processo para criar um simples "Hello World" utilizando o Next.js.

Passo 1: Instalação do Next.js
Para começar, você precisa ter o Node.js instalado em seu sistema. Se ainda não o tiver, você pode baixá-lo e instalá-lo a partir do [site oficial do Node.js](https://nodejs.org/).

Depois de ter o Node.js instalado, abra seu terminal e execute o seguinte comando para criar um novo projeto Next.js:

```bash
npx create-next-app hello-world-nextjs
```

Este comando criará uma nova pasta chamada `hello-world-nextjs` e instalará todas as dependências necessárias para um projeto Next.js básico.

Passo 2: Criando uma Página "Hello World"
Após a instalação, navegue até a pasta do seu novo projeto:

```bash
cd hello-world-nextjs
```

Agora, podemos criar uma página "Hello World". Para isso, crie um arquivo chamado `index.js` dentro do diretório `pages`:

```bash
touch pages/index.js
```

Abra o arquivo `index.js` com seu editor de código preferido e adicione o seguinte conteúdo:

```jsx
export default function Home() {
  return <h1>Hello World</h1>;
}
```

Este é um componente React simples que retorna um título "Hello World".

Passo 3: Executando o Projeto
Agora que criamos nossa página "Hello World", podemos iniciar o servidor de desenvolvimento do Next.js. No terminal, execute o seguinte comando:

```bash
npm run dev
```

Isso iniciará o servidor de desenvolvimento e você poderá acessar sua aplicação em `http://localhost:3000` no seu navegador.

Parabéns! Você criou seu primeiro "Hello World" com Next.js. 