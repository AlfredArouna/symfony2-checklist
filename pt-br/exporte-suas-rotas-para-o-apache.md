Exporte suas Rotas para o Apache
performance
Voc� pode aumentar a velocidade da sua aplica��o deixando o Apache manipular sua p�gina diretamente, no lugar de usar o componente Symfony2 Router. Aqui est�o os dois passos.

### 1. Exporte suas rotas para o Apache
Symfony2 possui um comando que exporta todas as suas rotas em um formato compreens�vel pelo modulo mod_rewrite do Apache:

    php app/console router:dump-apache -e=prod --no-debug

E ent�o adicione esses regras de rewrite para o arquivo `web/.htaccess`, ou diretamente no diret�rio de configura��o em seu `httpd.conf`, voc� quem decide.

    RewriteEngine On
    # E aqui adicione o resultado do comando anterior

E claro, esteja certo que o modulo mod_rewrite est� ativo na configura��o do Apache.

### 2. Diga para o router que voc� est� usando Apache
Agora voc� precisa dizer ao Symfony2 que voc� quer usar outro Matcher que n�o seja o padr�o. Adicione isto ao seu `config_prod.yml`:

    parameters:
        router.options.matcher.cache_class: ~ # disable router cache
        router.options.matcher_class: Symfony\Component\Routing\Matcher\ApacheUrlMatcher

� isso!

* _Veja [Symfony2 Apache Router documentation](http://symfony.com/doc/current/cookbook/configuration/apache_router.html)_
* _Veja [Apache mod_rewrite documentation](http://httpd.apache.org/docs/current/rewrite)_