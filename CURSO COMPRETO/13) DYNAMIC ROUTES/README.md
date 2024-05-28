# DYNAMIC ROUTES
Em um projeto Next.js, rotas dinâmicas permitem que você crie páginas que se adaptam a diferentes parâmetros na URL. Isso é útil para construir páginas que exibem conteúdo com base em IDs, nomes de usuário, categorias, ou qualquer outro parâmetro dinâmico na URL.

Aqui está como você pode criar rotas dinâmicas em um projeto Next.js:

## 1. Criar uma Página Dinâmica:
Você pode criar uma página dinâmica criando um arquivo dentro do diretório `pages` com colchetes `[ ]` em seu nome. Por exemplo, se você quiser criar uma página que exibe detalhes de um produto com base em seu ID, você pode criar um arquivo chamado `[id].js` ou `[id].tsx`.

```jsx
// pages/produtos/[id].js

const Produto = ({ produto }) => {
  // Use os dados do produto para renderizar a página
  return (
    <div>
      <h1>{produto.nome}</h1>
      <p>Preço: ${produto.preco}</p>
      <p>Descrição: {produto.descricao}</p>
    </div>
  );
};

export default Produto;
```

## 2. Implementar `getServerSideProps` ou `getStaticProps`:
Dependendo dos requisitos do seu projeto, você pode implementar a função `getServerSideProps` ou `getStaticProps` para buscar os dados do produto com base no ID na URL.

```jsx
// pages/produtos/[id].js

export async function getServerSideProps({ params }) {
  // Faz a requisição à API para buscar os dados do produto com base no ID
  const res = await fetch(`https://api.exemplo.com/produtos/${params.id}`);
  const produto = await res.json();

  // Retorna os dados do produto como props
  return {
    props: {
      produto,
    },
  };
}

const Produto = ({ produto }) => {
  // Use os dados do produto para renderizar a página
  return (
    <div>
      <h1>{produto.nome}</h1>
      <p>Preço: ${produto.preco}</p>
      <p>Descrição: {produto.descricao}</p>
    </div>
  );
};

export default Produto;
```

## 3. Links para Páginas Dinâmicas:
Você pode criar links para suas páginas dinâmicas usando o componente `Link` do Next.js. Certifique-se de passar o ID do produto como parâmetro na URL.

```jsx
// Em qualquer outro componente ou página
import Link from 'next/link';

const MeuComponente = () => (
  <div>
    {/* Link para a página do produto com ID 1 */}
    <Link href="/produtos/1">
      <a>Produto 1</a>
    </Link>
    <br />
    {/* Link para a página do produto com ID 2 */}
    <Link href="/produtos/2">
      <a>Produto 2</a>
    </Link>
  </div>
);

export default MeuComponente;
```

Com estas etapas, você pode criar e utilizar rotas dinâmicas em seu projeto Next.js para exibir conteúdo com base em parâmetros na URL, como IDs de produtos, nomes de usuário, IDs de postagens, etc. 