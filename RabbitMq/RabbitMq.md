
O RabbitMQ é um aplicativo de mensageria que atua como Message-Broker, sendo um dos sistemas mais utilizados nos dias de hoje. 
Ele atua como intermediário na gestão de envios e recebimentos de mensagens de uma ou mais aplicações, com o objetivo de lidar com o tráfego de mensagens o mais rápido possível.
O modo de funcionamento é bem simples. Conta com um servidor que é desenvolvido na linguagem "ERLANG", e de outro lado, as bibliotecas que implementam a interface de uso do Message-Broker. RabbitMQ foi desenvolvido para suportar o tráfego de mensagens usando o protocolo AMQP - Protocolo Avançado de Enfileiramento de Mensagens. Isso significa que, quando enviamos a mensagem, não receberemos resposta imediata, a mensagem será encaminhada para uma fila e será entregue para o consumidor assim que necessária.

## Estrutura da Mensagem no RabbitMQ
A mensagem é dividida em duas partes:
- Label: É o rótulo da mensagem. Através do label, o RabbitMQ conecta o produtor e o consumidor da mensagem.
- Payload: É o conteúdo da mensagem.

## Elementos Fundamentais no RabbitMQ
Existem 3 elementos que têm papel fundamental nas mensagens dentro do RabbitMQ:
- Binding: Responsável pela ligação entre a Exchange e a fila.
- BindingKey: Chave do binding, funcionando como uma ID para identificar a ligação.
- RoutingKey: É uma chave enviada junto com a mensagem. A Exchange usa essa chave para definir para qual fila a mensagem será enviada.

## Exchanges
Dentro do ambiente RabbitMQ, o produtor não encaminha a mensagem diretamente para a fila. Antes disso, a mensagem passa pela Exchange, que é quem encaminha cada mensagem para sua fila correta. Existem 4 tipos de **Exchange**:
- Direct: Encaminha a mensagem para a fila com base na chave de roteamento exata.
- Topic: Encaminha a mensagem com base em padrões na chave de roteamento.
- Fanout: Encaminha a mensagem para todas as filas ligadas a ela, independentemente da chave de roteamento.
- Headers: Encaminha a mensagem com base em atributos do cabeçalho em vez da chave de roteamento.


## Descrição das Etapas
- Produtor: Envia uma mensagem para uma Exchange específica no RabbitMQ (Direct, Fanout, topic ou Headers).
- Exchange: Recebe a mensagem, e dependendo do tipo de exchange e das regras de binding, envia a mensagem para uma fila.
- Filas (Queues): Armazenam as mensagens até que sejam consumidas.
- Consumidor: Recebe as mensagens das filas.
