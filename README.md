## Teste de Comunicação Modbus TCP entre duas instâncias do NodeRed


## Objetivo

O presente teste tem o objetivo de documentar os testes de comunicação do seguinte *node* [Modbus](https://flows.nodered.org/node/node-red-contrib-modbus).

## Desenvolvimento

Basicamente os teste e configuração irá seguir a seguinte estrutura:
<img src="https://github.com/dedynobre/comunicacao-modbus-tcp-com-node-red/blob/master/images/nodered-com-01.jpg"/></br>


### Configuração Servidor

Como a configuração é bem simples, nas imagens fica bem simples o entendimento:

1. Nodes de configuração do servidor modbus tcp:
	<img src="https://github.com/dedynobre/comunicacao-modbus-tcp-com-node-red/blob/master/images/nodered-com-03.jpg"/></br>

2. Menu de configuração no node Modbus Server:</br>
	<img src="https://github.com/dedynobre/comunicacao-modbus-tcp-com-node-red/blob/master/images/nodered-com-02.jpg"/></br>
	
3. Nodes de escrita em determinado registro:
	<img src="https://github.com/dedynobre/comunicacao-modbus-tcp-com-node-red/blob/master/images/nodered-com-04.jpg"/></br>
	
	+ O primeiro node(inject) está executando uma rotina a cada 2 segundos.
	+ O segundo node(randon) gera valores aleatórios dentro de um faixa configurado na sua interface e tem sua saída no parâmetro *msg.payload* conforme as configurações abaixo:
		<img src="https://github.com/dedynobre/comunicacao-modbus-tcp-com-node-red/blob/master/images/nodered-com-05.jpg"/></br>
	+ O terceiro é o node que *lê/escreve* os valores nos registros no servidor modbus tcp, que no nosso caso é escrita:
		+ **Server**: define o servidor modbus tcp que vamos usar para escrever/ler valores.
		+ **FC**: é o modo de operação que o node irá funcionar, por exemplo, ler/escreve unico registro ou ler/escrever múltiplos registros.
		+ **Address**: é o endereço modbus tcp.</br>
		<img src="https://github.com/dedynobre/comunicacao-modbus-tcp-com-node-red/blob/master/images/nodered-com-06.jpg"/></br>
	
