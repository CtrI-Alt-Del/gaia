# Gestão do Conhecimento - Projeto Gaia

Este documento centraliza o conhecimento do projeto Gaia, descrevendo a necessidade do cliente que originou o projeto, a solução desenvolvida por nossa equipe, os diferenciais da nossa abordagem e as informações gerais do produto final.

---

## 1. A Dor do Cliente

A empresa **Tecsus**, especializada na coleta e processamento de dados de utilidades (água, energia e gás) via redes de sensores IoT, identificou uma oportunidade estratégica para expandir seu portfólio para a área de **monitoramento ambiental**.

O desafio apresentado pela empresa consistia em múltiplas necessidades interconectadas:

* **Expansão de Mercado:** Entrar no segmento de monitoramento ambiental, uma área de crescente importância.
* **Viabilidade Econômica:** A solução precisava ser de **baixo custo** para ser escalável e competitiva.
* **Desenvolvimento de Ponta a Ponta:** Necessidade de uma solução completa, desde o hardware (estações meteorológicas) até o software (plataforma de visualização de dados).
* **Impacto Social e Educacional:** Um requisito chave era criar um portal que não apenas exibisse os dados, mas que também tivesse uma **finalidade pedagógica**. A plataforma deveria servir como uma ferramenta de ensino para alunos do ensino médio, demonstrando conceitos matemáticos aplicados e conscientizando sobre a prevenção de desastres naturais.
* **Validação Prática:** O projeto deveria ser implementado e validado em locais reais, como a Escola Estadual Elmano Ferreira Veloso e a Fatec de São José dos Campos, para testar sua eficácia e usabilidade.

Em resumo, a dor da Tecsus não era apenas tecnológica, mas também estratégica e educacional. A empresa precisava de um parceiro capaz de desenvolver um produto completo, inovador, de baixo custo e com um forte apelo social.

---

## 2. Nossa Proposta de Solução: O Projeto Gaia

Para solucionar o desafio da Tecsus, nossa equipe, a **Ctrl+Alt+Del**, propôs o **Projeto Gaia**: um ecossistema completo e integrado de monitoramento meteorológico com foco em educação e acessibilidade.

Nossa solução é composta por três pilares principais:

1.  **Hardware (Estações Meteorológicas):** Utilização de estações meteorológicas de baixo custo, equipadas com sensores para medir direção e velocidade do vento, índice pluviométrico, umidade, temperatura e pressão. Esses dispositivos são projetados para coletar dados ambientais de forma autônoma e periódica.

2.  **Infraestrutura de Dados:** Implementação de um fluxo de dados robusto. As informações coletadas pelas estações são enviadas para um servidor central utilizando tecnologias de comunicação IoT (Broker MQTT). No servidor, os dados são recebidos, tratados e armazenados de forma segura e eficiente, prontos para serem consumidos.

3.  **Software (Portal Educacional):** Criação de uma plataforma web interativa que serve a um duplo propósito:
    * **Para a Tecsus:** Oferece dashboards e relatórios técnicos para a visualização e análise dos dados coletados, permitindo o monitoramento contínuo das condições climáticas.
    * **Para a Comunidade:** Apresenta os dados de forma didática, explicando os conceitos matemáticos por trás dos cálculos (por exemplo, como a velocidade do vento é calculada) e contextualizando a importância desses dados para a geração de alertas e prevenção de desastres naturais.

---

## 3. Por que nossa solução funciona bem?

O Projeto Gaia não é apenas uma resposta técnica ao desafio, mas uma solução estratégica que agrega valor em diversas frentes, tornando-a eficaz e alinhada aos objetivos do cliente.

* **Custo-Benefício:** Utilizando componentes de hardware acessíveis e software de código aberto, atingimos o requisito de baixo custo sem comprometer a qualidade e a precisão dos dados, tornando a solução escalável.
* **Abordagem Holística:** Entregamos uma solução *end-to-end* (ponta a ponta). Cuidamos desde a montagem do sensor físico até a interface final com o usuário, eliminando a necessidade de o cliente integrar múltiplas soluções de diferentes fornecedores.
* **Foco no Engajamento:** O portal educacional é o nosso grande diferencial. Ele transforma um produto de monitoramento técnico em uma poderosa ferramenta de **Aprendizagem Baseada em Problemas (PBL)**, gerando engajamento com estudantes e criando um impacto social positivo que fortalece a imagem da Tecsus.
* **Tecnologia e Inovação:** O projeto aplica conceitos modernos de IoT, Cloud Computing e Desenvolvimento Web, resultando em um produto robusto, confiável e alinhado com as melhores práticas do mercado.
* **Validação em Campo:** A instalação dos protótipos em ambientes reais (escola e faculdade) garante que o produto final será testado e aprimorado com base no feedback de usuários reais, assegurando sua eficácia e usabilidade.

---

## 4. Informações Gerais do Produto

* **Nome do Projeto:** Gaia
* **Equipe Responsável:** Ctrl+Alt+Del
* **Objetivo Principal:** Desenvolver um sistema de monitoramento meteorológico de baixo custo para visualização de dados e geração de alertas juntamente com uma plataforma web educacional.
* **Público-Alvo:**
    * **Cliente Primário:** Tecsus (para expansão de seu portfólio de serviços).
    * **Usuários paralelos:** Alunos e professores do ensino médio, comunidades locais interessadas em monitoramento ambiental.
* **Principais Funcionalidades:**
    * Coleta periódica de dados de vento (direção e velocidade), chuva, umidade, temperatura e pressão.
    * Transmissão de dados via redes IoT.
    * Processamento e armazenamento dos dados em nuvem.
    * Exibição de dashboards e relatórios em tempo real.
    * Seção educacional interativa no portal.
    * Sistema de geração de alertas para prevenção de desastres.
* **Tecnologias Envolvidas:**
    * **Hardware:** Sensores meteorológicos, microcontroladores.
    * **Comunicação:** Protocolos IoT (HiveMQ).
    * **Backend:** NestJS, Node.js.
    * **Frontend:** Remix, Tailwind CSS.
    * **Banco de Dados:** MongoDB, PostgreSQL, Prisma.
    * **Infraestrutura:** Docker, Terraform.