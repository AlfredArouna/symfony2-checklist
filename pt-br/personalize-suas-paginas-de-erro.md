Customize suas p�ginas de erro
b�sico
Se voc� usa as p�ginas de erro em seu ambiente de desenvolvimento, isto n�o �, felizmente, o que os seus visitantes devem ver em caso de erro no seu ambiente de produ��o. Ent�o, voc� deve customizar diferentes p�ginas de erro, afim de integrar estes ao seu layout.

Felizmente, a customiza��o das p�ginas de erro � realmente f�cil. As "views" s�o localizadas dentro do componente `TwigBundle`, que lhe d� a possibilidade para substitu�-los pelos seus. As p�ginas que voc� precisa criar s�o: `Exception/errorXXX.html.twig`, onde `XXX` � o n�mero do erro ocorrido. � altamente recomendado personalizar ao menos as p�ginas para os erros 404 e 500.

Para usar as suas pr�prias p�ginas, existe duas possibilidades:

1. Voc� pode criar um novo bundle(componente), que estender� de `TwigBundle`, e colocar os seus arquivos em `Resources/views/Exception/errorXXX.html.twig`. Isso permite que voc� possa reutiliz�-lo em diferentes projetos, pois � um componente reutiliz�vel;
2. Voc� tamb�m pode adicionar as suas p�ginas no diret�rio `app/Resources/TwigBundle/views/Exception/errorXXX.html.twig`. Se as suas p�ginas de erros s�o espec�ficas para o seu projeto, isso evita que voc� crie um novo bundle apenas para isto.

* _Veja [Customize error pages on Symfony documentation](http://symfony.com/doc/master/cookbook/controller/error_pages.html)_