# NAVEGAÇÃO ENTRE PÁGINAS - COMPONENTE LINK
Em Next.js, o componente `Link` é usado para criar links entre páginas da aplicação. Ele fornece uma maneira fácil e eficiente de navegar entre diferentes rotas, mantendo a experiência do usuário rápida e suave, pois utiliza o pré-carregamento de páginas.

Aqui está como você pode usar o componente `Link` para criar navegação entre páginas em um projeto Next.js:

Passo 1: Importar o Componente `Link`
Certifique-se de importar o componente `Link` no arquivo onde deseja criar o link de navegação:

```jsx
import Link from 'next/link';
```

Passo 2: Usar o Componente `Link`
Você pode usar o componente `Link` para envolver qualquer elemento que deva funcionar como um link de navegação. Por exemplo, você pode usar um elemento `<a>` ou qualquer outro elemento que faça sentido para o seu design:

```jsx
<Link href="/pagina-alvo">
  <a>Navegar para a Página Alvo</a>
</Link>
```

O `href` é o caminho relativo para a página de destino. Você pode usar uma string simples, como `"/pagina-alvo"`, ou uma rota dinâmica com parâmetros, como `"/posts/[slug]"`.

Passo 3: Estilizar o Link (Opcional)
O componente `Link` renderiza um elemento `<a>` HTML, mas você pode estilizá-lo como quiser. Por exemplo, você pode adicionar classes CSS ou estilos inline conforme necessário para corresponder ao seu design:

```jsx
<Link href="/pagina-alvo">
  <a className="link-estilizado">Navegar para a Página Alvo</a>
</Link>
```

Passo 4: Tratamento de Eventos (Opcional)
Você pode adicionar manipuladores de eventos ao componente `Link` para adicionar funcionalidades adicionais, como rastreamento de cliques ou pré-processamento antes de navegar para a próxima página. Por exemplo:

```jsx
<Link href="/pagina-alvo" onClick={handleClick}>
  <a>Navegar para a Página Alvo</a>
</Link>
```

Aqui, `handleClick` é uma função que será executada quando o link for clicado. Você pode definir essa função conforme necessário para executar qualquer lógica personalizada.

Com esses passos, você pode usar o componente `Link` para criar navegação entre páginas em um projeto Next.js. Ele cuida automaticamente do pré-carregamento das páginas, garantindo uma transição suave e rápida entre os diferentes roteamentos.