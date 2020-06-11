![image](./web/src/assets/logo.svg)

Ecoleta é uma aplicação desenvolvida na Next Level Week tendo em vista a Semana do Meio Ambiente, foram desenvolvidas a aplicação web e a aplicação mobile.

- - -

## Índices

1. [ Funcionalidades ](#funcionalidades)
  - [Aplicação Web](#aplicação-web)
  - [Aplicação mobile](#aplicação-mobile)
2. [ Tecnologias utilizadas ](#tecnologias-utilizadas)
3. [ O que eu aprendi ](#o-que-eu-aprendi)
  - [ Back-end ](#back-end)
  - [ Front-end web](#front-end-web)
  - [ Mobile ](#mobile)
4. [ Padrão ](#padrão)
5. [ Como usar ](#como-usar)

- - -

<a name="funcionalidades"></a>

## Funcionalidades

<a name="aplicação-web"></a>

### Aplicação web

  - Cadastrar ponto de coleta;
  - Listar os itens de coleta.

<a name="aplicação-mobile"></a>

### Aplicação mobile

  - Cadastrar ponto de coleta;
  - Listar os itens de coleta.
  - Listar pontos (filtro por estado, cidade, itens);
  - Listar um ponto de coleta específico.

- - -

<a name="tecnologias-utilizadas"></a>

## Tecnologias utilizadas

  - Typescript
  - Node.js
  - SQLite3
  - KNEX
  - ReactJS
  - React Native
  - Express

- - -

<a name="o-que-eu-aprendi"></a>

## O que eu aprendi

<a name="back-end"></a>

### Back-end

**Rotas**: Endereço completo da requisição.
**Recurso**: Qual entidade estamos acessando no sistema.

**GET**: Buscar uma ou mais informações do back-end.
**POST**: Criar uma nova informação no back-end.
**PUT**: Atualizar uma informação existente no back-end.
**DELETE**: Remover uma informação do back-end.

**Request Param**: Parâmetros que vem na própria rota que identificam um recurso.
**Query Param**: Parâmetros que vêm na própria rota para filtros, paginação, geralemente são opcionais.
**Request Body**: Parâmetros para criação/atualização de informações.

Utilização de um **Query Builder** ([KNEX](http://knexjs.org/)) para construir queries independente do banco de dados, ou seja, se algum dia mudar o banco de dados, vai continuar funcionando da mesma forma.

Como configurar conexão com o banco de dados utilizando o KNEX e a importância de se utilizar o **"path"** por causa dos diferentes sistemas operacionais, por exemplo o Windows utiliza a **\\** no caminho das pastas enquanto outros S.Os utilizam a **/**. O path vai padronizar o caminho para acesso de algum arquivo ou alguma pasata dentro da nossa estrutura.

**Banco de dados**: Relacionamentos N-N (muitos para muitos) gera uma tabela PIVOT. Por exemplo, no caso dessa aplicação existe a tabela "points" (Pontos de coleta) e "items" (items para coleta), então a tabela PIVOT relaciona os pontos de coleta e os itens para coleta, geralmente essa tabela recebe o nome derivado das duas tabelas relacionadas (points_items)

**Migrations**: são o controle de versão do banco de dados, histórico do banco de dados.

<a name="front-end-web"></a>

### Front-end web

React serve para construir SPAs (Single Page Applications) que é uma forma da gente não precisar carregar toda a aplicação quando fizermos uma alteração de rota.

**JSX**: Sintaxe de XML dentro do JavaScript.
**TSX**: TypeScript com JSX.

**Componente no React**: Conseguir separar a aplicação em pequenos blocos que podem ser reutilizados.

**Propriedade**: Atributos que são enviados para o componente.

**Estado e Imutabilidade**: Estados são informações mantidas no próprio componente. Imutabilidade é algo que não pode alterar o estado de uma maneira direta. No React ao invés de alterar um valor é necessário criar um outro valor para esse estado com as modificações que precisamos. Isso garante várias melhorias na aplicação.

**UseState**: Usado sempre que precisar armazenar uma informação.
**useEffect**: Usado para carregar os itens assim que o usuário enrar na tela ou quando muda alguma informação.


<a name="mobile"></a>

### Mobile

#### Comparação do React Native para ReactJS

- Os componentes são escritos da mesma forma tanto no React Native quanto no ReactJS, porém no React Native nós não tempos as tags HTML, existem elementos próprios no React Native.

- As estilizações no React Native são feitas por uma propriedade **style** dentro do elemento que recebe um ojeto que utiliza uma classe chamada StyleSheet.create, por exemplo:

```typescript
export default function App() {
  return (
    <View style={styles.container}>
      <Text>Hello World</Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'center',
  },
});
```

- Podemos utilizar os conhecimentos de CSS para desenvolvimento mobile, isso é possível por causa de uma ferramenta criada pelo Facebook chamada [Yoga](https://yogalayout.com/), ele converte essa sintaxe de css para estilização nativa.

- Todos os elementos tem como padrão display flex.

- No React Native não existe herança/cascata de estilos.

- - -

<a name="padrão"></a>

## Padrão

Foi utilizado o seguinte padrão para os métodos nas controllers: 

- index: listagem
- show: exibir um único registro
- create: criar registro
- update: atualizar registro
- delete: excluir registro

- - -

<a name="como-usar"></a>

## Como usar

> Clone o repositório
```shell
$ git clone https://github.com/TakaGui/ecoleta.git
```
> Vá até os repositórios server, web e mobile
```shell
$ cd ecoleta
$ cd server
$ cd web
$ cd mobile
```
> Instale as dependências em cada repositório
```shell
$ npm install
```

Importante: Criar a conexão com o banco de dados.
