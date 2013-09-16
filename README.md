responsive-rem
=============

__Simple website using REM unit.__

Por que?
-------------

É uma unidade relativa, não absoluta(como o pixel). Permite que o site seja redimensionado ou seja aplicado zoom sem "quebrar o layout".

Exibição do site melhorada. Acessibilidade melhorada.

Você pode usar o rem para definir largura, altura, padding, margin...

Como Funciona
-------------

Todo browser tem um tamanho de fonte predefinido. Normalmente este tamanho é 16px.

Direfente da unidade EM, o REM tem como referência a fonte do elemento Root, no caso a tag HTML.

No HTML, 16px == 1em.

Logo, se quero definir que meu site tenha 1000px de largura, posso dizer também que meu site tem 62.500rem de largura.

__Agora começa a mágica__

Como a largura do site está relativa a fonte padrão do browser(16px), se eu aumentar o zoom do browser para 150%, a fonte padrão será 24px e logo a largura do site será 41.667rem.

Eu posso dizer que meu h1 terá 1rem de margem em baixo. Se o zoom tiver em 100%, teremos 16px de margin, mas se o zoom tiver em 50%, teremos 8px de margem.

__Na media querie também__

Suponha que eu faça uma media queria para pegar todas as larguras acima de 1024px. Ficaria assim usando REM:

```
@media only screen and (min-width : 64rem) {
  /* Aqui entra o código para telas acima de 1024px caso a fonte padrão seja 16px(Vamos considerar que sempre é) */
}
```

__E se eu setar um tamanho de fonte para uma div?__

Antes de explicar como funciona o REM, veja como funciona o EM:

Se em um determinado ponto você "dizer" no seu CSS que a fonte de um tal elemento tem 20px, a partir dai(do elemento que você setou para dentro), 20px é 1em.

Logo, se no elemento citado acima, ou para qualquer elemento dentro dele você "dizer" que que tem 0.25em de padding, assumesse que ele terá 5px de padding.

Mas para o REM isso não se aplica, entenda:

Isso porque a unidade REM não tem como referência o tamanho da fonte do elemento pai, mas sim, sempre do elemento root(html).


Truque para facilitar a conversão de PX para REM
-----------------------------------------------

Podemos criar uma regra css para o body e dizer que a fonte terá 62.5% do tamanho original. Ou seja, 62.5% de 16px é 10px.

Daqui pra frente, usando este truque, podemos assumir que 10px é igual a 1rem. Ficou mais claro né?

125px == 12.5rem
98px == 9.8rem
e por ai vai

Outras considerações
--------------------

Nos códigos deste repositório você encontra o REM aplicado em vários lugares, baixe e estude.

Usei o reset do Erik Meyer, mas não é necessário para entender o funcionamento do REM.

Também usei um background em SVG, você também não precisa dele pra entender o EM.

Você pode usar um conversor online de PX para REM, existe vários, eu uso normalmente o http://offroadcode.com/prototypes/rem-calculator/.

Para ver funcionando agora
--------------------------

Acesse http://cssdesk.com/MFDGS