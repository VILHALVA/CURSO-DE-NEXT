# ROTAS DINÂMICAS COM DADOS
Para criar rotas dinâmicas com dados em um projeto Next.js, você pode combinar rotas dinâmicas com a obtenção de dados usando `getServerSideProps` ou `getStaticProps`. Isso permite que você renderize páginas dinâmicas com base nos parâmetros da URL e obtenha os dados necessários durante a fase de construção ou no lado do servidor.

Aqui está como você pode fazer isso:

## 1. Criar Páginas Dinâmicas:
Crie páginas dinâmicas dentro do diretório `pages` do seu projeto. Por exemplo, se você estiver construindo um blog e quiser páginas para exibir detalhes de postagens com base em seus IDs, crie um arquivo `[id].js` ou `[id].tsx`.

```jsx
// pages/posts/[id].js

const Post = ({ post }) => {
  // Renderize os detalhes da postagem
  return (
    <div>
      <h1>{post.title}</h1>
      <p>{post.body}</p>
    </div>
  );
};

export default Post;
```

## 2. Implementar `getServerSideProps` ou `getStaticProps`:
Implemente a função `getServerSideProps` ou `getStaticProps` para buscar os dados da postagem com base no ID fornecido na URL dinâmica.

```jsx
// pages/posts/[id].js

export async function getServerSideProps({ params }) {
  // Faz a requisição à API para buscar os dados da postagem com base no ID
  const res = await fetch(`https://api.example.com/posts/${params.id}`);
  const post = await res.json();

  // Retorna os dados da postagem como props
  return {
    props: {
      post,
    },
  };
}

const Post = ({ post }) => {
  // Renderize os detalhes da postagem
  return (
    <div>
      <h1>{post.title}</h1>
      <p>{post.body}</p>
    </div>
  );
};

export default Post;
```

## 3. Usando Links para Navegação:
Use o componente `Link` do Next.js para criar links para as páginas dinâmicas. Certifique-se de passar o ID da postagem como parâmetro na URL.

```jsx
// Em qualquer outro componente ou página
import Link from 'next/link';

const MeuComponente = () => (
  <div>
    {/* Link para a página da postagem com ID 1 */}
    <Link href="/posts/1">
      <a>Postagem 1</a>
    </Link>
    <br />
    {/* Link para a página da postagem com ID 2 */}
    <Link href="/posts/2">
      <a>Postagem 2</a>
    </Link>
  </div>
);

export default MeuComponente;
```

Com essas etapas, você pode criar rotas dinâmicas com dados em um projeto Next.js, permitindo que você exiba conteúdo dinâmico com base nos parâmetros da URL.