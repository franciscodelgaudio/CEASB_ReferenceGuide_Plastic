# Plastic SCM at CEASB Reference Guide

## Ciclo de Trabalho

*   **Task**: Cada alteração no código deve estar associada a uma tarefa, seja para um novo recurso ou correção de bug.
*   **Task branch**: Crie uma ramificação específica para cada tarefa.
*   **Develop**: Trabalhe na sua ramificação de tarefa, fazendo check-ins frequentes e explicando cada etapa nos comentários.
*   **Code review**: Após concluir a tarefa, peça a um revisor para revisar o código.
*   **Test and Merge**: Depois que a tarefa for revisada/validada, ela será testada. Somente se o conjunto de testes passar na mesclagem, ele será confirmado.
*   **Deploy**: A nova versão é adicionada a branch principal.

<div align="center">
  <img src="https://github.com/user-attachments/assets/8a91a344-55f8-405f-991b-b3b014fa94ac">
</div>

## Branchs

### Ramificação por padrão de tarefa

*   Crie uma nova branch para trabalhar em cada nova tarefa do rastreador de tarefas.
*   Criar tarefas curtas e branchs curtas. Branchs muitos longas podem causar `big bang integration`.

Exemplo de um `big ban integration`:
<div align="center">
  <img src="https://github.com/user-attachments/assets/390f6435-c675-418b-a802-da5f24f82ed1">
</div>

*   Nao crie branchs que não fazem sentido isoladamente e não podem ser implementadas de forma independente.
*   Evite ao máximo branchs que dependam uma das outras.
*   Você pode atribuir combinações de pares de valores a uma ramificação. Um caso de uso típico é definir um status: resolvido, aberto, mesclado, com falha.
*   Atribua um status ao `check-in` como: `resolved`, `open`, `merged`, com `failed`.

Exemplo Incorreto:
<div align="center">
  <img src="https://github.com/user-attachments/assets/a4ad5b68-ab6a-4367-8d22-9cbb3d389d80">
</div>

*   Caso as tarefas precisem depender uma das outras, avise o _build-master_ ou _integrador_.
*   Uma task concluída deve estar pronta para ser implementada.
*   Não faça `Checkin` apenas uma vez.
*   Não faça `Checkin` para você mesmo, ou seja, faça o `Checkin` com o revisor em mente.

| Exemplo de `Checkin` para você mesmo (**Incorreto**). | Exemplo de `Checkin` para um revisor. (**Correto**). |
| :----: | :----: |
| <img src="https://github.com/user-attachments/assets/d1c25faa-1db7-480a-b34e-41ba1a811c05"/> | <img src="https://github.com/user-attachments/assets/5bfded91-09b4-4e86-98be-5a78614866a8" /> |

#### Nomenclatura da branch

*   O nome da branch deve seguir o padrão: prefixo + número da tarefa. Exemplo `task1213`.
*   Prefixos também sao vinculados a rastreadores de tarefas como o Jira/Trello.

#### Conflitos em build

| Conflito | Solução |
| :----: | :----: |
| <img src="https://github.com/user-attachments/assets/bc85e496-9943-4b1e-9382-cb7ae04c7710" alt="project"/> | <img src="https://github.com/user-attachments/assets/6f73c544-f85b-4ecf-8a4c-1d8701a58970" alt="project"/> |

*   Conflitos em build é responsabilidade do programador que realizou a última alteração.
*   A imagem acima é um exemplo de solução de conflito na build.
