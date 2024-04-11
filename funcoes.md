# Funções
Em geral podemos dizer que todo o código utiliza o conceito de programação funcional, vamos então conhecer os arquivos de funções e as principais funções contidas dentro deles.

## configWifi
Arquivo que contém todas as funções necessárias para a configuração da rede WiFi. Este é um **arquivo muito importante para o projeto** pois é quem faz todas as verificações se existe ou não uma rede salva por exemplo, além de criar o servidor web da interface, e realiza todas as configurações MQTT  

```bool iniciarWiFi()```  

Função responsável por configurar a rede WiFi, basicamente verifica se já existe alguma rede salva na memória SPIFFS caso contrário cria um servidor Web que permite configurar desde as credenciais a até mesmo configurações para conexão com o Broker MQTT. 

 ```void resetarWifi()```  

 Função simples que quando chamada reseta as configurações WiFi no SPIFFS, dessa forma na próxima chamada a função `iniciar wifi()` não haverá nada salvo no SPIFFS, assim a interface web será criada e o usuário poderá redefinir as suas credenciais. No caso deste hardware em especifico essa função é chamada sempre que o usuário pressiona o botão reset por 5 segundos na placa.  

 ## configMqtt
 Este é um outro arquivo de funções extremamente importante para o projeto, aqui estão as funções que permitem as configurações MQTT como IP do broker, todas as questões de conexão e reconexão e todos os tópicos necessários para a comunicação MQTT do projeto. 

 ### Funções responsáveis pela comunicação MQTT

```void publicaTensaoBat()```
Função que publica no tópico respectivo a tensão (em volts) da bateria.  
```void publicaPorcentBat()```
Função que publica no tópico respectivo qual a porcentagem da bateria.
**Importante:** Ambas as funções relacionadas a bateria dependem de uma chamada a `leituraPinoBateria();` e assim teremos um valor analógico que representa a tensão mensurada na bateria.  
```void publicaTensaoPlaca()```
Função que publica qual a tensão gerada pela placa no momento mensurado. Utiliza a função `tensaoPlacaSolar()` para obter este valor.