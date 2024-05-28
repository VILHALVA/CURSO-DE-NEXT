# NESTED ROUTES EM NEXT 
Em Next.js, rotas aninhadas (nested routes) referem-se à capacidade de criar uma estrutura de roteamento hierárquica, onde uma rota pode ter sub-rotas associadas a ela. Isso é útil para organizar e modularizar a aplicação, especialmente em projetos maiores ou complexos.

Vou te guiar através do processo para criar rotas aninhadas em um projeto Next.js:

Passo 1: Estrutura de Pastas
Para começar, organize a estrutura de pastas do seu projeto de acordo com as rotas aninhadas que deseja criar. Por exemplo, se você tiver uma rota principal como `/products`, e deseja ter sub-rotas para cada produto individual, você pode organizar a estrutura da seguinte forma:

```
pages/
└── products/
    └── [productId].js
```

Neste exemplo, `pages/products` é a rota principal e `[productId].js` é uma rota dinâmica que representa os detalhes de um produto específico.

Passo 2: Criar Componentes
Dentro do diretório `pages/products`, crie o arquivo `[productId].js` e defina o componente que corresponde a esta rota. Por exemplo:

```jsx
export default function ProductDetail({ productId }) {
  return (
    <div>
      <h1>Product Detail</h1>
      <p>Product ID: {productId}</p>
    </div>
  );
}

export async function getServerSideProps({ params }) {
  // Aqui você pode buscar dados do produto com base no productId
  const productId = params.productId;
  // Simulação de dados
  // const product = await fetchProduct(productId);

  return {
    props: {
      productId,
    },
  };
}
```

Este componente `ProductDetail` representa a página de detalhes de um produto específico. O `productId` é passado como parâmetro para a página dinâmica.

Passo 3: Configurar Roteamento
No arquivo `[productId].js`, você já definiu a lógica para a rota dinâmica. O Next.js cuidará do roteamento para esta página automaticamente, com base na estrutura de pastas e no nome do arquivo.

Passo 4: Navegação entre Rotas Aninhadas
Para navegar entre as rotas aninhadas, você pode usar o componente `Link` fornecido pelo Next.js. Por exemplo, em qualquer página, você pode adicionar um link para a página de detalhes de um produto específico da seguinte forma:

```jsx
import Link from 'next/link';

export default function ProductList() {
  return (
    <div>
      <h1>Product List</h1>
      <ul>
        <li>
          <Link href="/products/1">
            <a>Product 1</a>
          </Link>
        </li>
        <li>
          <Link href="/products/2">
            <a>Product 2</a>
          </Link>
        </li>
        {/* Adicione mais links para outros produtos aqui */}
      </ul>
    </div>
  );
}
```

Este link irá navegar para a página de detalhes do produto específico quando clicado, com base no `productId` passado na URL.

