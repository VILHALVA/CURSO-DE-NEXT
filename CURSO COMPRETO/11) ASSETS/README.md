# ASSETS
Em um projeto Next.js, os ativos (assets) são arquivos estáticos, como imagens, fontes, ícones, arquivos de estilo CSS, JavaScript externo, entre outros, que são utilizados para a construção da interface do usuário.

Aqui estão algumas maneiras de lidar com assets em um projeto Next.js:

## 1. Diretório `public`:
O diretório `public` é usado para armazenar arquivos estáticos que serão acessíveis publicamente. Esses arquivos são servidos pelo servidor sem passar pelo processo de construção. Você pode colocar imagens, fontes, ícones e outros arquivos estáticos neste diretório.

Por exemplo, se você colocar uma imagem chamada `logo.png` no diretório `public`, você poderá acessá-la em suas páginas da seguinte forma:

```jsx
<img src="/logo.png" alt="Logo" />
```

## 2. Importação Direta:
Você pode importar assets diretamente em seus componentes ou páginas. Por exemplo, se você tiver um arquivo de estilo CSS chamado `styles.css` no diretório `styles`, você pode importá-lo em seu componente da seguinte forma:

```jsx
import '../styles/styles.css';
```

Isso se aplica não apenas a arquivos CSS, mas também a imagens, fontes e outros tipos de assets.

## 3. Usando Módulos CSS:
Para arquivos CSS que estão relacionados a um componente específico, você pode criar um módulo CSS e importá-lo no componente usando a sintaxe de módulos CSS. Isso permite que você escopo estilos específicos para componentes individuais.

Por exemplo, se você tiver um arquivo CSS chamado `styles.module.css`:

```css
/* styles.module.css */
.container {
  max-width: 960px;
  margin: 0 auto;
}
```

Você pode importá-lo em seu componente da seguinte forma:

```jsx
import styles from '../styles/styles.module.css';

const MeuComponente = () => (
  <div className={styles.container}>
    {/* Conteúdo do componente */}
  </div>
);
```

## 4. Frameworks de Estilo:
Você também pode integrar frameworks de estilo como Tailwind CSS, Bootstrap ou Material-UI ao seu projeto Next.js, seguindo as instruções de instalação e configuração específicas de cada framework.

