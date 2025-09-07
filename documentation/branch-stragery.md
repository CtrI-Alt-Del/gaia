# Estratégia de Branches

Para este projeto, adotaremos o modelo GitHub Flow com Releases para Produção.
Esta estratégia foi escolhida por combinar a agilidade e a simplicidade de uma
única branch principal com a segurança de um processo de lançamento controlado
para o ambiente de produção. O modelo se alinha perfeitamente aos requisitos de
Integração Contínua (IC) e Deploy Automático (CD) do projeto.

A filosofia é simples: a branch main representa o código mais atual e integrado,
que é continuamente entregue a um ambiente de testes (staging), enquanto o
ambiente de produção é atualizado apenas por meio de lançamentos de versões
(releases) explícitas e controladas.

### Fluxo de Trabalho

1. **Branch principal**

   - Utilizamos apenas uma branch de longa duração: `main`.
   - Ela representa sempre o estado mais estável do código.

2. **Branches de desenvolvimento**

   - Novas funcionalidades ou correções devem ser desenvolvidas em branches
     curtas, criadas a partir da `main`.
   - Nomenclatura:

     - `feat/nome-da-feature`
     - `fix/nome-do-bug`

3. **Pull Requests (PRs)**

   - Antes de integrar qualquer mudança à `main`, deve ser aberto um **PR**.
   - Os PRs ao serem abertos passam por revisão de código e execução automática
     de testes e build para garantir a integração do trabalho do desenvolvedor o
     quanto antes.
    - O título do PR deve conter o ID da tarefa correspondente (ex: [#123] Ajuste no login).

4. **Integração em Staging**

   - Ao realizar **merge na `main`**, o pipeline de **CI/CD** é acionado
     automaticamente.
   - O deploy é feito no ambiente de **staging**, permitindo validar o
     comportamento da aplicação em condições próximas às de produção.

5. **Publicação em Produção**

   - Quando o sistema estiver pronto para ser liberado, criamos uma
     **release/tag no GitHub**.
   - Isso aciona o pipeline de **CI/CD para produção**, garantindo que apenas
     versões aprovadas cheguem ao ambiente final.

6. **Hotfixes**

   - Correções urgentes podem ser feitas diretamente em uma branch criada a
     partir da `main`.
   - Após aprovação e merge, deve-se gerar uma release para liberar a correção
     em produção.
