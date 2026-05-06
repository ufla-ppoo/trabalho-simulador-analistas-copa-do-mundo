# Simulador Analistas Esportivos - Copa do Mundo

Este projeto foi preparado para apoiar o trabalho prático da disciplina sem complicar o começo.

A ideia principal é simples:

1. Seguindo as histórias de usuário das instruções do trabalho, você vai desenvolver quase tudo testando pela interface de terminal.
2. Só na etapa final vai mexer na interface web.
3. Não é necessário dominar Maven ou Vaadin Flow para fazer o trabalho.

## Como executar (jeito mais simples)

### Opção recomendada no VS Code

- Pressione `F5`.
- A configuracao do projeto inicia tanto o terminal quando a parte web de apoio.
- A interface web é acessível em: `http://localhost:8080`

### Caso queira rodar só a interface web

```bash
mvn jetty:run
```

## Estrutura de pastas em src

```text
src/
  MainApp.java
  br/ufla/copa/
    core/
      contracts/
      model/
      service/
    ui/
      terminal/
      web/
```

### O que tem em cada parte

- `src/MainApp.java`
  - Ponto de entrada da aplicacao.
  - Inicia o fluxo principal no terminal.

- `src/br/ufla/copa/core/contracts`
  - Interfaces de regras (contratos).
  - Define "o que" precisa ser implementado, sem prender ao "como".
  - Essas interfaces **não podem ser alteradas**.

- `src/br/ufla/copa/core/model`
  - Entidades do dominio (ex.: `Estadio`).
  - Representam os dados do sistema.
  - A classe `Estadio` foi colocada apenas como exemplo, podendo ser alterada ou removida conforme necessário.

- `src/br/ufla/copa/core/service`
  - Coordenação da regra de negócio (ex.: simulador).
  - Aqui ficam os métodos que orquestram os casos de uso.
  - A classe disponibilizada é só um exemplo, podendo ser alterada conforme necessário.

- `src/br/ufla/copa/ui/terminal`
  - Interface textual para executar e validar o sistema no dia a dia.
  - Este será seu principal ambiente de teste durante o desenvolvimento.
  - Altere a classe disponibilizada para que o menu funcione conforme desejado.

- `src/br/ufla/copa/ui/web`
  - Interface web com Vaadin Flow.
  - Recomendado focar nela apenas depois que a parte de negocio estiver consistente.
  - Altere a classe para representar a tela principal, integrando as funcionalidades já testadas no terminal.

## Dicas

- Faça commits pequenos e frequentes.
- Teste cada mudanca no terminal antes de avançar.
- Na web, prefira integrar funcionalidade já validada, em vez de criar lógica nova direto na tela.

## O que é Maven (resumo rápido)

Maven é uma ferramenta que organiza o projeto Java e automatiza tarefas comuns, como:

1. Baixar bibliotecas usadas pelo projeto.
2. Compilar o código.
3. Executar plugins e montar a aplicação.

Em outras palavras: ele evita configurações manuais repetitivas.

Voce não precisa aprender Maven para fazer o trabalho.

## O que é Vaadin Flow (resumo rápido)

Vaadin Flow permite criar interface web usando Java (sem precisar escrever front-end completo em JavaScript).

No projeto:

1. A tela web principal está em `ui/web/MainView.java`.
2. Componentes como `Grid`, `Button` e `TextField` são montados no codigo Java.
