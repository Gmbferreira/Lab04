## **Questão 1:** ##
O ConfigRepository define o contrato. É a abstração que garante que qualquer estratégia escolhida terá o método .get(), tornando o código cliente  genérico.
O LocalConfig é a implementação específica. Contém o algoritmo real para buscar configurações de um arquivo local.
E get_repo_from_env() lê o contexto das variáveis de ambiente e escolhe qual estratégia instanciar, isolando a lógica de escolha da lógica de execução.
## **Questão 2:**

### 2.1 ###
Para deixar de ser estática, a lógica de resolução deve sair do __init__ e ir para o método resolve
### 2.2 ###
Apache ZooKeeper e AWS Cloud Map

## **Questão 3:** ##

## **Questão 4:** ##
### 4.1 ###

### 4.2 ###
Ele não garante exactly-once. Mensagens são perdidas se o processo cair (Possivelmente devido a RAM) ou se a reconexão falhar definitivamente. Duplicatas ocorrem pela falta de confirmações (ACKs) do servidor, levando o cliente a reenviar mensagens que já haviam sido processadas antes da migração.

### 4.3 ###
Modelar estados explícitos evita a explosão de booleanos (explosão combinatória(Crescimento exponencial de estados)) e estados inválidos causado por conflito entre flags. Isso permite aplicar comportamentos distintos para cada fase, tornando o código mais legível e fácil de expandir.
### 4.4 ###
Microsoft Orleans