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
Usando essas wordlists, iremos usar o Medusa novamente para tentar os logins e senhas que colocamos nos nossos arquivos de texto para acessar o sistema, procure pelo SUCCESS depois de usar o Medusa para saber qual o login e senha corretos.

Para prevenir esse tipo de ataque é necessário controles de segurança, como limite de tentativas por IP, bloqueio temporário por IP, entre outras

-------------------------------------------------------------------------------------------------------------------------------------

Agora iremos falar sobre password spraying e SMB, SMB é um protocolo do windows que é usado para compartilhar arquivos, pastas, impressoras e outros recursos entre computadores em uma rede, comum em ambientes Windows, macOS e Linux. Password spraying é uma técnica furtiva de força bruta, visto que muitos sistemas bloqueiam seu acesso após muitas tentativas malsucedidas no mesmo usuário, a técnica consiste em tentar senhas em usuários diferentes e ir alternando, assim não sendo bloqueado.

Primeiro de tudo precisamos saber quais são os usuários antes de tentar as senhas, visto que se tentarmos muitos usuários não existentes, o sistema pode nos bloquear, para descobrir os usuários reais do sistema, usamos um processo chamado de enumeração de usuários a partir da ferramente enum4linux.
Após usar a ferramente com o comando na aba Comandos, procure o nome user: que vai marcar todos os nomes de usuários reais.

Agora criaremos uma lista com os usuários retirados do enum4linux e logo depois criar uma lista com senhas para testar usando o spray.
Após isso finalmente podemos usar o Medusa para invadir. Depois de rodar o código, procure pelo texto ACCOUNT FOUND e SUCCESS para saber qual tentativa foi bem sucedida

Após conseguir o acesso precisamos verificar se realmente vamos ter acesso como administrador, para isso rodamos um código simples mencionado na página Comandos.
Logo após conseguir acesso, use a senha que conseguimos durante o spray. Isso vai confirmar que temos accesso como administrador a rede, podendo baixar arquuivos, subir payloads ou navegar pelo sistema.

Para se proteger desse tipo de ataque use autenticação multifatores, que mesmo caso acertem sua senha, existe uma camada extra de proteção que exige outras técnicas mais avançadas, outra coisa importante é usar senhas fortes e troca-las regularmente, assim é dificil usar força bruta pra acessar, outra forma é o bloqueio de IP após diversas tentativas de login, podemos usar também segmentação da rede para não deixar arquivos internos expostos e auditorias regulares usando a própria ferramenta Medusa.
