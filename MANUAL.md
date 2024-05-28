# MANUAL
## TUTORIAL:
Vou criar um pequeno projeto em Next que consistirá em um contador simples, onde o usuário pode incrementar e decrementar o valor do contador. Vou explicar cada parte do código conforme avançamos:

1. **Criando o Projeto:**
  No caso de criar um projeto Next, a diferença está principalmente no uso de TypeScript ou JavaScript como linguagem de programação. Aqui estão os comandos para criar um novo projeto Next.js, tanto em JavaScript quanto em TypeScript:

  1. **Criar um projeto em JavaScript**:

  Para criar um projeto em JavaScript, você pode usar o seguinte comando:

  ```bash
  npx create-next-app nome-do-projeto
  ```

  Este comando criará um novo projeto Next em JavaScript com o nome especificado. Ele usará JavaScript como linguagem de programação padrão.

  2. **Criar um projeto em TypeScript**:

  Para criar um projeto em TypeScript, você pode usar o seguinte comando:

  ```bash
  npx create-next-app nome-do-projeto --typescript
  ```

  Este comando criará um novo projeto Next em TypeScript com o nome especificado. A opção `--typescript` instrui o Create Next App a configurar o projeto para usar TypeScript como linguagem de programação. Isso significa que todos os arquivos de código-fonte serão escritos em TypeScript e o projeto será configurado para compilar o código TypeScript em JavaScript durante o processo de construção.

2. **Implementando o Componente de Contador:**

Vamos agora implementar o componente de contador. Crie um arquivo `pages/index.js` (ou `pages/index.tsx` se estiver usando TypeScript) e adicione o seguinte conteúdo:

```jsx
import { useState } from 'react';
import styles from '../styles/Home.module.css';

export default function Home() {
  const [count, setCount] = useState(0);

  const increment = () => {
    setCount(count + 1);
  };

  const decrement = () => {
    setCount(count - 1);
  };

  return (
    <div className={styles.container}>
      <h1>Contador</h1>
      <div className={styles.counter}>
        <button onClick={decrement}>-</button>
        <span>{count}</span>
        <button onClick={increment}>+</button>
      </div>
    </div>
  );
}
```

- **Explicação:** Neste código, criamos uma página `Home` que renderiza um contador. Utilizamos o hook `useState` para definir o estado do contador e uma função `setCount` para atualizar esse estado. Implementamos duas funções, `increment` e `decrement`, que são chamadas quando os botões "+" e "-" são clicados, respectivamente. O valor atual do contador é exibido entre os botões.

3. **Estilizando o Componente:**

Vamos adicionar um pouco de estilo ao nosso contador. Crie um arquivo `styles/Home.module.css` e adicione o seguinte código:

```css
.container {
  text-align: center;
}

.counter {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 20px;
}

.counter button {
  font-size: 24px;
  padding: 10px 20px;
  margin: 0 10px;
  cursor: pointer;
}

.counter span {
  font-size: 36px;
}
```

Este código adiciona um estilo simples para alinhar o contador ao centro da página e definir o estilo dos botões e do número do contador.

4. **Executando o Projeto:**

Agora que o projeto está pronto, você pode executá-lo. Abra um terminal, navegue até o diretório do projeto (`nome-do-projeto`) e execute o seguinte comando:

```bash
npm run dev
```

Isso iniciará o servidor de desenvolvimento e abrirá automaticamente o seu navegador padrão com o aplicativo Next.js em execução. Você verá o contador e poderá clicar nos botões "+" e "-" para incrementar e decrementar o valor do contador, respectivamente.

Este é um projeto Next simples que demonstra como criar e atualizar o estado de um componente funcional utilizando o hook `useState`. Você pode expandir esse projeto adicionando mais funcionalidades, como reiniciar o contador, definir um valor inicial personalizado, ou estilizar ainda mais o componente.

## DIRETÓRIOS:
Ao criar um aplicativo Next usando Create Next App, você geralmente encontrará uma estrutura de diretórios padrão que se parece com isso:

```
meu-app-next/
  |- node_modules/
  |- public/
  |- styles/
      |- Home.module.css
  |- pages/
      |- api/
      |- index.js
  |- package.json
  |- README.md
```

Vamos explicar o propósito de cada diretório:

1. **`node_modules/`**: Este diretório contém todas as dependências do seu projeto, incluindo bibliotecas de terceiros que você instalou usando npm (Node Package Manager) ou Yarn. Você não deve modificar manualmente nada neste diretório, pois é gerado automaticamente pelo gerenciador de pacotes.

2. **`public/`**: Este diretório contém os arquivos estáticos do seu aplicativo, como HTML, imagens, ícones, etc. O arquivo `index.html` neste diretório é o ponto de entrada do seu aplicativo React e geralmente contém uma div com um id específico onde o React renderizará o conteúdo do seu aplicativo.

3. **`styles/`**: Este diretório contém arquivos CSS ou Sass usados para estilizar os componentes do seu projeto.

4. **`pages/`**: Este diretório é onde você cria as páginas do seu aplicativo Next.js. Cada arquivo dentro deste diretório corresponde a uma rota no seu aplicativo.

    - **`api/`**: Este subdiretório é utilizado para criar rotas API que podem ser chamadas diretamente pelo frontend. Cada arquivo neste diretório define um endpoint da API.
    
    - **`index.js`**: Este arquivo é a página inicial do seu aplicativo Next.js. Você pode criar outras páginas criando novos arquivos dentro do diretório `pages`.

5. **`package.json`**: Este arquivo mantém metadados sobre o projeto e suas dependências, incluindo scripts de inicialização, dependências de desenvolvimento, entre outros. É onde você especifica os pacotes que seu projeto depende e suas versões.

6. **`README.md`**: Este é um arquivo Markdown que geralmente contém informações sobre o seu projeto, como instruções de instalação, uso, contribuição, etc. Markdown é uma linguagem de marcação simples que permite formatar texto de forma fácil e rápida.

