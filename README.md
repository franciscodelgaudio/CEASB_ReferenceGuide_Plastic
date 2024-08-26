# ANOTAÇÕES GUIA DE REFERÊNCIA PLASTIC SCM

## ESTRATÉGIA DE TRABALHO

### Ciclo de Trabalho

![aperfectworkflow-00](https://github.com/user-attachments/assets/8a91a344-55f8-405f-991b-b3b014fa94ac)
![aperfectworkflow-01](https://github.com/user-attachments/assets/2478cdbd-d458-4fbb-9610-49668a1b60ca)

*   Task
Tudo começa com uma tarefa no seu rastreador de problemas ou sistema de gerenciamento de projetos: Jira, Bugzilla, Mantis, Ontime ou sua própria solução caseira. A chave é que tudo o que você faz no código tem uma tarefa associada. Não importa se é parte de um novo recurso ou uma correção de bug; crie uma tarefa para isso. Se você ainda não está praticando isso, comece agora. Acredite em mim, inserir uma tarefa não é nada depois que você e sua equipe se acostumarem.

*   Task branch
Em seguida, você cria uma ramificação para a tarefa. Sim, uma ramificação para cada tarefa.

*   Develop
Você trabalha no seu branch de tarefa e faz quantos check-ins precisar. Na verdade, recomendamos fortemente fazer check-in com muita, muita frequência, explicando cada etapa nos comentários. Dessa forma, você estará explicando cada etapa ao revisor, e isso realmente vale a pena. Além disso, não se esqueça de adicionar testes para qualquer novo recurso ou correção de bug.

*   Code review
Depois que você marcar sua tarefa como concluída, ela pode ter o código revisado por um colega programador. Sem desculpas aqui, cada tarefa precisa de uma revisão de código.

*   Validation
Há uma etapa opcional que fazemos internamente: validação. Um colega muda para o branch de tarefa e o testa manualmente. Eles não procuram por bugs (testes automatizados cuidam disso), mas olham da solution/fix/new-featureperspectiva do cliente. O testador garante que a solução faça sentido. Esta fase provavelmente não faz sentido para todas as equipes, mas recomendamos fortemente quando possível.

*   Automated testing and merge
Depois que a tarefa for revisada/validada, ela será testada automaticamente. (Após ser mesclada, mas antes da mesclagem ser verificada. Mais sobre isso depois). Somente se o conjunto de testes passar na mesclagem, ele será confirmado. Isso significa que evitamos quebrar a compilação a todo custo.

*   Deploy
Você pode obter uma nova versão após cada nova tarefa passar por esse ciclo ou se decidir agrupar algumas. Estamos na era DevOps, com implantação contínua como o novo normal, então implantar cada tarefa na produção faz muito sentido.

### Uma tarefa por branch

#### Ramificação por padrao de tarefa

*   Crie uma nova ramificação para trabalhar em cada nova tarefa no rastreador de tarefas.
*   Criar tarefas curtas (O estilo SCRUM: Tarefas não devem durar mais do que 16 horas).
*   Branchs muitos longas podem causar `big bang integration`

![bigbang-03](https://github.com/user-attachments/assets/390f6435-c675-418b-a802-da5f24f82ed1)

*   Nao crie branchs que não fazem sentido isolodamente e não podem ser implementadas de forma independente.

![taskbranch-00](https://github.com/user-attachments/assets/81807b24-9525-4d41-be4f-5209e22ad4a6)

#### Convenção de nomenclatura de ramificação

*   prefixo + número da tarefa. Exemplo `task1213`.
*   Prefixos também sao vinculados a rastreadores de tarefas como o Jira.
