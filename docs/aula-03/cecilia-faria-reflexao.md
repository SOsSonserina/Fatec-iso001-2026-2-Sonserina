# Aula 03 - Reflexão individual
## 1. Ambiente
Kernel observado: <6.8.0-1052-azure>
Memória disponível: <5.7 GiB (de um total de 7.8 GiB)>
Uma informação que me chamou atenção: <...>
## 2. Processo
PID observado: <24266>
PPID observado: <2743>
Explique com suas palavras a diferença entre programa e processo: < Programa é apenas o arquivo salvo no computador (como um aplicativo fechado). O processo é esse programa funcionando na memória enquanto a gente usa.>
## 3. Proteção
Quem negou a leitura do arquivo e por quê? < O próprio sistema Kernel bloqueou o acesso porque o comando `chmod 000` retirou todas as permissões de leitura do arquivo.>
## 4. Projeto da squad
Escolha UM componente do projeto (API, banco, worker, storage, etc.) <API>. 
Esse componente rodaria como quê? < processo/serviço/arquivo/etc. Serviço (um  programa rodando em segundo plano)>
Se ele falhar, qual impacto de negócio aparece? < O site/app para de funcionar e os usuários não conseguem nem entrar e nem usar.>
Qual controle deveria existir? <log/healthcheck/restart/permissão/etc.   Healthcheck para monitorar o status, logs para identificar erros e restart automático se o processo fechar.>