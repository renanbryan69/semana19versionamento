# semana20versionamento


PERGUNTAS
1. Quem é o Produtor no seu fluxograma e qual evento ele publica?
R: O Produtor é o Serviço de Pedidos. Ele é responsável por enviar para o Kafka o evento chamado PedidoCriado, sempre que uma nova compra é realizada.

2. Qual é a função do Kafka nesse fluxo?
R: O Kafka funciona como um intermediário, chamado Broker. Ele recebe os eventos enviados pelo produtor e deixa esses eventos disponíveis para os outros serviços que precisam consumi-los.

3. Por que o serviço de Pedidos não precisa esperar o serviço de Notificação terminar?
R: Porque os serviços funcionam de forma independente. O Serviço de Pedidos apenas envia o evento para o Kafka, enquanto o serviço de Notificação pode ler esse evento depois, sem atrasar o processo do pedido.

4. Em qual parte do seu fluxograma ocorre o streaming?
R: O streaming acontece no tópico Pedidos, pois os eventos vão chegando continuamente, como Pedido 1 Criado, Pedido 2 Criado e assim por diante.

5. Em qual parte aparece o reprocessamento?
R: O reprocessamento aparece quando é necessário acessar novamente eventos antigos que ficaram armazenados no tópico para serem processados outra vez.

6. Se o serviço de Notificação ficar fora do ar por alguns minutos, o que pode acontecer com as mensagens?
R: Os eventos continuam armazenados no Kafka durante o período configurado. Quando o serviço de Notificação voltar a funcionar, ele poderá consumir as mensagens que perdeu.

7. Qual vantagem existe em manter um histórico dos eventos no Kafka?
R: Manter um histórico permite consultar eventos antigos e utilizá-los novamente caso seja necessário. Isso facilita a recuperação de informações e o reprocessamento dos dados.
