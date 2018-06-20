# Instalação do RabbitMq no Ubuntu

É necessário atualizar os pacotes e bibliotecas do Ubuntu

`sudo apt-get update && sudo apt-get upgrade`

Após isso, entrar como administrador com o seguinte comando:

`sudo su`

Antes de instalar o RabbitMq, instalar o Erlang:

`apt-get install erlang`

Após isso, agora sim podemos instalar o RabbitMq com o seguinte comando:

`apt-get install rabbitmq-server`

Depois, iremos habilitar o RabbitMq na máquina:

`systemctl enable rabbitmq-server`

E o iniciamos:

`systemctl start rabbitmq-server`

Para verificar se o RabbitMq está de pé, executar o seguinte comando:

`systemctl status rabbitmq-server`

Agora iremos habilitar o plugin de gerenciamento do RabbitMq: 

`rabbitmq-plugins enable rabbitmq_management`

E criamos o nosso usuário e senha de acesso:

`rabbitmqctl add_user <USUARIO> <SENHA>`

Iremos inserir ao grupo de administrador o nosso usuário:

`rabbitmqctl set_user_tags <USUARIO> administrator`

E enfim concederemos as permissões de administrador ao nosso usuário

`rabbitmqctl set_permissions -p / <USUARIO> ".*" ".*" ".*"`