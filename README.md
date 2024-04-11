# Sensor de Irrigação
## :mag_right: Conhecendo o Projeto
Este projeto consiste em um simples sensor de Irrigação utilizando o microcontrolador ESP32. A placa desenvolvida permite a conexão de até 4 sensores capacitivos do solo, uma bateria 18650 é responsável por alimentar toda a placa, e uma placa solar de 5V/1w mantém a bateria carregada.  
### Comunicação
O projeto é capaz de se conectar a internet utilizando uma rede WiFi. Já a comunicação é realizada utilizando o protocolo MQTT, onde a placa envia os dados coletados a cada período de tempo. Os dados são enviados para ao node-red via MQTT, e este fica encarregado de tomar as decisões sobre os dados. O objetivo é que as configurações de WiFi, Mqtt e até mesmo a frequência em que os dados são enviados para o broker sejam configuráveis através de uma interface amigável.

### Dados coletados e enviados.

* **Umidade do Solo:** obtida utilizando sensores capacitivo de umidade do solo
* **Umidade do Ambeiente:** foi utilizado um sensor DHT11
* **Temperatura do Ambiente:** também coletada pelo DHT11
* **Tensão da Bateria:** Mensurada atrávés de um divisor resistivo
* **Porcentagem da Bateria** é baseada na tensão da bateria
* **Tensão da Placa Solar** também utiliza um divisor resistivo

## :wrench: Status de Desenvolvimento

- Status do Projeto: Em desenvolvimento :warning:
- Versão de lançamento: <img src = "https://img.shields.io/static/v1?label=vers%C3%A3o_lan%C3%A7amento&message=v0.1&color=blue&style=for-the-plastic"/>
- Versão atual: <img src="https://img.shields.io/static/v1?label=vers%C3%A3o&message=v0.1&color=blue&style=for-the-plastic"/>

### Objetivos de desenvolvimento:
- [X] Desenvolver um hardware que suporte o projeto
- [X] Possibilidade de coletar a umidade do solo
- [X] Possibilidade de coletar a temperatura e umidade do ambiente
- [X] Possibilidade de monitorar o status da bateria e placa solar
- [ ] A placa se mantém apenas com o conjunto bateria e placa solar
- [ ] Toda a solução deve ser configurável por uma interface amigável
- [X] Possibilidade de configuração do WiFi através de uma interface Web.  
- [X] Possibilidade de configurar o Host do broker MQTT e sua porta através de uma interface Web.
- [ ] Possibilidade de configurar as credenciais do broker MQTT através de uma interface web.
- [ ] Possibilidade de definir todos os tópicos MQTT através de uma interface web.
- [ ] A solução é capaz de buscar e efetuar atualizações de forma autônoma
- [ ] Desenvolver uma versão utilizando rádio LoRa, visando o longo alcance
