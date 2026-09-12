# Aula 03 - Reflexão individual
## 1. Ambiente
Kernel observado: <6.8.0-1064-azure>
Memória disponível: <7.8Gi>
Uma informação que me chamou atenção: <Os ID's para cada processo>
## 2. Processo
PID observado: <13995>
PPID observado: <6403>
Explique com suas palavras a diferença entre programa e processo: <Um programa é um arquivo estático salvo no disco do computador, enquanto um processo é esse mesmo programa quando está rodando na memória>
## 3. Proteção
Quem negou a leitura do arquivo e por quê? <O Kernel, porque ele não estava no quadro de permissões atribuídas>
## 4. Projeto da squad
Escolha UM componente do projeto (storage).
Esse componente rodaria como quê? <processo>
Se ele falhar, qual impacto de negócio aparece? <como o storage guarda desde arquivos até o SO, a falha dele seja permanente ou momentânea, no mínimo logs de erro e tela azul. Assim como a perda de dados importantes>
Qual controle deveria existir? <healthcheck>
