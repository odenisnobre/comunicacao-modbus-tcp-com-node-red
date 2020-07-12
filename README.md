<h1 align="center">
<br>
Teste de Comunicação Modbus TCP entre duas instâncias do Node-Red
</h1>

<p align="center">O projeto tem como objetivo documentar os testes de comunicação do seguinte *node* [Modbus](https://flows.nodered.org/node/node-red-contrib-modbus).*.</p>

<p align="center">
  <a href="https://www.apache.org/licenses/LICENSE-2.0">
    <img src="https://img.shields.io/badge/apache-2.0-blue" alt="License Apache">
  </a>
</p>

## Desenvolvimento

Basicamente os teste e configuração irá seguir a seguinte estrutura:
<img src="https://github.com/dedynobre/comunicacao-modbus-tcp-com-node-red/blob/master/images/nodered-com-01.jpg"/></br>


## Configuração Servidor

Como a configuração é bem simples, nas imagens fica bem simples o entendimento:

1. Nodes de configuração do servidor modbus tcp:
	<img src="https://github.com/dedynobre/comunicacao-modbus-tcp-com-node-red/blob/master/images/nodered-com-03.jpg"/></br>

2. Menu de configuração no node Modbus Server:</br>
	<img src="https://github.com/dedynobre/comunicacao-modbus-tcp-com-node-red/blob/master/images/nodered-com-02.jpg"/></br>
	
3. Nodes de escrita em determinado registro:
	<img src="https://github.com/dedynobre/comunicacao-modbus-tcp-com-node-red/blob/master/images/nodered-com-04.jpg"/></br>
	
	+ O primeiro node(inject) está executando uma rotina a cada 2 segundos.
	+ O segundo node(random) gera valores aleatórios dentro de um faixa configurado na sua interface e tem sua saída no parâmetro *msg.payload* conforme as configurações abaixo:</br>
		<img src="https://github.com/dedynobre/comunicacao-modbus-tcp-com-node-red/blob/master/images/nodered-com-05.jpg"/></br>
	+ O terceiro é o node que *lê/escreve* os valores nos registros no servidor modbus tcp, que no nosso caso é escrita:
		+ **Server**: define o servidor modbus tcp que vamos usar para escrever/ler valores.
		+ **FC**: é o modo de operação que o node irá funcionar, por exemplo, ler/escrever, no nosso caso escrita.
		+ **Address**: é o endereço modbus tcp.</br>
		<img src="https://github.com/dedynobre/comunicacao-modbus-tcp-com-node-red/blob/master/images/nodered-com-06.jpg"/></br>
		

## Configuração Cliente

As configurações dos nodes no Node-Red Cliente é bem mais simples comparando com as configuraçoes do servidor.
No lado cliente vamos precisar somente instânciar o servidor Modbus e configurar qual registro será lido.

1. Nodes de leitura do registro modbus tcp:</br>
	<img src="https://github.com/dedynobre/comunicacao-modbus-tcp-com-node-red/blob/master/images/nodered-com-07.jpg"/></br>
	
	+ O primeiro *node* contém as informações de configuração da comunicação modbus:
	<img src="https://github.com/dedynobre/comunicacao-modbus-tcp-com-node-red/blob/master/images/nodered-com-08.jpg"/></br>
		+ **FC**: é o modo de operação que o node irá funcionar, por exemplo, ler/escrever, no nosso caso leitura.
		+ **Address**: é o endereço modbus tcp.</br>
		+ **Quantity**: quantidade de registros para leitura, nosso caso sera 01.
		+ **Pool Rate**: tempo entre leituras.
		+ **Server**: configuração o servidor modbus, que deve ser conforme configuração anterior:</br>
			<img src="https://github.com/dedynobre/comunicacao-modbus-tcp-com-node-red/blob/master/images/nodered-com-09.jpg"/></br>
	
	+ O segundo node(debub) tem a função de mostrar o resultado de uma operação anterior. Neste caso ele está retornando *msg.payload*.
	
	
## Conclusão

Este teste é bem simples mas o principal objetivo foi demonstrar a capacidade que Node-Red tem de se comunicar via Modbus. No nosso caso foi usando o Modbus TCP mas tendo também a capacidade de
se comunicar via Modbus Serial.
Fica claro também que além de ser um cliente Modbus ele pode trabalhar também como um servidor Modbus o que pode tornar sua aplicabilidade muita mais interessante.


## Help

Caso precisem te ajuda ou tenham alguma sugestão, deixe seu comentário [Aqui](https://github.com/dedynobre/comunicacao-modbus-tcp-com-node-red/issues).
