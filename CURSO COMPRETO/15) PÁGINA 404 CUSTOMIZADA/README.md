# PÁGINA 404 CUSTOMIZADA
Para criar uma página 404 customizada em um projeto Next.js, você pode criar um arquivo chamado `404.js` dentro do diretório `pages`. O Next.js automaticamente reconhecerá este arquivo como a página a ser exibida quando ocorrer um erro 404 (página não encontrada).

Aqui está como você pode criar uma página 404 customizada:

1. **Crie o Arquivo `404.js`:**

Dentro do diretório `pages`, crie um arquivo chamado `404.js`. Este arquivo conterá o conteúdo da sua página 404 customizada.

```jsx
// pages/404.js

const Custom404 = () => {
  return (
    <div>
      <h1>404 - Página não encontrada</h1>
      <p>A página que você está procurando não foi encontrada.</p>
    </div>
  );
};

export default Custom404;
```

2. **Estilize a Página (Opcional):**

Você pode estilizar a página 404 customizada adicionando CSS ao arquivo `404.js` ou criando um arquivo de estilo separado e importando-o para a página. Isso permite que você personalize a aparência da página de acordo com o design do seu site.

3. **Teste a Página 404:**

Após criar a página 404 customizada, você pode testá-la acessando uma rota que não existe em seu aplicativo Next.js. Por exemplo, se você acessar `http://localhost:3000/rota-inexistente`, o Next.js deverá exibir sua página 404 customizada em vez da página padrão de erro.

Com essas etapas simples, você pode criar e personalizar uma página 404 em seu projeto Next.js. Isso é útil para fornecer uma experiência amigável para os usuários que acessam URLs inválidas em seu aplicativo. 