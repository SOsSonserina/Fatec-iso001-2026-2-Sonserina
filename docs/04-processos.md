# Aula 04 - Modelo de Processos da Solução
## 1. Process Inventory
| Componente | Executa como | Iniciado por | Perfil | Recurso crítico | Se morrer... | Controle |
|---|---|---|---|---|---|---|
| API | serviço/processo | runtime/systemd/container | I/O-bound | rede/memória | usuários perdem acesso | healthcheck + restart + logs |
| Banco | serviço/processo | serviço gerenciado/container | I/O-bound | memória/disco | transações 
falham | backup + monitoramento + restart |
| Worker | processo/job | scheduler/fila | misto | CPU/memória | tarefas atrasam | retry + timeout + 
logs |
| Interface | Serviço | Navegador/web server | I/0-bound | Rede | Usuários não conseguem acessar o sistema | Monitoramento + logs |
## 2. Ciclo de vida
Para cada componente, responda:
- como inicia? Inicia quando o container ou serviço é executado. 
- como sabemos que está saudável? Responde às requisições dos usuários.
- como encerra de forma normal? Finaliza conexões e encerra o processo.
- como detectamos falha? Erros nos logs ou ausência de resposta.
- quem reinicia? Runtime, systemd ou container.
- quais logs/métricas precisam existir? Logs de acesso, erros e tempo de resposta.
## 3. Hipótese de falha
Processo crítico: Não é possível finalizar pedidos.
1. Sintoma para o usuário: Não é possível finalizar pedidos;
2. Evidência no SO/aplicação: Erros de conexão registrados nos logs;
3. Ação de recuperação: Reiniciar o serviço e verificar a conectividade;
4. Risco de reiniciar incorretamente: Perda de transações em andamento.
## 4. Decisões da Sprint
- Decisão 1: Separar API e banco de dados em componentes distintos;
- Decisão 2: Utilizar logs para monitoramento da aplicação;
- Dívida técnica: Definir estratégia completa de backup e recuperação.
