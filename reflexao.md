## **Questão 1:** ##
O ConfigRepository define o contrato. É a abstração que garante que qualquer estratégia escolhida terá o método .get(), tornando o código cliente  genérico.
O LocalConfig é a implementação específica. Contém o algoritmo real para buscar configurações de um arquivo local.
E get_repo_from_env() lê o contexto das variáveis de ambiente e escolhe qual estratégia instanciar, isolando a lógica de escolha da lógica de execução.
## **Questão 2:**

### 2.1 ###
Para deixar de ser estática, a lógica de resolução deve sair do __init__ e ir para o método resolve
### 2.2 ###
Apache ZooKeeper e AWS Cloud Map
