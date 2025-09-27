# Gestão do Processo - Projeto Gaia

Este documento descreve o fluxo de trabalho adotado pela equipe **Ctrl+Alt+Del** para o desenvolvimento do Projeto Gaia. Nosso processo visa garantir agilidade, qualidade e transparência, desde a concepção de uma ideia até a entrega do valor em produção.

---

### Nosso Fluxo de Trabalho em 4 Etapas

O nosso processo pode ser dividido em quatro grandes etapas sequenciais:

### 1. Entendimento e Priorização

Tudo começa com a necessidade do cliente, que é recebida e analisada pelo **Product Owner (PO)**.

* **Entrada:** A dor principal, ideias de funcionalidades ou problemas reportados pelo cliente são registrados pelo PO, que é responsável por detalhar tudo que foi conversado. Após analisar o que foi dito nas reuniões e pesquisar sobre possíveis soluções, o PO elabora uma **Proposta de Solução** que é apresentada ao cliente para que ele possa validar se a solução atende às suas **necessidades**.
* **Refinamento:** Se aprovada, **Requisitos** são extraídos da proposta de solução, documentados em um documento formal, que é novamente apresentado ao cliente para verificar se eles refletem as necessidades do cliente do ponto de vista técnico.
* **MVP:** Após a validação dos requisitos, o PO juntamente à equipe, elaboram um **MVP (Minimum Viable Product)**, que demonstra de forma básica como será o produto final, podendo ser um wireframe ou um protótipo navegável(Figma, UXPilot, etc).
* **Priorização:** Em reuniões de alinhamento, a equipe discute os requisitos com o PO para entender o valor de cada um e definir as user stories e suas prioridades. O objetivo é garantir que estamos sempre trabalhando no que gera mais impacto para o projeto.

### 2. Planejamento e Definição (Planning)

Com os requisitos priorizados e as user stories definidas, a equipe realiza a reunião de **Planning**.

* **Seleção:** A equipe de desenvolvimento seleciona os itens do topo do backlog para trabalhar no próximo ciclo.
* **Quebra de Tarefas:** Os requisitos são decompostos em tarefas técnicas menores e mais gerenciáveis.
* **Definição de Pronto (DoR):** Para uma tarefa ser iniciada, ela precisa atender à nossa **"Definition of Ready" (DoR)**, o que significa que ela está clara, detalhada e pronta para ser desenvolvida sem impedimentos.
* **Estimativa:** A equipe atribui uma estimativa de esforço para cada tarefa, o que ajuda a planejar a capacidade do ciclo de trabalho.

### 3. Desenvolvimento e Qualidade

Nesta etapa, o código é escrito e a qualidade da entrega é garantida.

* **Codificação:** O desenvolvedor assume uma tarefa e inicia a implementação.
* **Pull Request (PR):** Ao concluir a tarefa, o desenvolvedor abre um **Pull Request** no repositório. Este ato sinaliza que o código está pronto para revisão.
* **Testes e Revisão (Code Review):** A abertura do PR dispara testes automatizados. Além disso, o código é revisado por, no mínimo, outro membro da equipe. Essa revisão é fundamental para garantir a qualidade, encontrar bugs e compartilhar conhecimento. Nenhum código é integrado sem a aprovação da equipe.

### 4. Integração e Deploy (CI/CD)

Após a aprovação, o código é integrado e entregue aos ambientes de forma automatizada, um processo conhecido como **Continuous Integration/Continuous Deployment (CI/CD)**.

Nosso fluxo conta com dois ambientes principais:

* **Ambiente de Homologação (Dev/Staging):**
    * **Gatilho:** Qualquer integração de código na base principal dispara uma entrega automatizada para este ambiente.
    * **Frequência:** As entregas ocorrem continuamente, com o objetivo de acontecer **pelo menos uma vez por dia**.
    * **Objetivo:** Permitir que a equipe valide as novas funcionalidades de forma integrada e contínua.

* **Ambiente de Produção (Prod):**
    * **Gatilho:** A entrega é realizada quando um requisito completo é validado e aprovado.
    * **Objetivo:** Disponibilizar valor real para o usuário final de forma consistente e previsível.

Finalmente, após a entrega, realizamos a **Análise de Desempenho** em ambos os ambientes para monitorar a estabilidade e a eficiência da aplicação.