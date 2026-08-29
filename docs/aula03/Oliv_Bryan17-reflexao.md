# Aula 03 - Reflexão individual
## 1. Ambiente
Kernel observado: <6.8.0-1052-azure>
Memória disponível: <7.8Gi>
Uma informação que me chamou atenção: <Ubuntu>
## 2. Processo
PID observado: <21366>
PPID observado: <20789>
Explique com suas palavras a diferença entre programa e processo: <Programa é o que realiza o processo>
## 3. Proteção
Quem negou a leitura do arquivo e por quê? <o programa recusou a entrada por falta de permissão, que eu mesmo removi>
## 4. Projeto da squad
Escolha UM componente do projeto (API).
Esse componente rodaria como quê? <serviço>
Se ele falhar, qual impacto de negócio aparece? <Perca de informações e possível conflito>
Qual controle deveria existir? <healthcheck/restart>