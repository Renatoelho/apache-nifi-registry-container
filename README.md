# Crie seu servidor Apache NiFi integrado com Nifi Registry utilizando o Docker-compose

O ***Apache NiFi*** é uma ferramenta de processamento de fluxo de dados que permite a transferência, manipulação e processamento de dados em tempo real de várias fontes para diversos destinos. O ***NiFi Registry***, por sua vez, é uma ferramenta que permite gerenciar versões de fluxos de dados criados no NiFi.

Ambas as ferramentas podem ser executadas como serviços em um ambiente ***Docker*** usando o docker-compose. Isso significa que você pode criar um arquivo docker-compose.yml para definir os serviços do NiFi e NiFi Registry, além de especificar como eles se comunicam e como serão executados.

Ao usar o docker-compose, você pode facilmente configurar e implantar esses serviços, incluindo a definição de opções de configuração, como portas, volumes de dados e opções de rede. Além disso, o docker-compose permite que você personalize a configuração do ***healthcheck*** para monitorar a integridade desses serviços.

Em resumo, executar o Apache NiFi e NiFi Registry no docker-compose permite que você implante facilmente essas ferramentas em um ambiente de contêineres e personalizar sua configuração para atender às suas necessidades específicas.


# Requisitos

Docker 23.0.3 (Host)

Docker-Compose 1.25.0 (Host)


# Ativando os serviços do Apache Nifi e Nifi Registry

Temos neste repositório um arquivo ***docker-compose.yml*** com todas as configurações de integração do Apache NiFi e NiFi Registry, prontos para serem executados e utilizados imediatamente.


#### Ativando os serviços

```bash
docker-compose -f docker-compose.yaml --compatibility up -d
```

> ***IMPORTANTE:*** No primeiro start dos serviços, pode ocorrer um erro no serviço 'nifi-registry' se a permissão de acesso ao volume criado for negada. Nesse caso, desative os serviços e ***altere as permissões do volume***. Use o comando '***sudo chmod -R 777 nifi_registry/***' e, em seguida, suba novamente os serviços. Tudo deve funcionar corretamente.


#### Desativando os serviços

```bash
docker-compose -f docker-compose.yaml --compatibility down
```

# Referências:

Apache/Nifi, ***Docker Hub***. Disponível em: <https://hub.docker.com/r/apache/nifi>. Acesso em: 19 abr. 2023.

NiFi System Administrator’s Guide, ***Apache NiFi***. Disponível em: <https://nifi.apache.org/docs/nifi-docs/html/administration-guide.html>. Acesso em: 22 abr. 2023.

apache/nifi-registry, ***Docker Hub***. Disponível em: <https://hub.docker.com/r/apache/nifi-registry>. Acesso em: 22 abr. 2023.

Getting Started with Apache NiFi Registry, ***Apache NiFi Registry***. Disponível em: <https://nifi.apache.org/docs/nifi-registry-docs/index.html>. Acesso em: 22 abr. 2023.

How to build a data lake from scratch - Part 1: The setup, ***Victor Seifert***. Disponível em: <https://towardsdatascience.com/how-to-build-a-data-lake-from-scratch-part-1-the-setup-34ea1665a06e>. acesso em: 19 abr. 2023.