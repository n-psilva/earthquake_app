# Earthquake Watch

### _Aplicativo que permite ao usuários procurar por terremotos_

Esse projeto faz parte da 2ª temporada do Mini Beginner's Crash Course para Elasticsearch e Kibana, orientado pela Senior Developer Advocate [Lisa Jung](https://dev.to/lisahjung).

Deixo aqui o link do guia para quem desejar acessar e aprender:
https://dev.to/lisahjung/beginners-guide-to-building-a-full-stack-app-nodejs-react-with-elasticsearch-5347

> Obs: o link também contém toda a arquitetura detalhada, incluindo fotos e gifs para melhor entendimento.

#### Arquitetura
O aplicativo web full stack está usando Node.js com Express(server), React(client) e Elastic Cloud conectado ao servidor.

Assim que o servidor estiver conectado ao Elastic Cloud, ingeriremos dados no Elasticsearch hospedado no Elastic Cloud.
Após ingerir dados globais de terremotos da API do [USGS](https://earthquake.usgs.gov/earthquakes/feed/v1.0/geojson.php) dos últimos 30 dias, o servidor enviará os dados para o Elasticsearch. O Elasticsearch, por sua vez, transformará os dados e os salvará em um índice.

O cliente exibirá um conjunto de critérios que um usuário pode selecionar para procurar terremotos.

Depois que o usuário selecionar os critérios e clicar no botão de pesquisa, o cliente enviará a entrada do usuário para o servidor. O servidor, por sua vez, passará a entrada do usuário para uma solicitação do Elasticsearch e enviará a solicitação para o Elasticsearch.

Ao receber a solicitação, o Elasticsearch recuperará resultados relevantes e enviará os resultados para o servidor. O servidor enviará os resultados para o cliente, que exibirá os resultados para o usuário na forma de cartões contendo informações detalhadas sobre cada terremoto.

Por fim, utilizamos o Elastic Cloud para explorar ainda mais nossos dados usando o Kibana para visualizar dados de terremotos no Elasticsearch e como criar essas visualizações usando o Kibana Lens!