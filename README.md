## Teste de Comunicação Modbus TCP entre duas instâncias do NodeRed


## Objetivo

O presente teste tem o objetivo de documentar os testes de comunicação do seguinte *node* [Modbus](https://flows.nodered.org/node/node-red-contrib-modbus).

## Desenvolvimento

Basicamente os teste e configuração irá seguir a seguinte estrutura:
<img src="https://github.com/dedynobre/comunicacao-modbus-tcp-com-node-red/blob/master/images/nodered-com-01.jpg"/></br>


### Configuração Servidor

Como a configuração é bem simples, nas imagens fica bem simples o entendimento:

Para importar no NodeRed(caso queiram testar):
```
[{"id":"a88c0232.0afee","type":"inject","z":"2cb15f5b.37a73","name":"","topic":"","payload":"","payloadType":"date","repeat":"","crontab":"","once":false,"onceDelay":0.1,"x":200,"y":100,"wires":[["6333ed6a.3722a4"]]},{"id":"6333ed6a.3722a4","type":"modbus-server","z":"2cb15f5b.37a73","name":"Note-Modbus","logEnabled":false,"hostname":"192.168.0.1","serverPort":"502","responseDelay":100,"delayUnit":"ms","coilsBufferSize":10000,"holdingBufferSize":10000,"inputBufferSize":10000,"discreteBufferSize":10000,"showErrors":false,"x":480,"y":100,"wires":[["4acf94c6.22685c"],["44f37aee.f14f84"],["be800b.cfec8ff8"],["2add1125.dd8b0e"]]},{"id":"4acf94c6.22685c","type":"debug","z":"2cb15f5b.37a73","name":"","active":true,"tosidebar":true,"console":false,"tostatus":false,"complete":"false","x":710,"y":40,"wires":[]},{"id":"44f37aee.f14f84","type":"debug","z":"2cb15f5b.37a73","name":"","active":true,"tosidebar":true,"console":false,"tostatus":false,"complete":"false","x":710,"y":80,"wires":[]},{"id":"be800b.cfec8ff8","type":"debug","z":"2cb15f5b.37a73","name":"","active":true,"tosidebar":true,"console":false,"tostatus":false,"complete":"false","x":710,"y":120,"wires":[]},{"id":"2add1125.dd8b0e","type":"debug","z":"2cb15f5b.37a73","name":"","active":true,"tosidebar":true,"console":false,"tostatus":false,"complete":"false","x":710,"y":160,"wires":[]}]
```

Nodes de configuração do servidor modbus tcp:
<img src="https://github.com/dedynobre/comunicacao-modbus-tcp-com-node-red/blob/master/images/nodered-com-03.jpg"/></br>

Menu de configuração no node Modbus Server;
<img src="https://github.com/dedynobre/comunicacao-modbus-tcp-com-node-red/blob/master/images/nodered-com-02.jpg"/></br>
