# Sprint - 3️⃣

## Requisitos realizados nessa sprint ✨

- **Gerenciamento de Relatórios:**
  - Geração de relatórios baseados nos dados e parâmetros definidos no sistema para análises de risco meteorológico potencial, em formato PDF  gerado a partir dos dados de uma estação específica.
- **Desenvolvimento de Datalogger:**
  - Implementação de um datalogger para registrar dados em uma estação meteorológica. Deve registrar dados de múltiplos sensores (temperatura, umidade, pressão, velocidade e direção do vento, etc.) ter capacidade de trasnmissão de dados para o sistema
- **Montagem de Estação Meteorológica:**
  - Construção física de uma estação meteorológica com os componentes necessários. Montagem da estação e testes de funcionamento (verificar se está ligando corretamente, verificar se está enviando dados, etc.)
- **Landing Page explicativa**
  - Desenvolvimento de um portal (página) explicativo sobre o funcionamento do sistema, o significado de cada parâmetro meteorológico medido, e o impacto social no monitoramento de risco. O portal irá descrever o funcionamento do sistema, o que são as estações, e quais os tipos de parâmetro lidos. Também, o portal deve ser atraente para todos os tipos de público, mas principalmente para o público na faixa etária da adolescência.
- **Dashboard de Estações Meteorológicas**
  - Garantir que o sistema se mantenha ativo o tempo todo para não perder leituras de risco potencial. A infraestrutura do sistema deve ser capaz de armazenar e exibir todos os dados enviados pelas estações sem exceções. 

## User Stories realizados nessa sprint 📖

| Rank | Prioridade | User Story | Estimativa | Sprint |
| :--- | :--- | :--- | :--- | :--- |
| 14 | Alta | Como administrador, quero configurar um datalogger linkado à arquitetura do meu sistema, para registrar os dados colhidos dos sensores nas estações e posteriormente enviar esses dados para o meu sistema processá-los | 8 | 3 |
| 15 | Alta | Como dono do sistema, quero montar estações meteorológicas em pontos de risco da minha cidade, para obter leituras importantes das condições climáticas da região | 3 | 3 |
| 16 | Média | Como administrador, quero gerar relatórios sobre os registros presentes no sistema, para verificar a situação das áreas monitoradas num período de tempo determinado | 5 | 3 |
| 17 | Baixa | Como usuário público, quero visualizar uma seção educativa relacionada ao sistema na página principal, para informar ao público sobre a importância da análise dos dados das estações meteorológicas e como isso pode impactar no cotidiano de pessoas alocadas em área de risco. | 3 | 3 |
| 18 | Baixa | Como administrador, quero poder consultar um manual do sistema, para poder treinar novos usuários sobre como utilizar o sistema como um todo | 3 | 3 |

## Critérios de aceitação para cada User Story

### US13

O datalogger precisa enviar os dados colhidos dos sensores para o broker.
A configuração da placa deve permitir que o datalogger funcione de forma autônoma, sem precisar de intervenção de usuários no sistema.

### US14

As estações devem ser montadas nos locais definidos pelo cliente.
As estações devem funcionar de forma autônoma, enviando os dados dos sensores, data e hora e porcentagem da bateria da estação.

### US15

A página principal do sistema deve ter uma seção educativa de fácil acesso para visitantes não logados.
O conteúdo deve explicar a importância do monitoramento climático e como os dados podem ajudar a população em áreas de risco.
O conteúdo deve mostrar e explicar o que cada estação com seus sensores é capaz de medir.
A linguagem utilizada na seção deve ser simples e clara, sem jargões técnicos, para ser compreendida pelo público geral.

### US16

O manual deve detalhar o funcionamento de cada componente do sistema.
O conteúdo deve estar sumarizado no começo do documento.
As funcionalidades precisam estar detalhadas com imagens indicando as ações que podem ser feitas em cada página.
Deve ser disponibilizado no repositório do projeto como um documento PDF.

## Slides para apresentação 🎞️

**<a href="../../media/slides_sprint_2.pdf" _target="blank" download="sprint-2-apresentacao">Clique para acessar a apresentação no Canva</a>**