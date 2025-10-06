# Gestão da Automação - Projeto Gaia

Este documento especifica as automações utilizadas no desenvolvimento e na gestão do Projeto Gaia. O objetivo é padronizar processos, reduzir o trabalho manual, minimizar erros e garantir que a equipe possa focar na entrega de valor.

As nossas automações estão divididas em duas áreas principais: **Gestão de Processos (Jira)** e **Ciclo de Desenvolvimento (CI/CD)**.

---

## 1. Automação da Gestão de Processos (Jira)

Utilizamos o Jira como nossa ferramenta central para gestão de tarefas. As automações configuradas nele são essenciais para manter nosso fluxo de trabalho organizado, rastreável e eficiente.

### 1.1. Integração com o GitHub

A conexão entre Jira e GitHub é a base da nossa rastreabilidade. Ela vincula o trabalho planejado (tarefas no Jira) ao trabalho executado (código no repositório).

* **Como funciona:** Através de *smart commits* e nomes de branches, as atividades no GitHub (commits, branches e pull requests) são automaticamente exibidas no card correspondente do Jira.
* **Nosso Padrão:**
    * **Branches:** Toda branch de trabalho deve conter o ID da tarefa do Jira. Ex: `GAIA-131-tela-de-login`.
    * **Commits e Pull Requests:** As mensagens devem referenciar o ID da tarefa para criar o vínculo. Ex: `git commit -m "GAIA-131: adiciona validação de formulário"`.
* **Benefício:** Qualquer pessoa pode ver o status de desenvolvimento de uma tarefa (branches, commits, PRs) diretamente no Jira, sem precisar consultar o GitHub, centralizando a informação.

### 1.2. Hierarquia e Vínculo de Itens

Para garantir a organização e o alinhamento estratégico, seguimos uma estrutura hierárquica clara no Jira, reforçada por um processo consistente.

* **Estrutura:** **Épico** > **User Story** > **Task**
* **Nossa Regra de Processo:**
    1.  Todo trabalho funcional que entrega valor ao usuário é uma **User Story** e deve, obrigatoriamente, estar vinculada a um **Épico**. Isso garante que todo desenvolvimento está alinhado a um objetivo maior.
    2.  Tarefas puramente técnicas, necessárias para completar uma User Story (ex: "configurar tabela no banco de dados"), são criadas como **Tasks** e vinculadas à sua respectiva User Story.
* **Benefício:** Essa estrutura nos dá uma visão clara do progresso dos Épicos e garante que nenhuma tarefa seja criada sem um propósito de negócio ou funcional claro.

### 1.3. Automação de Status e Transições

Para manter o quadro do Jira sempre atualizado e refletindo a realidade, automações são configuradas para mover as tarefas entre as colunas com base em eventos do GitHub.

* **Exemplo de Regra 1: De "Tarefa pendente" para "Em Andamento"**
    * **Gatilho:** Quando uma **Branch** é criada no GitHub referenciando uma tarefa.
    * **Ação:** O status da tarefa no Jira é automaticamente alterado de `Tarefa pendente` para `Em Andamento`.

* **Exemplo de Regra 2: De "Em Andamento" para "Concluído"**
    * **Gatilho:** Quando um **Pull Request é aprovado e mergeado** no GitHub.
    * **Ação:** O status da tarefa no Jira é automaticamente alterado de `Em Andamento` para `Concluído`.

* **Benefício:** Os desenvolvedores não precisam se preocupar em atualizar o Jira manualmente, e o PO e outros stakeholders têm uma visão em tempo real e precisa do andamento do projeto.

---

## 2. Automação do Ciclo de Desenvolvimento (CI/CD)

O Projeto Gaia utiliza **GitHub Actions** para automatizar parte do ciclo de desenvolvimento, garantindo que o código enviado para o repositório esteja funcional e atenda aos padrões de qualidade definidos.

### 2.1. Workflow de Integração Contínua (CI)

Atualmente, implementamos um workflow de **Integração Contínua (Continuous Integration)** que é executado automaticamente a cada *push* ou *pull request* realizado na branch principal do repositório.

**Etapas do Workflow:**

1. **Instalação de Dependências**  
   O ambiente é configurado e todas as dependências do projeto são instaladas automaticamente, garantindo que a execução ocorra em um ambiente limpo e padronizado.

2. **Execução dos Testes Unitários**  
   Todos os testes unitários são executados para validar se as principais funcionalidades do sistema permanecem estáveis após novas alterações.  
   *Objetivo:* evitar regressões e identificar falhas o mais cedo possível.

3. **Build do Projeto**  
   Após a validação dos testes, o projeto é compilado/empacotado para verificar se o código está em condição de ser implantado.  
   *Objetivo:* garantir que o código em `main` esteja sempre em estado "deployável".

**Benefício:**  
Esse processo automatizado reduz o risco de erros manuais, garante a estabilidade contínua do código e facilita a integração entre os desenvolvedores, permitindo que problemas sejam detectados logo no início do ciclo de desenvolvimento.
