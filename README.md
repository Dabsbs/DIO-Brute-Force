# DIO-Brute-Force
Desafio de força bruta das aulas da DIO com Kali Linux e Medusa

Para mais informações sobre os comandos acessar Comandos

A Primeira etapa foi configurar o Virtual Box com uma máquina Kali Linux e outra máquina Metasploitable 2, e depois configurar os dois com rede interna host only.

A segunda etapa foi usar o comando ping para ver se as máquinas realmente estão conectadas.

Terceira etapa é usar o nmap para saber quais portas estão vulneráveis.

quarta etapa é entrar no ftp que está vulnerável (porta 21) e criar um arquivo de texto com senhas e usuarios comuns.

Quinta etapa foi usar a Medusa com todas as peças anteriores para descobrir na força bruta qual a senha e usuário.

Com isso termina a força bruta em ftp, para evitar que esse tipo de infiltração aconteça é recomendado o uso de senhas fortes e deixar seu sistema atualizado.
Próxima etapa é a força bruta em formularios de login web.
