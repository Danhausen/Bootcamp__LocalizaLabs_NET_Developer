# Internet das coisas
Requisitos básicos:
- Cloud computing
- Protocolo de comunicação de rede
- Processamento e armazenamento de dados

## Introdução

A internet é uma rede mundial que conecta pessoas
A IoT é a utilização da rede mundial da internet para conectar coisas. Utiliza a nuvem para armazenar e processar os dados coletados. A inteligencia é o processo de utilizar todos estes dados para ter vantagem competitiva e resolver problemas.

Por que conectar as coisas?
- Embutir sensores em objetos do dia a dia
- Coletar dados dos sensores
- Usar o dado para tomar decisões

Nasceu com o RFID em cadeias de distribuição.
RFID é uma etiqueta eletronica para armazenar e coletar dados.

Desafios do IoT:
- Privacidade e Segurança
- Quantidade exponencial de dispositivos conectadas na rede
- Ser capaz de processar e armazenas uma enorme quantidade de informações
- Gerar valor a partir dos dados coletados

## Arquitetura da Internet das Coisas

Devemos considerar alguns atributos na escolha dos dispositivos:
- Baixo consumo de energia
- Rede de dados limitado. Devemos pensar que a rede ao qual o objeto será inserido é de baixa qualidade.
- Resiliencia. É necessario que o dispositivo lide com os problemas para continuar funcionando.
- Segurança. Quais são as camadas de segurança que preciso me preocupar?
- Customização. É importante que os dispositivos possibilitem customização para adaptar aos diversos ambientes
- Baixo custo. 

Exemplos de plataformas para utilizar em IoT:
- Arduino. É uma plataforma de prototipagem que executa alguma atividade simples. Não possui conexão com a web mas permite a utilização dos Shields que são dispositivos que agregam valor ao Arduino.
- Embarcados (MCUs). Utilizado em cenários que precisam da garantia da coleta e processamento dos dados. É um microcontrolador de chip único. É possível adicionar sistema operacional, e é importante que seja real time que integra com o hardware.
- Minicomputadores (Raspberry Pi). É um computador completo, é um hardware integrado em uma única placa. Roda Linux ou Windows.


## Melhores práticas

É importante que aja um protocolo de comunicação que se comunique entre qualquer tipo de dispositivo.
**MQTT**, Message Queue Telemetric Transport, é o protocolo mais utilizado em IoT para comunicar entre o dispositivo e a nuvem.
MQTT foi criado pela IBM e é um protocolo de mensagens assíncronas (M2M). Foi criado pela IBM para conectar sensores de pipelines de petróleo a satélites, eles queriam coletar dados de toda a cadeia do petróleo e enviar à núvem. Virou um padrão OASIS suportado pelas linguagens de programação mais populares.

### Flexibilidade dos tópicos

Cada acesso ao sistema, através do MQTT, possui um registro único, e para acessar os dados mais atualizados e obter as informações, o requisitante deve se inscrever no MQTT Broker para receber as públicações.

QoS0, é um protocolo de comunicação fornecido pelo MQTT. Serve para verificar níveis diferentes de qualidade de serviço (QoS0 nível 0, QoS1 nível 1, QoS2 nível 2):
- QoS0 nível 0. Não há garantia nenhuma que a mensagem foi entregue. A mensagem também não é armazenada para que seja retransmitida. Nível de menor esforço.
- QoS0 nível 1. Fornece garantia que a mensagem foi entregue. Armazena a mensagem. Pode retransmitir a mensagem quando não obtem confirmação de entrega.
- QoS0 nível 2. Possui mesmos recursos que o de nível 1, mas de forma mais eficiente. O cliente se comunica com o broker para saber se a mensagem ja foi entrega e com isso facilita o gerenciamento do broker para armazenar ou não a mensagem.

