# COMPONENTE DE LAYOUT
Um componente de layout no Next.js é um componente reutilizável que define a estrutura básica da sua página, como cabeçalhos, rodapés, barras laterais, menus de navegação, estilos globais, etc. Ele ajuda a manter a consistência visual e estrutural em toda a sua aplicação.

Vou te mostrar como criar um componente de layout básico no Next.js:

Passo 1: Criar o Componente de Layout
Primeiro, crie um novo arquivo para o seu componente de layout. Você pode colocá-lo em um diretório como `components` na raiz do seu projeto Next.js. Aqui está um exemplo simples:

```jsx
// components/Layout.js

import Head from 'next/head';

const Layout = ({ children }) => (
  <div>
    <Head>
      <title>Meu Site</title>
      <meta name="description" content="Descrição do meu site" />
      <link rel="icon" href="/favicon.ico" />
    </Head>
    <header>
      <h1>Meu Cabeçalho</h1>
    </header>
    <main>{children}</main>
    <footer>
      <p>Meu Rodapé</p>
    </footer>
  </div>
);

export default Layout;
```

Neste exemplo, o componente `Layout` possui uma estrutura básica com um cabeçalho, conteúdo principal e rodapé. Ele também usa o componente `Head` do Next.js para adicionar metadados à página, como título, descrição e ícone.

Passo 2: Usar o Componente de Layout
Agora você pode usar o componente de layout em suas páginas. Por exemplo:

```jsx
// pages/Index.js

import Layout from '../components/Layout';

const IndexPage = () => (
  <Layout>
    <h1>Página Inicial</h1>
    <p>Conteúdo da página inicial...</p>
  </Layout>
);

export default IndexPage;
```

Neste exemplo, o componente `IndexPage` é envolvido pelo componente `Layout`, fornecendo assim a estrutura básica de layout para a página inicial.

Passo 3: Estilização e Personalização
Você pode estilizar o componente de layout e adicionar qualquer conteúdo adicional, como barras laterais, menus de navegação, etc., conforme necessário para atender às necessidades da sua aplicação. Além disso, você pode passar props para o componente de layout para personalizar seu comportamento, como passar um título dinâmico para cada página.

Com esse componente de layout, você pode manter uma estrutura consistente em toda a sua aplicação Next.js, facilitando a manutenção e melhorando a experiência do usuário. 