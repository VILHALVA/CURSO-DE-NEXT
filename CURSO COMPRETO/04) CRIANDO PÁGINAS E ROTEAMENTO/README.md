# CRIANDO PÁGINAS E ROTEAMENTO
Para criar páginas e definir o roteamento em um projeto Next.js, você utiliza o diretório `pages`. Cada arquivo JavaScript ou TypeScript dentro do diretório `pages` se torna uma rota acessível na aplicação. Vou te guiar através do processo para criar páginas e configurar o roteamento:

Passo 1: Criar Páginas
1. Navegue até o diretório do seu projeto Next.js.
2. Dentro do diretório `pages`, crie os arquivos JavaScript ou TypeScript correspondentes às suas páginas. Por exemplo, `index.js`, `about.js`, `contact.js`, etc.
3. No arquivo de cada página, defina o componente React que corresponde àquela página. Por exemplo, em `index.js`, você poderia ter:

```jsx
export default function Home() {
  return (
    <div>
      <h1>Homepage</h1>
      <p>Welcome to the homepage!</p>
    </div>
  );
}
```

Passo 2: Configurar Roteamento
O roteamento em Next.js é feito automaticamente com base na estrutura de arquivos dentro do diretório `pages`. Por exemplo:

- `pages/index.js` corresponde à rota `/`
- `pages/about.js` corresponde à rota `/about`
- `pages/contact.js` corresponde à rota `/contact`
- E assim por diante.

Não é necessário configurar manualmente o roteamento. O Next.js cuidará disso para você com base nos arquivos dentro do diretório `pages`.

Passo 3: Navegação entre Páginas
Para navegar entre as páginas, você pode usar o componente `Link` fornecido pelo Next.js. Por exemplo, em qualquer página, você pode adicionar um link para a página `about` da seguinte forma:

```jsx
import Link from 'next/link';

export default function Home() {
  return (
    <div>
      <h1>Homepage</h1>
      <p>Welcome to the homepage!</p>
      <Link href="/about">
        <a>About</a>
      </Link>
    </div>
  );
}
```

Este link irá navegar para a página `/about` quando clicado.

Passo 4: Executar o Projeto
Por fim, você pode executar o projeto Next.js para ver as páginas em ação. No terminal, dentro do diretório do seu projeto, execute o seguinte comando:

```bash
npm run dev
```

Isso iniciará o servidor de desenvolvimento e você poderá acessar sua aplicação em `http://localhost:3000` no seu navegador. Você verá as páginas que criou e poderá navegar entre elas usando os links.

