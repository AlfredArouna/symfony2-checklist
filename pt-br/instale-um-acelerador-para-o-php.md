Instale um acelerador para o PHP
performance
Symfony2 � um framework flex�vel e poderoso... que, obviamente, acaba aumentando relativamente o tempo de execu��o. � claro que, o ambiente de produ��o � muito mais r�pido que o seu ambiente de desenvolvimento de costume, mas isso n�o � o suficiente.

Com a inten��o de aumentar a velocidade de sua aplica��o em produ��o, � _muito recomendado_ instalar um Acelerador para o PHP como o APC.

### Em um servidor dedicado

#### Plataforma Linux
Para instalar o APC em uma distribui��o linux baseada em debian, execute:

    apt-get install php-apc

Adapte o comando para a sua distrui��o.

#### Plataforma Windows
Descomente a linha a baixo em seu `php.ini`:

    extension=php_apc.dll

#### Em todos os casos
Depois da instala��o, voc� deve habilitar o uso da extens�o. Isto � feito adicionando a linha a baixo em seu `php.ini`:

    [APC]
    apc.enabled=1

### Em um host compartilhado
Se voc� est� em um host compartilhado, voc� pode n�o ter acesso SSH. Neste caso, a melhor op��o � contatar o administrador da sua hospedagem. Diga para ele que � melhor para o seus servidores rodar com um Acelerador PHP.

* _Veja [APC na documenta��o do PHP](http://php.net/manual/en/book.apc.php)_