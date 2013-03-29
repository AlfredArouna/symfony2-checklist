Utilize o Cache do Doctrine
performance
No ambiente de produ��o, � _altamente recomendado_ utilizar o cache do Doctrine. Aqui est�o dois tipos de cache.

### Query e Metadata Cache
* A Query Cache visa o cacheamento da transforma��o de DQL query para o SQL. Em produ��o, as suas requisi��es n�o ir�o mudar, ent�o porque n�o fazer o cache.
* A Metadata Cache permite o cacheamento das informa��es de metadata vindas de diferentes formatos como YAML, XML, Annotations, etc.

O cache dessas informa��es � feito definindo alguns param�tros no arquivo de configura��o `config_prod.yml`:

    doctrine:
        orm:
            auto_mapping: true
                query_cache_driver:    apc
                metadata_cache_driver: apc

### Result Cache
O resultado das suas queries podem ser armazenadas em cache para que a consulta n�o seja executada no banco de dados v�rias vezes. Como isso � um ajuste mais delicado, voc� n�o consegue apenas alterar um param�tro em sua aplica��o. Voc� apenas precisa setar o driver como anteriormente:

    doctrine:
        orm:
            auto_mapping: true
                result_cache_driver: apc

Mas voc� precisa tornar explicito o uso ou n�o desse cache na maioria de suas queries. Isto � feito setando o nome e o tempo de vida de cada querie. Veja [Doctrine Result Cache documentation](http://docs.doctrine-project.org/projects/doctrine-orm/en/latest/reference/caching.html#result-cache).

* _Veja [Doctrine Cache documentation](http://docs.doctrine-project.org/projects/doctrine-orm/en/latest/reference/caching.html)_
* _Veja [Symfony2 Doctrine configuration reference](http://symfony.com/doc/current/reference/configuration/doctrine.html)_