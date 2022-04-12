Essa e a API que conecta o Zabbix no PowerBI.

Você poderá ver diversos blogs na comunidade, porém, alguns deles não funciona.

Ao Abrir o PowerBI, vai em Página Inicial/Transformar dados/Transformar dados

Segue a estrutura abaixo.

3 - Parametros

Primeiro crie um usuário de aplicação no zabbix.

- User = nome do usuário
- Password = senha do usuario
- ZabbixUL = Aqui você irá colocar seu IP ou DNSNAME ex:http://1.1.1.1/api_jsonrpc.php

1 Função

GetZabbixToken e uma "senha" que e gerada a cada interação do powerbi com o zabbix, sem esse token, você não fecha a conexão.

- GetZabbixToken - Pode deixar em branco, se não irá gerar um token em toda interação, e com isso teria que atualizar manualmente. Deixando em branco, iremos aproveitar a função para quando formos fazer a consulta gere e armazene o token automaticamente.

3 - Consultas

ZabbixUsers 
ZabbixEvents
ZabbixInventory

Para editar a consulta, selecione uma delas e clique botão direito/Editor avançado.

Como falei acima, esse paramentro aqui token = GetZabbixToken(User, Password, ZabbixURL) ele puxa a função do token.
Esse comando ""auth"": """ & token & """, ele salva o token, com isso, sempre que o powerbi gerar um token a consulta, gera e armazena automaticamente.


Obs: O Projeto ainda estou desenvolvendo, pois a API está funcionando perfeitamente, porém ainda não consegui fazer o agendamento de atualização funcionar, pois o problema está no corpo da consulta. Quando conseguir atualizo.