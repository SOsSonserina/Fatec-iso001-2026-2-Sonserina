# Aula 03 - Reflexão individual
## 1. Ambiente
Kernel observado: <6.8.0-1064-azure>
Memória disponível: <Total: 7.8Gi Disponível: 5.7Gi>
Uma informação que me chamou atenção: <Ter aprendido e visto de perto os PID'S, usei programas a vida toda, e nunca reparei nisso... nem mesmo no Gerenciador de Tarefas>
## 2. Processo
PID observado: <12099>
PPID observado: <3914>
Explique com suas palavras a diferença entre programa e processo: <O Programa é aquilo diretamente instalado no computador, o processo - ou processos - são aquilo que rodam diretamente e internamente nele.>
## 3. Proteção
Quem negou a leitura do arquivo e por quê? <O Kernel do Linux, negou pois - pelo que pesquisei - quando rodei chmod 000, todas as permissões foram tiradas...>
## 4. Projeto da squad
Escolha UM componente do projeto (storage).
Esse componente rodaria como quê? <processo>
Se ele falhar, qual impacto de negócio aparece? <Se o Storage falha, arquivos podem se perder, falhas acontecerem, e, como mencionado em sala... Uma tela azul, se fosse um SO. Mas, visto que o CodeSpace roda na nuvem, a perda dos dados que meu Squad modificou poderia acontecer.>
Qual controle deveria existir? <healthcheck>