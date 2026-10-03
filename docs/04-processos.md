# Aula 04 - Modelo de Processos da Solução
## 1. Process Inventory
| Componente | Executa como | Iniciado por | Perfil | Recurso crítico | Se morrer... | Controle |
|---|---|---|---|---|---|---|
| API | serviço | container | I/O-bound | rede/memória | usuários perdem acesso | healthcheck + restart + logs |
| Banco | serviço | container | I/O-bound | memória/disco | transações falham | backup + monitoramento + restart |
| Worker | processo | scheduler | misto | CPU/memória | tarefas atrasam | retry + timeout + logs |
| interface | serviço | navegador/web server | I/O-bound | Rede | usuários não conseguem acessar o sistema | monitoramento + logs |

## 2. Ciclo de vida

### API
- como inicia? Inicia quando o container ou serviço é executado.
- como sabemos que está saudável? Responde às requisições dos usuários.
- como encerra de forma normal? Finaliza conexões e encerra o processo.
- como detectamos falha? Erros nos logs ou ausência de resposta.
- quem reinicia? Runtime, systemd ou container.
- quais logs/métricas precisam existir? Logs de acesso, erros e tempo de resposta.

### Banco
- como inicia? Inicia junto com o serviço de banco de dados.
- como sabemos que está saudável? Aceita conexões e consultas.
- como encerra de forma normal? Finaliza conexões e grava os dados pendentes.
- como detectamos falha? Erros de conexão ou indisponibilidade.
- quem reinicia? Serviço gerenciado ou container.
- quais logs/métricas precisam existir? Logs de consultas, erros e uso de recursos.

### Worker
- como inicia? É iniciado pela fila ou scheduler.
- como sabemos que está saudável? Processa tarefas normalmente.
- como encerra de forma normal? Finaliza a tarefa atual e encerra.
- como detectamos falha? Acúmulo de tarefas ou erros de execução.
- quem reinicia? Scheduler ou container.
- quais logs/métricas precisam existir? Logs de tarefas, falhas e tempo de execução.

### Interface
- como inicia? É carregada pelo navegador ou servidor web.
- como sabemos que está saudável? Permite acesso e interação dos usuários.
- como encerra de forma normal? Finaliza a sessão ou o serviço.
- como detectamos falha? Página indisponível ou erros de acesso.
- quem reinicia? Servidor web ou container.
- quais logs/métricas precisam existir? Logs de acesso e erros.
  
## 3. Hipótese de falha
Processo crítico: Banco.
1. Sintoma para o usuário: Não é possível finalizar pedidos.
2. Evidência no SO/aplicação: Erros de conexão registrados nos logs.
3. Ação de recuperação: Reiniciar o serviço e verificar a conectividade.
4. Risco de reiniciar incorretamente: Perda de transações em andamento.
   
## 4. Decisões da Sprint
- Decisão 1: Separar API e banco de dados em componentes diferentes;
- Decisão 2: Utilizar logs para monitoramento da aplicação;
- Dívida técnica: Definir estratégia completa de backup e recuperação.
