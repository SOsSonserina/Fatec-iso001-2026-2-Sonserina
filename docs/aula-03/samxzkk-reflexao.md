# Aula 03 - Reflexão individual
## 1. Ambiente
Kernel observado: <6.8.0-1064-azure>
Memória disponível: <7.8Gi>
Uma informação que me chamou atenção: <Memória>
## 2. Processo
PID observado: <2294>
PPID observado: <383>
Explique com suas palavras a diferença entre programa e processo: <programa é um arquivo estático, processo é esse mesmo programa enquanto roda na memória>
## 3. Proteção
Quem negou a leitura do arquivo e por quê? <o kernel precisando de permissão>
## 4. Projeto da squad
Escolha UM componente do projeto (API, banco, worker, storage, etc.).
Esse componente rodaria como quê? <API: Serviço/processo>
Se ele falhar, qual impacto de negócio aparece? <o usuário não conseguiria acessar as funcionalidades do processo>
Qual controle deveria existir? <healthcheck>