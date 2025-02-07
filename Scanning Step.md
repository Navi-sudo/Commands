- Atua diretamente nas camadas de rede (IPV4 e IPV6) e transporte (TCP e UDP)
    - Manipular o cabeçalho dos protocolos
>> Todas as informações obtidas têm de ser consideradas __próximas__ ao real, pois podem ser falsas com intenção de atrapalhar o ataque <<
     (O que é avaliado é apenas a informção recebida, não o que de fato existe no alvo)
#### TCP
- Manipular as flags do TCP
- Estabelecer 3-Way HandShake com modificações para testar comportamento do alvo
      - Mandar em uma porta uma determinada flag, caso a porta estiver aberta, fechada ou filtrada, vai voltar a resposta com o estado da porta.




&nbsp;
  >> __TCP CONNECT:__ Estabelece uma conexão completa com o alvo (3-Way Handshake completo) **PROBLEMA: ELE TE DEIXA REGISTRADO NO ALVO, CASO HOUVER REGISTRO DE LOG VAI APARECER SEU IP**
>  > 




&nbsp;
  >> __TCP SYN:__ Estabelece uma conexão parcial (Half-Connect) - NMAP envia um pacote SYN, se estiver aberta responde com SYN ACK e a conexão será fechada (Classifica a porta como aberta, porém não completa a conexão com o alvo) **Só da pra fazer sendo ROOT no Linux**




&nbsp;  
  >> __TCP ACK:__ Envia um pacote TCP com a flag ACK ativada já na primeira conexão (Serve para testar se Firewalls estão bloqueando o caminho)




&nbsp;
  >> __TCP XMAS:__ Envia um pacote TCP com todas as flags ativadas e espera a resposta da porta para classifica-la como Aberta, Filtrada, Fechada, etc **SCAN ANTIGO, DIFICILMENTE FUNCIONARIA NOS DIAS DE HOJE**

<!--#### UDP
- Envia um pacote UDP
- (Não há flags no UDP)



&nbsp;
      >> Se a porta estiver aberta, uma resposta será enviada então o NMAP classificará como aberta




&nbsp;      
      >> Se a porta estiver fechada, um pacote do tipo ICMP PORT UNREACHABLE é enviado




&nbsp;
      >> Se a porta estiver filtrada nenhuma resposta será enviada




&nbsp;  
  >> **PROBLEMA DO UDP: MUITO MAIS LENTO (CASO PORTA ESTIVER FILTRADA OU PACOTE PERDIDO O NMAP FICA UM BOM TEMPO ESPERANDO)**
  --> 
