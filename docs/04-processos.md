# Aula 04 - Modelo de Processos da Solução
## 1. Process Inventory
| Componente | Executa como | Iniciado por | Perfil | Recurso crítico | Se morrer... | Controle |
|---|---|---|---|---|---|---|
| API | serviço/processo | runtime/systemd/container | I/O-bound | rede/memória | usuários perdem 
acesso | healthcheck + restart + logs |
| Banco | serviço/processo | serviço gerenciado/container | I/O-bound | memória/disco | transações 
falham | backup + monitoramento + restart |
| Worker | processo/job | scheduler/fila | misto | CPU/memória | tarefas atrasam | retry + timeout + 
logs |
| <componente real> | ... | ... | ... | ... | ... | ... |
## 2. Ciclo de vida
Para cada componente, responda:
- como inicia?
- como sabemos que está saudável?
- como encerra de forma normal?
- como detectamos falha?
- quem reinicia?
- quais logs/métricas precisam existir?
## 3. Hipótese de falha
Escolha um processo crítico e descreva:
1. sintoma para o usuário;
2. evidência no SO/aplicação;
3. ação de recuperação;
4. risco de reiniciar incorretamente.
## 4. Decisões da Sprint
- Decisão 1: ...
- Decisão 2: ...
- Dívida técnica: ...
