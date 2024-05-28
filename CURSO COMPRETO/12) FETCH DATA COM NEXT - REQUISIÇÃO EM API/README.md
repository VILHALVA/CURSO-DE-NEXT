# FETCH DATA COM NEXT - REQUISIÇÃO EM API
Para fazer requisições a uma API em um projeto Next.js, você pode utilizar o método `getServerSideProps` ou `getStaticProps`, dependendo de suas necessidades de renderização estática ou do lado do servidor. Aqui está como você pode fazer isso:

## 1. Utilizando `getServerSideProps`:
O `getServerSideProps` é utilizado quando você precisa gerar a página em tempo de execução (no servidor) a cada requisição. Isso é útil para dados que mudam frequentemente ou que não podem ser pré-renderizados no momento da construção.

```jsx
// pages/seu-componente.js

export async function getServerSideProps() {
  // Faz a requisição à API
  const res = await fetch('https://api.exemplo.com/dados');
  const dados = await res.json();

  // Retorna os dados como props
  return {
    props: {
      dados,
    },
  };
}

// Seu componente
const SeuComponente = ({ dados }) => {
  // Use os dados recebidos
  return (
    <div>
      {/* Renderize os dados aqui */}
    </div>
  );
};

export default SeuComponente;
```

## 2. Utilizando `getStaticProps`:
O `getStaticProps` é utilizado quando você pode pré-renderizar as páginas no momento da construção e elas não mudam com frequência. Isso é útil para melhorar o desempenho e a escalabilidade do seu site.

```jsx
// pages/seu-componente.js

export async function getStaticProps() {
  // Faz a requisição à API
  const res = await fetch('https://api.exemplo.com/dados');
  const dados = await res.json();

  // Retorna os dados como props
  return {
    props: {
      dados,
    },
  };
}

// Seu componente
const SeuComponente = ({ dados }) => {
  // Use os dados recebidos
  return (
    <div>
      {/* Renderize os dados aqui */}
    </div>
  );
};

export default SeuComponente;
```

## Tratamento de Erros:
Não se esqueça de tratar possíveis erros nas requisições à API, especialmente ao lidar com `fetch`. Você pode usar `try/catch` para isso:

```jsx
export async function getServerSideProps() {
  try {
    // Faz a requisição à API
    const res = await fetch('https://api.exemplo.com/dados');
    const dados = await res.json();

    // Retorna os dados como props
    return {
      props: {
        dados,
      },
    };
  } catch (error) {
    console.error('Erro ao obter dados:', error);
    return {
      props: {
        dados: null, // ou algum valor padrão
      },
    };
  }
}
```

## Revalidação de Dados Estáticos:
Se você estiver usando `getStaticProps` e precisar atualizar os dados periodicamente, você pode adicionar a opção `revalidate` para especificar em quantos segundos a página deve ser revalidada.

```jsx
export async function getStaticProps() {
  // Faz a requisição à API
  const res = await fetch('https://api.exemplo.com/dados');
  const dados = await res.json();

  // Retorna os dados como props
  return {
    props: {
      dados,
    },
    revalidate: 60, // Revalida a cada 60 segundos
  };
}
```

Com essas abordagens, você pode facilmente fazer requisições a APIs em um projeto Next.js e renderizar os dados em suas páginas. Certifique-se de escolher a abordagem correta com base nos requisitos de seu projeto. 