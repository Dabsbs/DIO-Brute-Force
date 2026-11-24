# DIO-Brute-Force
Desafio de força bruta das aulas da DIO com Kali Linux e Medusa

Para mais informações sobre os comandos acessar Comandos

A Primeira etapa foi configurar o Virtual Box com uma máquina Kali Linux e outra máquina Metasploitable 2, e depois configurar os dois com rede interna host only.

A segunda etapa foi usar o comando ping para ver se as máquinas realmente estão conectadas.

Terceira etapa é usar o nmap para saber quais portas estão vulneráveis.

quarta etapa é entrar no ftp que está vulnerável (porta 21) e criar um arquivo de texto com senhas e usuarios comuns.

Quinta etapa foi usar a Medusa com todas as peças anteriores para descobrir na força bruta qual a senha e usuário.

Com isso termina a força bruta em ftp, para evitar que esse tipo de infiltração aconteça é recomendado o uso de senhas fortes e deixar seu sistema atualizado.
---------------------------------------------------------------------------------------------------------------------------------
Próxima etapa é a força bruta em formularios de login web.

Para testes dentro do Kali, entrar em um site feito com diversas brechas para aprendizado assim como o Metasploitable.
A URL dele vai ser seu ip /dvwa/login.php
no meu caso ficaria 192.168.56.101/dvwa/login.php

Para descobrir o acesso, precisamos abrir o painel de dev, para acessa-lo aperte F12 ou FN + F12.
Aperte em Network para saber o que o navegador está recebendo e teste um login e senha aleatório com essa aba aberta, assim poderemos ver
nossa tentativa pelo painel, que aparece como POST, clique nele e vá em Request para ver os dados do que acabamos de digitar, logo o Medusa vai tirar grande proveito disso.

Próxima etapa é criar wordlists, assim como criamos antes com diversos logins e senhas, pode usar os mesmos arquivos de antes.
Usando essas wordlists, iremos usar o Medusa novamente para tentar os logins e senhas que colocamos nos nossos arquivos de texto para acessar o sistema, procure pelo SUCCESS depois de usar o Medusa para saber qual o login e senha corretos
