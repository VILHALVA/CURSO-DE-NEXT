# ADICIONANDO CSS NO NEXT.JS 
Para adicionar estilos CSS em um projeto Next.js, você tem algumas opções, incluindo o uso de arquivos CSS globais, módulos CSS, CSS-in-JS e frameworks de estilos como Tailwind CSS. Vou te mostrar como você pode adicionar estilos usando algumas dessas abordagens:

## Arquivos CSS Globais:
1. **Criar um Arquivo CSS Global:** Você pode criar um arquivo CSS global para aplicar estilos em toda a sua aplicação. Por exemplo, você pode criar um arquivo `global.css` na raiz do seu projeto.

2. **Importar o Arquivo CSS Global:** Para importar o arquivo CSS global, você pode fazer isso no arquivo `_app.js` ou `_app.tsx`. Este arquivo é especial no Next.js e é usado para envolver seus componentes com funcionalidades adicionais, como layouts e estilos globais.

Exemplo de como importar o arquivo CSS global no `_app.js`:

```jsx
// pages/_app.js

import '../styles/global.css';

function MyApp({ Component, pageProps }) {
  return <Component {...pageProps} />;
}

export default MyApp;
```

## Módulos CSS:
1. **Criar um Arquivo CSS Módulo:** Você também pode criar arquivos CSS módulos para estilizar componentes específicos. Estes são arquivos CSS que são importados como módulos JavaScript, e os nomes de classe são gerados automaticamente para evitar conflitos.

2. **Importar o Arquivo CSS Módulo:** Você pode importar o arquivo CSS módulo diretamente no componente que deseja estilizar.

Exemplo de como usar um arquivo CSS módulo:

```jsx
// components/MeuComponente.js

import styles from './MeuComponente.module.css';

const MeuComponente = () => (
  <div className={styles.container}>
    <h1>Meu Componente</h1>
    <p>Este é um componente estilizado usando CSS módulo!</p>
  </div>
);

export default MeuComponente;
```

## Tailwind CSS:
1. **Instalar o Tailwind CSS:** Você pode instalar o Tailwind CSS no seu projeto Next.js usando npm ou yarn:

```bash
npm install tailwindcss postcss autoprefixer
```

2. **Configurar o Tailwind CSS:** Siga as instruções de configuração do Tailwind CSS conforme descrito na [documentação oficial](https://tailwindcss.com/docs/guides/nextjs).

3. **Utilizar o Tailwind CSS:** Agora você pode usar as classes do Tailwind CSS diretamente em seus componentes para estilizá-los.

Exemplo de como usar o Tailwind CSS em um componente:

```jsx
// components/MeuComponente.js

const MeuComponente = () => (
  <div className="bg-blue-500 text-white p-4">
    <h1>Meu Componente</h1>
    <p>Este é um componente estilizado usando Tailwind CSS!</p>
  </div>
);

export default MeuComponente;
```

Com essas opções, você pode adicionar estilos CSS de várias maneiras em seu projeto Next.js, dependendo das necessidades e preferências do seu projeto. 