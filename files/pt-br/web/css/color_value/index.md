---
title: <color>
slug: Web/CSS/color_value
tags:
  - CSS
  - Layout
  - Referencia
  - Tipo de dado CSS
  - Web
translation_of: Web/CSS/color_value
---
<div>{{CSSRef}}</div>

<h2 id="Sumário">Sumário</h2>

<p>O tipo de dado <a href="/en-US/docs/Web/CSS">CSS</a> <code>&lt;color&gt;</code> indica uma <a class="external" href="https://en.wikipedia.org/wiki/SRGB">cor no espaço sRGB</a>. Uma cor pode ser descrita em qualquer uma destas formas:</p>

<ul>
 <li>usando uma <em>palavra-chave</em></li>
 <li>usando o sistema de <a class="external" href="https://en.wikipedia.org/wiki/RGB_color_model#Geometric_representation">coordenada-cúbica RGB</a>  (via #-hexadecimal ou das notações funcional <code>rgb()</code> e <code>rgba()</code>)</li>
 <li>usando o sistema de <a class="external" href="https://en.wikipedia.org/wiki/HSL_and_HSV">coordenada-cilíndrica HSL</a> (via <code>hsl()</code> e notações funcionais <code>hsla()</code> )</li>
</ul>

<p>Observe que a lista de valores de cores aceitas foi estendida à medida que a especificação evoluiu, culminando com as cores CSS3 mais recentes.</p>

<p>Associado à cor no espaço sRGB, um valor &lt;color&gt; também pode consistir de uma coordenada de <em>valor de transparência</em> <a class="external" href="https://en.wikipedia.org/wiki/Alpha_compositing">canal-alfa</a>, Indicando como a cor deve se <a class="external" href="https://www.w3.org/TR/2003/REC-SVG11-20030114/masking.html#SimpleAlphaBlending">composta</a> com sua cor de fundo.</p>

<p>Embora os valores de cores CSS sejam definidos com precisão, eles podem aparecer de forma diferente em dispositivos de saída diferentes. A maioria deles não está calibrada e alguns navegadores não suportam o <a href="https://pt.wikipedia.org/wiki/Perfil_de_cores_ICC">perfil de cores</a> dos dispositivos de saída. Sem estes, a renderização de cores pode variar muito.</p>

<div class="note"><strong>Nota:</strong> A recomendação <a class="external" href="https://www.w3.org/TR/WCAG/#visual-audio-contrast">WCAG 2.0</a> do W3C aconselha fortemente aos autores web não usarem cor como o único meio para transmitir uma mensagem específica, ação ou resultado. Alguns usuários têm problemas em distinguir cores e as informações transmitidas podem não ser compreendidas. Claro, isso não impede o uso da cor, mas o seu uso apenas como o único meio para descrever certas coisas (veja <a href="/en-US/docs/Learn/Accessibility/CSS_and_JavaScript#Color_and_color_contrast">Cor e contraste de cor</a> para mais informações).</div>

<h2 id="Interpolação">Interpolação</h2>

<p>Valores do tipo de dados CSS <code>&lt;color&gt;</code> podem ser interpolados para realizar animações ou para criar valores &lt;gradient&gt;. Nesse caso, eles são interpolados em cada um de seus componentes vermelho, verde, azul, cada um manipulado como um número real, de ponto flutuante. Observe que a interpolação de cores ocorre no <a href="https://www.gimp.org/docs/plug-in/appendix-alpha.html">espaço de cores sRGBA alfa-pré-multiplicado</a> para evitar que cores cinzentas inesperadas apareçam. Nas animações, a velocidade da interpolação é determinada pela <a href="/en-US/docs/Web/CSS/timing-function">função de temporização</a> associada à animação.</p>

<h2 id="Valores">Valores</h2>

<p>Existem várias maneiras de descrever um valor &lt;<code>color&gt;</code>.</p>

<h3 id="Palavras-chave_de_cores">Palavras-chave de cores</h3>

<p>As palavras-chave de cor são identificadores não sensíveis a maiúsculas e minúsculas que representam uma cor específica, ex.: <code>red</code>, <code>blue</code>, <code>brown</code>, ou <code>lightseagreen</code>. O nome descreve a cor, embora seja principalmente artificial. A lista de valores aceitos variou muito ao longo das diferentes especificações:</p>

<ul>
 <li>CSS nível 1 aceita apenas16 cores básicas, denominadas <em>cores VGA </em>já que foram tiradas do conjunto de cores exibíveis das placas gráficas <a class="external" href="https://pt.wikipedia.org/wiki/Video_Graphics_Array">VGA</a>.</li>
 <li>CSS nível 2 Adicionou a palavra-chave <code>orange</code>.</li>
 <li>Desde o início, os navegadores aceitaram outras cores, principalmente a lista de cores nomeadas X11 já que alguns dos primeiros navegadores foram aplicações X11, embora com algumas diferenças. O SVG 1.0 foi o primeiro padrão a definir formalmente essas palavras-chave; As cores no CSS nível 3 também formalmente definiram essas palavras-chave. Elas são muitas vezes referidas como <em>palavras-chave de cor estendida</em>, <em>cores X11</em> ou <em>cores SVG</em>.</li>
</ul>

<p>Existem algumas restrições a serem consideradas ao usar palavras-chave:</p>

<ul>
 <li>Com exceção das 16 cores básicas comuns com HTML, as outras não podem ser usadas em HTML. O HTML vai converter esses valores desconhecidos com um algoritmo específico levando a cores completamente diferentes. Essas palavras-chave só devem ser usadas em SVG &amp; CSS.</li>
 <li>Palavras-chave desconhecidas tornam a propriedade CSS inválida. Propriedades inválidas sendo ignoradas, a cor não terá efeito. Esse é um comportamento diferente do HTML.</li>
 <li>Nenhuma palavra-chave de core definida em CSS têm qualquer transparência — eles são cores simples, sólidas.</li>
 <li>Várias palavras-chave indicam as mesmas cores:
  <ul>
   <li><code>darkgray</code> / <code>darkgrey</code></li>
   <li><code>darkslategray</code> / <code>darkslategrey</code></li>
   <li><code>dimgray</code> / <code>dimgrey</code></li>
   <li><code>lightgray</code> / <code>lightgrey</code></li>
   <li><code>lightslategray</code> / <code>lightslategrey</code></li>
   <li><code>gray</code> / <code>grey</code></li>
   <li><code>slategray</code> / <code>slategrey</code></li>
  </ul>
 </li>
 <li>Embora os nomes das palavras-chave tenham sido tomadas pelos nomes de cores X11 habituais, a cor pode divergir da cor do sistema correspondente em sistemas X11 como estes são adaptados para o hardware específico pelo fabricante.</li>
</ul>

<table>
 <thead>
  <tr>
   <th scope="col">Especificação</th>
   <th scope="col">Cor</th>
   <th scope="col">Palavra-chave</th>
   <th scope="col">valores hex RGB</th>
   <th scope="col">Resultado</th>
  </tr>
 </thead>
 <tbody>
  <tr style="position: relative;">
   <td rowspan="16">{{SpecName("CSS1")}}</td>
   <td style="background: #000;"> </td>
   <td style="text-align: center;"><code>black</code></td>
   <td><code>#000000</code></td>
   <td style="background: black;"> </td>
  </tr>
  <tr>
   <td style="background: #C0C0C0;"> </td>
   <td style="text-align: center;"><code>silver</code></td>
   <td><code>#c0c0c0</code></td>
   <td style="background: silver;"> </td>
  </tr>
  <tr>
   <td style="background: #808080;"> </td>
   <td style="text-align: center;"><code>gray</code></td>
   <td><code>#808080</code></td>
   <td style="background: gray;"> </td>
  </tr>
  <tr>
   <td style="background: #FFF;"> </td>
   <td style="text-align: center;"><code>white</code></td>
   <td><code>#ffffff</code></td>
   <td style="background: white;"> </td>
  </tr>
  <tr>
   <td style="background: #800000;"> </td>
   <td style="text-align: center;"><code>maroon</code></td>
   <td><code>#800000</code></td>
   <td style="background: maroon;"> </td>
  </tr>
  <tr>
   <td style="background: #F00;"> </td>
   <td style="text-align: center;"><code>red</code></td>
   <td><code>#ff0000</code></td>
   <td style="background: red;"> </td>
  </tr>
  <tr>
   <td style="background: #800080;"> </td>
   <td style="text-align: center;"><code>purple</code></td>
   <td><code>#800080</code></td>
   <td style="background: purple;"> </td>
  </tr>
  <tr>
   <td style="background: #F0F;"> </td>
   <td style="text-align: center;"><code>fuchsia</code></td>
   <td><code>#ff00ff</code></td>
   <td style="background: fuchsia;"> </td>
  </tr>
  <tr>
   <td style="background: #008000;"> </td>
   <td style="text-align: center;"><code>green</code></td>
   <td><code>#008000</code></td>
   <td style="background: green;"> </td>
  </tr>
  <tr>
   <td style="background: #0F0;"> </td>
   <td style="text-align: center;"><code>lime</code></td>
   <td><code>#00ff00</code></td>
   <td style="background: lime;"> </td>
  </tr>
  <tr>
   <td style="background: #808000;"> </td>
   <td style="text-align: center;"><code>olive</code></td>
   <td><code>#808000</code></td>
   <td style="background: olive;"> </td>
  </tr>
  <tr>
   <td style="background: #FF0;"> </td>
   <td style="text-align: center;"><code>yellow</code></td>
   <td><code>#ffff00</code></td>
   <td style="background: yellow;"> </td>
  </tr>
  <tr>
   <td style="background: #000080;"> </td>
   <td style="text-align: center;"><code>navy</code></td>
   <td><code>#000080</code></td>
   <td style="background: navy;"> </td>
  </tr>
  <tr>
   <td style="background: #00F;"> </td>
   <td style="text-align: center;"><code>blue</code></td>
   <td><code>#0000ff</code></td>
   <td style="background: blue;"> </td>
  </tr>
  <tr>
   <td style="background: #008080;"> </td>
   <td style="text-align: center;"><code>teal</code></td>
   <td><code>#008080</code></td>
   <td style="background: teal;"> </td>
  </tr>
  <tr>
   <td style="background: #0FF;"> </td>
   <td style="text-align: center;"><code>aqua</code></td>
   <td><code>#00ffff</code></td>
   <td style="background: aqua;"> </td>
  </tr>
  <tr>
   <td>{{SpecName("CSS2.1")}}</td>
   <td style="background: #FFA500;"> </td>
   <td style="text-align: center;"><code>orange</code></td>
   <td><code>#ffa500</code></td>
   <td style="background: orange;"> </td>
  </tr>
  <tr>
   <td rowspan="129">{{SpecName("CSS3 Colors")}}</td>
   <td style="background: #f0f8ff;"> </td>
   <td style="text-align: center;"><code>aliceblue</code></td>
   <td><code>#f0f8ff</code></td>
   <td style="background: aliceblue;"> </td>
  </tr>
  <tr>
   <td style="background: #faebd7;"> </td>
   <td style="text-align: center;"><code>antiquewhite</code></td>
   <td><code>#faebd7</code></td>
   <td style="background: antiquewhite;"> </td>
  </tr>
  <tr>
   <td style="background: #7fffd4;"> </td>
   <td style="text-align: center;"><code>aquamarine</code></td>
   <td><code>#7fffd4</code></td>
   <td style="background: aquamarine;"> </td>
  </tr>
  <tr>
   <td style="background: #f0ffff;"> </td>
   <td style="text-align: center;"><code>azure</code></td>
   <td><code>#f0ffff</code></td>
   <td style="background: azure;"> </td>
  </tr>
  <tr>
   <td style="background: #f5f5dc;"> </td>
   <td style="text-align: center;"><code>beige</code></td>
   <td><code>#f5f5dc</code></td>
   <td style="background: beige;"> </td>
  </tr>
  <tr>
   <td style="background: #ffe4c4;"> </td>
   <td style="text-align: center;"><code>bisque</code></td>
   <td><code>#ffe4c4</code></td>
   <td style="background: bisque;"> </td>
  </tr>
  <tr>
   <td style="background: #ffebcd;"> </td>
   <td style="text-align: center;"><code>blanchedalmond</code></td>
   <td><code>#ffebcd</code></td>
   <td style="background: blanchedalmond;"> </td>
  </tr>
  <tr>
   <td style="background: #8a2be2;"> </td>
   <td style="text-align: center;"><code>blueviolet</code></td>
   <td><code>#8a2be2</code></td>
   <td style="background: blueviolet;"> </td>
  </tr>
  <tr>
   <td style="background: #a52a2a;"> </td>
   <td style="text-align: center;"><code>brown</code></td>
   <td><code>#a52a2a</code></td>
   <td style="background: brown;"> </td>
  </tr>
  <tr>
   <td style="background: #deb887;"> </td>
   <td style="text-align: center;"><code>burlywood</code></td>
   <td><code>#deb887</code></td>
   <td style="background: burlywood;"> </td>
  </tr>
  <tr>
   <td style="background: #5f9ea0;"> </td>
   <td style="text-align: center;"><code>cadetblue</code></td>
   <td><code>#5f9ea0</code></td>
   <td style="background: cadetblue;"> </td>
  </tr>
  <tr>
   <td style="background: #7fff00;"> </td>
   <td style="text-align: center;"><code>chartreuse</code></td>
   <td><code>#7fff00</code></td>
   <td style="background: chartreuse;"> </td>
  </tr>
  <tr>
   <td style="background: #d2691e;"> </td>
   <td style="text-align: center;"><code>chocolate</code></td>
   <td><code>#d2691e</code></td>
   <td style="background: chocolate;"> </td>
  </tr>
  <tr>
   <td style="background: #ff7f50;"> </td>
   <td style="text-align: center;"><code>coral</code></td>
   <td><code>#ff7f50</code></td>
   <td style="background: coral;"> </td>
  </tr>
  <tr>
   <td style="background: #6495ed;"> </td>
   <td style="text-align: center;"><code>cornflowerblue</code></td>
   <td><code>#6495ed</code></td>
   <td style="background: cornflowerblue;"> </td>
  </tr>
  <tr>
   <td style="background: #fff8dc;"> </td>
   <td style="text-align: center;"><code>cornsilk</code></td>
   <td><code>#fff8dc</code></td>
   <td style="background: cornsilk;"> </td>
  </tr>
  <tr>
   <td style="background: #dc143c;"> </td>
   <td style="text-align: center;"><code>crimson</code></td>
   <td><code>#dc143c</code></td>
   <td style="background: crimson;"> </td>
  </tr>
  <tr>
   <td style="background: #0ff;"> </td>
   <td style="text-align: center;"><code>cyan</code></td>
   <td><code>#00ffff</code></td>
   <td style="background: cyan;"> </td>
  </tr>
  <tr>
   <td style="background: #00008b;"> </td>
   <td style="text-align: center;"><code>darkblue</code></td>
   <td><code>#00008b</code></td>
   <td style="background: darkblue;"> </td>
  </tr>
  <tr>
   <td style="background: #008b8b;"> </td>
   <td style="text-align: center;"><code>darkcyan</code></td>
   <td><code>#008b8b</code></td>
   <td style="background: darkcyan;"> </td>
  </tr>
  <tr>
   <td style="background: #b8860b;"> </td>
   <td style="text-align: center;"><code>darkgoldenrod</code></td>
   <td><code>#b8860b</code></td>
   <td style="background: darkgoldenrod;"> </td>
  </tr>
  <tr>
   <td style="background: #a9a9a9;"> </td>
   <td style="text-align: center;"><code>darkgray</code></td>
   <td><code>#a9a9a9</code></td>
   <td style="background: darkgray;"> </td>
  </tr>
  <tr>
   <td style="background: #006400;"> </td>
   <td style="text-align: center;"><code>darkgreen</code></td>
   <td><code>#006400</code></td>
   <td style="background: darkgreen;"> </td>
  </tr>
  <tr>
   <td style="background: #a9a9a9;"> </td>
   <td style="text-align: center;"><code>darkgrey</code></td>
   <td><code>#a9a9a9</code></td>
   <td style="background: darkgrey;"> </td>
  </tr>
  <tr>
   <td style="background: #bdb76b;"> </td>
   <td style="text-align: center;"><code>darkkhaki</code></td>
   <td><code>#bdb76b</code></td>
   <td style="background: darkkhaki;"> </td>
  </tr>
  <tr>
   <td style="background: #8b008b;"> </td>
   <td style="text-align: center;"><code>darkmagenta</code></td>
   <td><code>#8b008b</code></td>
   <td style="background: darkmagenta;"> </td>
  </tr>
  <tr>
   <td style="background: #556b2f;"> </td>
   <td style="text-align: center;"><code>darkolivegreen</code></td>
   <td><code>#556b2f</code></td>
   <td style="background: darkolivegreen;"> </td>
  </tr>
  <tr>
   <td style="background: #ff8c00;"> </td>
   <td style="text-align: center;"><code>darkorange</code></td>
   <td><code>#ff8c00</code></td>
   <td style="background: darkorange;"> </td>
  </tr>
  <tr>
   <td style="background: #9932cc;"> </td>
   <td style="text-align: center;"><code>darkorchid</code></td>
   <td><code>#9932cc</code></td>
   <td style="background: darkorchid;"> </td>
  </tr>
  <tr>
   <td style="background: #8b0000;"> </td>
   <td style="text-align: center;"><code>darkred</code></td>
   <td><code>#8b0000</code></td>
   <td style="background: darkred;"> </td>
  </tr>
  <tr>
   <td style="background: #e9967a;"> </td>
   <td style="text-align: center;"><code>darksalmon</code></td>
   <td><code>#e9967a</code></td>
   <td style="background: darksalmon;"> </td>
  </tr>
  <tr>
   <td style="background: #8fbc8f;"> </td>
   <td style="text-align: center;"><code>darkseagreen</code></td>
   <td><code>#8fbc8f</code></td>
   <td style="background: darkseagreen;"> </td>
  </tr>
  <tr>
   <td style="background: #483d8b;"> </td>
   <td style="text-align: center;"><code>darkslateblue</code></td>
   <td><code>#483d8b</code></td>
   <td style="background: darkslateblue;"> </td>
  </tr>
  <tr>
   <td style="background: #2f4f4f;"> </td>
   <td style="text-align: center;"><code>darkslategray</code></td>
   <td><code>#2f4f4f</code></td>
   <td style="background: darkslategray;"> </td>
  </tr>
  <tr>
   <td style="background: #2f4f4f;"> </td>
   <td style="text-align: center;"><code>darkslategrey</code></td>
   <td><code>#2f4f4f</code></td>
   <td style="background: darkslategrey;"> </td>
  </tr>
  <tr>
   <td style="background: #00ced1;"> </td>
   <td style="text-align: center;"><code>darkturquoise</code></td>
   <td><code>#00ced1</code></td>
   <td style="background: darkturquoise;"> </td>
  </tr>
  <tr>
   <td style="background: #9400d3;"> </td>
   <td style="text-align: center;"><code>darkviolet</code></td>
   <td><code>#9400d3</code></td>
   <td style="background: darkviolet;"> </td>
  </tr>
  <tr>
   <td style="background: #ff1493;"> </td>
   <td style="text-align: center;"><code>deeppink</code></td>
   <td><code>#ff1493</code></td>
   <td style="background: deeppink;"> </td>
  </tr>
  <tr>
   <td style="background: #00bfff;"> </td>
   <td style="text-align: center;"><code>deepskyblue</code></td>
   <td><code>#00bfff</code></td>
   <td style="background: deepskyblue;"> </td>
  </tr>
  <tr>
   <td style="background: #696969;"> </td>
   <td style="text-align: center;"><code>dimgray</code></td>
   <td><code>#696969</code></td>
   <td style="background: dimgray;"> </td>
  </tr>
  <tr>
   <td style="background: #696969;"> </td>
   <td style="text-align: center;"><code>dimgrey</code></td>
   <td><code>#696969</code></td>
   <td style="background: dimgrey;"> </td>
  </tr>
  <tr>
   <td style="background: #1e90ff;"> </td>
   <td style="text-align: center;"><code>dodgerblue</code></td>
   <td><code>#1e90ff</code></td>
   <td style="background: dodgerblue;"> </td>
  </tr>
  <tr>
   <td style="background: #b22222;"> </td>
   <td style="text-align: center;"><code>firebrick</code></td>
   <td><code>#b22222</code></td>
   <td style="background: firebrick;"> </td>
  </tr>
  <tr>
   <td style="background: #fffaf0;"> </td>
   <td style="text-align: center;"><code>floralwhite</code></td>
   <td><code>#fffaf0</code></td>
   <td style="background: floralwhite;"> </td>
  </tr>
  <tr>
   <td style="background: #228b22;"> </td>
   <td style="text-align: center;"><code>forestgreen</code></td>
   <td><code>#228b22</code></td>
   <td style="background: forestgreen;"> </td>
  </tr>
  <tr>
   <td style="background: #dcdcdc;"> </td>
   <td style="text-align: center;"><code>gainsboro</code></td>
   <td><code>#dcdcdc</code></td>
   <td style="background: gainsboro;"> </td>
  </tr>
  <tr>
   <td style="background: #f8f8ff;"> </td>
   <td style="text-align: center;"><code>ghostwhite</code></td>
   <td><code>#f8f8ff</code></td>
   <td style="background: ghostwhite;"> </td>
  </tr>
  <tr>
   <td style="background: #ffd700;"> </td>
   <td style="text-align: center;"><code>gold</code></td>
   <td><code>#ffd700</code></td>
   <td style="background: gold;"> </td>
  </tr>
  <tr>
   <td style="background: #daa520;"> </td>
   <td style="text-align: center;"><code>goldenrod</code></td>
   <td><code>#daa520</code></td>
   <td style="background: goldenrod;"> </td>
  </tr>
  <tr>
   <td style="background: #adff2f;"> </td>
   <td style="text-align: center;"><code>greenyellow</code></td>
   <td><code>#adff2f</code></td>
   <td style="background: greenyellow ;"> </td>
  </tr>
  <tr>
   <td style="background: #808080;"> </td>
   <td style="text-align: center;"><code>grey</code></td>
   <td><code>#808080</code></td>
   <td style="background: grey;"> </td>
  </tr>
  <tr>
   <td style="background: #f0fff0;"> </td>
   <td style="text-align: center;"><code>honeydew</code></td>
   <td><code>#f0fff0</code></td>
   <td style="background: honeydew;"> </td>
  </tr>
  <tr>
   <td style="background: #ff69b4;"> </td>
   <td style="text-align: center;"><code>hotpink</code></td>
   <td><code>#ff69b4</code></td>
   <td style="background: hotpink;"> </td>
  </tr>
  <tr>
   <td style="background: #cd5c5c;"> </td>
   <td style="text-align: center;"><code>indianred</code></td>
   <td><code>#cd5c5c</code></td>
   <td style="background: indianred;"> </td>
  </tr>
  <tr>
   <td style="background: #4b0082;"> </td>
   <td style="text-align: center;"><code>indigo</code></td>
   <td><code>#4b0082</code></td>
   <td style="background: indigo;"> </td>
  </tr>
  <tr>
   <td style="background: #fffff0;"> </td>
   <td style="text-align: center;"><code>ivory</code></td>
   <td><code>#fffff0</code></td>
   <td style="background: ivory;"> </td>
  </tr>
  <tr>
   <td style="background: #f0e68c;"> </td>
   <td style="text-align: center;"><code>khaki</code></td>
   <td><code>#f0e68c</code></td>
   <td style="background: khaki;"> </td>
  </tr>
  <tr>
   <td style="background: #e6e6fa;"> </td>
   <td style="text-align: center;"><code>lavender</code></td>
   <td><code>#e6e6fa</code></td>
   <td style="background: lavender;"> </td>
  </tr>
  <tr>
   <td style="background: #fff0f5;"> </td>
   <td style="text-align: center;"><code>lavenderblush</code></td>
   <td><code>#fff0f5</code></td>
   <td style="background: lavenderblush ;"> </td>
  </tr>
  <tr>
   <td style="background: #7cfc00;"> </td>
   <td style="text-align: center;"><code>lawngreen</code></td>
   <td><code>#7cfc00</code></td>
   <td style="background: lawngreen;"> </td>
  </tr>
  <tr>
   <td style="background: #fffacd;"> </td>
   <td style="text-align: center;"><code>lemonchiffon</code></td>
   <td><code>#fffacd</code></td>
   <td style="background: lemonchiffon;"> </td>
  </tr>
  <tr>
   <td style="background: #add8e6;"> </td>
   <td style="text-align: center;"><code>lightblue</code></td>
   <td><code>#add8e6</code></td>
   <td style="background: lightblue;"> </td>
  </tr>
  <tr>
   <td style="background: #f08080;"> </td>
   <td style="text-align: center;"><code>lightcoral</code></td>
   <td><code>#f08080</code></td>
   <td style="background: lightcoral;"> </td>
  </tr>
  <tr>
   <td style="background: #e0ffff;"> </td>
   <td style="text-align: center;"><code>lightcyan</code></td>
   <td><code>#e0ffff</code></td>
   <td style="background: lightcyan;"> </td>
  </tr>
  <tr>
   <td style="background: #fafad2;"> </td>
   <td style="text-align: center;"><code>lightgoldenrodyellow</code></td>
   <td><code>#fafad2</code></td>
   <td style="background: lightgoldenrodyellow ;"> </td>
  </tr>
  <tr>
   <td style="background: #d3d3d3;"> </td>
   <td style="text-align: center;"><code>lightgray</code></td>
   <td><code>#d3d3d3</code></td>
   <td style="background: lightgray;"> </td>
  </tr>
  <tr>
   <td style="background: #90ee90;"> </td>
   <td style="text-align: center;"><code>lightgreen</code></td>
   <td><code>#90ee90</code></td>
   <td style="background: lightgreen;"> </td>
  </tr>
  <tr>
   <td style="background: #d3d3d3;"> </td>
   <td style="text-align: center;"><code>lightgrey</code></td>
   <td><code>#d3d3d3</code></td>
   <td style="background: lightgrey;"> </td>
  </tr>
  <tr>
   <td style="background: #ffb6c1;"> </td>
   <td style="text-align: center;"><code>lightpink</code></td>
   <td><code>#ffb6c1</code></td>
   <td style="background: lightpink;"> </td>
  </tr>
  <tr>
   <td style="background: #ffa07a;"> </td>
   <td style="text-align: center;"><code>lightsalmon</code></td>
   <td><code>#ffa07a</code></td>
   <td style="background: lightsalmon;"> </td>
  </tr>
  <tr>
   <td style="background: #20b2aa;"> </td>
   <td style="text-align: center;"><code>lightseagreen</code></td>
   <td><code>#20b2aa</code></td>
   <td style="background: lightseagreen;"> </td>
  </tr>
  <tr>
   <td style="background: #87cefa;"> </td>
   <td style="text-align: center;"><code>lightskyblue</code></td>
   <td><code>#87cefa</code></td>
   <td style="background: lightskyblue;"> </td>
  </tr>
  <tr>
   <td style="background: #778899;"> </td>
   <td style="text-align: center;"><code>lightslategray</code></td>
   <td><code>#778899</code></td>
   <td style="background: lightslategray;"> </td>
  </tr>
  <tr>
   <td style="background: #778899;"> </td>
   <td style="text-align: center;"><code>lightslategrey</code></td>
   <td><code>#778899</code></td>
   <td style="background: lightslategrey;"> </td>
  </tr>
  <tr>
   <td style="background: #b0c4de;"> </td>
   <td style="text-align: center;"><code>lightsteelblue</code></td>
   <td><code>#b0c4de</code></td>
   <td style="background: lightsteelblue;"> </td>
  </tr>
  <tr>
   <td style="background: #ffffe0;"> </td>
   <td style="text-align: center;"><code>lightyellow</code></td>
   <td><code>#ffffe0</code></td>
   <td style="background: lightyellow;"> </td>
  </tr>
  <tr>
   <td style="background: #32cd32;"> </td>
   <td style="text-align: center;"><code>limegreen</code></td>
   <td><code>#32cd32</code></td>
   <td style="background: limegreen;"> </td>
  </tr>
  <tr>
   <td style="background: #faf0e6;"> </td>
   <td style="text-align: center;"><code>linen</code></td>
   <td><code>#faf0e6</code></td>
   <td style="background: linen;"> </td>
  </tr>
  <tr>
   <td style="background: #66cdaa;"> </td>
   <td style="text-align: center;"><code>mediumaquamarine</code></td>
   <td><code>#66cdaa</code></td>
   <td style="background: mediumaquamarine;"> </td>
  </tr>
  <tr>
   <td style="background: #0000cd;"> </td>
   <td style="text-align: center;"><code>mediumblue</code></td>
   <td><code>#0000cd</code></td>
   <td style="background: mediumblue;"> </td>
  </tr>
  <tr>
   <td style="background: #ba55d3;"> </td>
   <td style="text-align: center;"><code>mediumorchid</code></td>
   <td><code>#ba55d3</code></td>
   <td style="background: mediumorchid;"> </td>
  </tr>
  <tr>
   <td style="background: #9370db;"> </td>
   <td style="text-align: center;"><code>mediumpurple</code></td>
   <td><code>#9370db</code></td>
   <td style="background: mediumpurple;"> </td>
  </tr>
  <tr>
   <td style="background: #3cb371;"> </td>
   <td style="text-align: center;"><code>mediumseagreen</code></td>
   <td><code>#3cb371</code></td>
   <td style="background: mediumseagreen;"> </td>
  </tr>
  <tr>
   <td style="background: #7b68ee;"> </td>
   <td style="text-align: center;"><code>mediumslateblue</code></td>
   <td><code>#7b68ee</code></td>
   <td style="background: mediumslateblue;"> </td>
  </tr>
  <tr>
   <td style="background: #00fa9a;"> </td>
   <td style="text-align: center;"><code>mediumspringgreen</code></td>
   <td><code>#00fa9a</code></td>
   <td style="background: mediumspringgreen;"> </td>
  </tr>
  <tr>
   <td style="background: #48d1cc;"> </td>
   <td style="text-align: center;"><code>mediumturquoise</code></td>
   <td><code>#48d1cc</code></td>
   <td style="background: mediumturquoise;"> </td>
  </tr>
  <tr>
   <td style="background: #c71585;"> </td>
   <td style="text-align: center;"><code>mediumvioletred</code></td>
   <td><code>#c71585</code></td>
   <td style="background: mediumvioletred;"> </td>
  </tr>
  <tr>
   <td style="background: #191970;"> </td>
   <td style="text-align: center;"><code>midnightblue</code></td>
   <td><code>#191970</code></td>
   <td style="background: midnightblue;"> </td>
  </tr>
  <tr>
   <td style="background: #f5fffa;"> </td>
   <td style="text-align: center;"><code>mintcream</code></td>
   <td><code>#f5fffa</code></td>
   <td style="background: mintcream;"> </td>
  </tr>
  <tr>
   <td style="background: #ffe4e1;"> </td>
   <td style="text-align: center;"><code>mistyrose</code></td>
   <td><code>#ffe4e1</code></td>
   <td style="background: mistyrose;"> </td>
  </tr>
  <tr>
   <td style="background: #ffe4b5;"> </td>
   <td style="text-align: center;"><code>moccasin</code></td>
   <td><code>#ffe4b5</code></td>
   <td style="background: moccasin;"> </td>
  </tr>
  <tr>
   <td style="background: #ffdead;"> </td>
   <td style="text-align: center;"><code>navajowhite</code></td>
   <td><code>#ffdead</code></td>
   <td style="background: navajowhite;"> </td>
  </tr>
  <tr>
   <td style="background: #fdf5e6;"> </td>
   <td style="text-align: center;"><code>oldlace</code></td>
   <td><code>#fdf5e6</code></td>
   <td style="background: oldlace;"> </td>
  </tr>
  <tr>
   <td style="background: #6b8e23;"> </td>
   <td style="text-align: center;"><code>olivedrab</code></td>
   <td><code>#6b8e23</code></td>
   <td style="background: olivedrab;"> </td>
  </tr>
  <tr>
   <td style="background: #ff4500;"> </td>
   <td style="text-align: center;"><code>orangered</code></td>
   <td><code>#ff4500</code></td>
   <td style="background: orangered;"> </td>
  </tr>
  <tr>
   <td style="background: #da70d6;"> </td>
   <td style="text-align: center;"><code>orchid</code></td>
   <td><code>#da70d6</code></td>
   <td style="background: orchid;"> </td>
  </tr>
  <tr>
   <td style="background: #eee8aa;"> </td>
   <td style="text-align: center;"><code>palegoldenrod</code></td>
   <td><code>#eee8aa</code></td>
   <td style="background: palegoldenrod;"> </td>
  </tr>
  <tr>
   <td style="background: #98fb98;"> </td>
   <td style="text-align: center;"><code>palegreen</code></td>
   <td><code>#98fb98</code></td>
   <td style="background: palegreen;"> </td>
  </tr>
  <tr>
   <td style="background: #afeeee;"> </td>
   <td style="text-align: center;"><code>paleturquoise</code></td>
   <td><code>#afeeee</code></td>
   <td style="background: paleturquoise;"> </td>
  </tr>
  <tr>
   <td style="background: #db7093;"> </td>
   <td style="text-align: center;"><code>palevioletred</code></td>
   <td><code>#db7093</code></td>
   <td style="background: palevioletred;"> </td>
  </tr>
  <tr>
   <td style="background: #ffefd5;"> </td>
   <td style="text-align: center;"><code>papayawhip</code></td>
   <td><code>#ffefd5</code></td>
   <td style="background: papayawhip;"> </td>
  </tr>
  <tr>
   <td style="background: #ffdab9;"> </td>
   <td style="text-align: center;"><code>peachpuff</code></td>
   <td><code>#ffdab9</code></td>
   <td style="background: peachpuff;"> </td>
  </tr>
  <tr>
   <td style="background: #cd853f;"> </td>
   <td style="text-align: center;"><code>peru</code></td>
   <td><code>#cd853f</code></td>
   <td style="background: peru;"> </td>
  </tr>
  <tr>
   <td style="background: #ffc0cb;"> </td>
   <td style="text-align: center;"><code>pink</code></td>
   <td><code>#ffc0cb</code></td>
   <td style="background: pink;"> </td>
  </tr>
  <tr>
   <td style="background: #dda0dd;"> </td>
   <td style="text-align: center;"><code>plum</code></td>
   <td><code>#dda0dd</code></td>
   <td style="background: plum;"> </td>
  </tr>
  <tr>
   <td style="background: #b0e0e6;"> </td>
   <td style="text-align: center;"><code>powderblue</code></td>
   <td><code>#b0e0e6</code></td>
   <td style="background: powderblue;"> </td>
  </tr>
  <tr>
   <td style="background: #bc8f8f;"> </td>
   <td style="text-align: center;"><code>rosybrown</code></td>
   <td><code>#bc8f8f</code></td>
   <td style="background: rosybrown;"> </td>
  </tr>
  <tr>
   <td style="background: #4169e1;"> </td>
   <td style="text-align: center;"><code>royalblue</code></td>
   <td><code>#4169e1</code></td>
   <td style="background: royalblue;"> </td>
  </tr>
  <tr>
   <td style="background: #8b4513;"> </td>
   <td style="text-align: center;"><code>saddlebrown</code></td>
   <td><code>#8b4513</code></td>
   <td style="background: saddlebrown;"> </td>
  </tr>
  <tr>
   <td style="background: #fa8072;"> </td>
   <td style="text-align: center;"><code>salmon</code></td>
   <td><code>#fa8072</code></td>
   <td style="background: salmon;"> </td>
  </tr>
  <tr>
   <td style="background: #f4a460;"> </td>
   <td style="text-align: center;"><code>sandybrown</code></td>
   <td><code>#f4a460</code></td>
   <td style="background: sandybrown;"> </td>
  </tr>
  <tr>
   <td style="background: #2e8b57;"> </td>
   <td style="text-align: center;"><code>seagreen</code></td>
   <td><code>#2e8b57</code></td>
   <td style="background: seagreen;"> </td>
  </tr>
  <tr>
   <td style="background: #fff5ee;"> </td>
   <td style="text-align: center;"><code>seashell</code></td>
   <td><code>#fff5ee</code></td>
   <td style="background: seashell;"> </td>
  </tr>
  <tr>
   <td style="background: #a0522d;"> </td>
   <td style="text-align: center;"><code>sienna</code></td>
   <td><code>#a0522d</code></td>
   <td style="background: sienna;"> </td>
  </tr>
  <tr>
   <td style="background: #87ceeb;"> </td>
   <td style="text-align: center;"><code>skyblue</code></td>
   <td><code>#87ceeb</code></td>
   <td style="background: skyblue;"> </td>
  </tr>
  <tr>
   <td style="background: #6a5acd;"> </td>
   <td style="text-align: center;"><code>slateblue</code></td>
   <td><code>#6a5acd</code></td>
   <td style="background: slateblue;"> </td>
  </tr>
  <tr>
   <td style="background: #708090;"> </td>
   <td style="text-align: center;"><code>slategray</code></td>
   <td><code>#708090</code></td>
   <td style="background: slategray;"> </td>
  </tr>
  <tr>
   <td style="background: #708090;"> </td>
   <td style="text-align: center;"><code>slategrey</code></td>
   <td><code>#708090</code></td>
   <td style="background: slategrey;"> </td>
  </tr>
  <tr>
   <td style="background: #fffafa;"> </td>
   <td style="text-align: center;"><code>snow</code></td>
   <td><code>#fffafa</code></td>
   <td style="background: snow;"> </td>
  </tr>
  <tr>
   <td style="background: #00ff7f;"> </td>
   <td style="text-align: center;"><code>springgreen</code></td>
   <td><code>#00ff7f</code></td>
   <td style="background: springgreen;"> </td>
  </tr>
  <tr>
   <td style="background: #4682b4;"> </td>
   <td style="text-align: center;"><code>steelblue</code></td>
   <td><code>#4682b4</code></td>
   <td style="background: steelblue;"> </td>
  </tr>
  <tr>
   <td style="background: #d2b48c;"> </td>
   <td style="text-align: center;"><code>tan</code></td>
   <td><code>#d2b48c</code></td>
   <td style="background: tan;"> </td>
  </tr>
  <tr>
   <td style="background: #d8bfd8;"> </td>
   <td style="text-align: center;"><code>thistle</code></td>
   <td><code>#d8bfd8</code></td>
   <td style="background: thistle;"> </td>
  </tr>
  <tr>
   <td style="background: #ff6347;"> </td>
   <td style="text-align: center;"><code>tomato</code></td>
   <td><code>#ff6347</code></td>
   <td style="background: tomato;"> </td>
  </tr>
  <tr>
   <td style="background: #40e0d0;"> </td>
   <td style="text-align: center;"><code>turquoise</code></td>
   <td><code>#40e0d0</code></td>
   <td style="background: turquoise;"> </td>
  </tr>
  <tr>
   <td style="background: #ee82ee;"> </td>
   <td style="text-align: center;"><code>violet</code></td>
   <td><code>#ee82ee</code></td>
   <td style="background: violet;"> </td>
  </tr>
  <tr>
   <td style="background: #f5deb3;"> </td>
   <td style="text-align: center;"><code>wheat</code></td>
   <td><code>#f5deb3</code></td>
   <td style="background: wheat;"> </td>
  </tr>
  <tr>
   <td style="background: #f5f5f5;"> </td>
   <td style="text-align: center;"><code>whitesmoke</code></td>
   <td><code>#f5f5f5</code></td>
   <td style="background: whitesmoke;"> </td>
  </tr>
  <tr>
   <td style="background: #9acd32;"> </td>
   <td style="text-align: center;"><code>yellowgreen</code></td>
   <td><code>#9acd32</code></td>
   <td style="background: yellowgreen;"> </td>
  </tr>
  <tr>
   <td>{{SpecName("CSS4 Colors")}}</td>
   <td style="background: #639;"> </td>
   <td style="text-align: center;"><code>rebeccapurple</code></td>
   <td><code>#663399</code></td>
   <td style="background: rebeccapurple;"> </td>
  </tr>
 </tbody>
</table>

<p>A cor <code>rebeccapurple</code> é equivalente à cor <code>#639</code>, e mais informações sobre por que foi introduzida pode ser encontrada neste post no blog Codepen por Trezy "<a href="https://codepen.io/trezy/post/honoring-a-great-man">Honoring a Great Man</a>" (em inglês)</p>

<h3 id="palavra-chave_transparent"><code>palavra-chave transparent</code></h3>

<p>A palavra-chave <code>transparent </code>representa uma cor totalmente transparente, isto é, a cor vista será a cor de fundo. Tecnicamente, é um preto com canal alfa no seu valor mínimo e é um atalho para <code>rgba(0,0,0,0)</code>.</p>

<div class="note"><strong>Nota histórica</strong><br>
A palavra-chave <code>transparent</code> não era uma cor verdadeira no CSS nível 2 (Revisão 1). Era uma palavra-chave específica que poderia ser usada no lugar de um valor <code>&lt;color&gt;</code> regular em duas propriedades CSS: {{Cssxref("background")}} e {{Cssxref("border")}}. Ela foi adicionada essencialmente para permitir a substituição de cores sólidas herdadas.<br>
<br>
Com o apoio da opacidade através de <a class="external" href="https://en.wikipedia.org/wiki/Alpha_compositing">canais alfal</a>, <code>transparent</code> foi redefinida como uma cor verdadeira no Cores CSS nível 3 permitindo seu uso em qualquer lugar onde for exigido um valor para <code>&lt;color&gt;</code>, como a propriedade {{Cssxref("color")}}.</div>

<h3 id="palavra-chave_currentcolor"><code>palavra-chave currentcolor</code></h3>

<p>A palavra-chave <code>currentcolor</code> representa o valor calculado da propriedade {{Cssxref("color")}} dos elementos . Ela permite que as propriedades de cor sejam herdadas por propriedades ou propriedades de elemento filho que não a herdam por padrão.</p>

<p>Ela também pode ser usada em propriedades que herdam o valor calculado da propriedade {{Cssxref ("color")}} do elemento e será equivalente à palavra-chave <code>inherit</code> nesses elementos, se houver.</p>

<h4 id="Exemplo_ao_vivo">Exemplo ao vivo</h4>

<p>A cor da linha (uma div preenchida com cor) se adapta à cor de sua propriedade {{Cssxref ("color")}}, herdada de seu pai.</p>

<div style="width: 50%;">
<h5 id="Exemplo_1">Exemplo 1</h5>

<pre class="brush: html">&lt;div style="color:darkred"&gt;
A cor deste texto é a mesma da linha:  &lt;div style="background:currentcolor; height:1px"&gt;&lt;/div&gt;
 Mais algum texto.
&lt;/div&gt;
</pre>

<p>{{EmbedLiveSample('Live_example_1')}}</p>

<h5 id="Exemplo_2">Exemplo 2</h5>

<pre class="brush: html">&lt;div style="color:blue; border-bottom: 1px dashed currentcolor;"&gt;
A cor deste texto é a mesma da linha:  &lt;div style="background:currentcolor; height:1px"&gt;&lt;/div&gt;
 Mais algum texto.
&lt;/div&gt; </pre>

<p>{{EmbedLiveSample('Live_example_2')}}</p>
</div>

<h3 id="rgb()"><a id="rgb"><code>rgb()</code></a></h3>

<div class="note">
<p><strong>Nota</strong>: Na especificação Módulo de cor CSS Color nível 4, a rgba() foi definida como uma função herdada com gramática e comportamento idênticos à rgb(); na verdade, um apelido. Mais para frente, ambas podem aceitar exatamente os mesmos parâmetros.</p>
</div>

<p>Colors can be defined using the red-green-blue (RGB) model in two ways:</p>

<dl>
 <dt>Hexadecimal notation <code>#RRGGBB,</code> <code>#RGB</code></dt>
 <dd>
 <ul style="margin-bottom: 0;">
  <li>"<code>#</code>", followed by six hexadecimal characters (0-9, A-F), where the first two digits represent the red part, the second two the green part and the last two the blue part.</li>
  <li>"<code>#</code>", followed by three hexadecimal characters (0-9, A-F), where the first digit represents the red part, the second the green part and the last one the blue part.</li>
 </ul>
 The three-digit RGB notation (<code>#RGB</code>) and the six-digit form (<code>#RRGGBB</code>) are equal, for example <code>#f03</code> and <code>#ff0033</code> represent the same color.</dd>
 <dt>Functional Notation <code>rgb(R,G,B)</code></dt>
 <dd>"<code>rgb</code>", followed by three {{cssxref("&lt;integer&gt;")}} or three {{cssxref("&lt;percentage&gt;")}} values, plus an optional alpha value that specifies the transparency of the color (this can be a {{cssxref("&lt;number&gt;")}} between 0 and 1, or a {{cssxref("&lt;percentage&gt;")}})<br>
 The integer number 255 corresponds to 100%, and to F or FF in the hexadecimal notation.</dd>
</dl>

<pre class="plain">/* These examples all specify the same RGB color: */

#f03
#F03
#ff0033
#FF0033
rgb(255,0,51)
rgb(255, 0, 51)
<s>rgb(255, 0, 51.2)</s> /* ERROR! Don't use fractions, use integers */
rgb(100%,0%,20%)
rgb(100%, 0%, 20%)
<s>rgb(100%, 0, 20%)</s> /* ERROR! Don't mix up integer and percentage notation */

/* whitespace syntax */
rgb(255 0 0)

/* optional alpha value */
rgb(255,0,0,0.4)  /* 40% opaque red */ 
rgb(255,0,0,40%)  /* 40% opaque red with percentage value for alpha */ 
rgb(255 0 0 / 0.4)  /* 40% opaque red */ 
rgb(255 0 0 / 40%)  /* 40% opaque red with percentage value for alpha */ 

</pre>

<h3 id="hsl()"><a id="hsl"><code>hsl()</code></a></h3>

<div class="note">
<p><strong>Note</strong>: In the CSS Color Module Level 4 spec, <code>hsla()</code> has been defined as a legacy function with identical grammar and behaviour to <code>hsl()</code>; in effect, an alias. Going forward, both can accept exactly the same parameters.</p>
</div>

<p>Colors can also be defined via hue, saturation, and lightness, or HSL, by using the <code>hsl()</code> functional notation. The advantage of HSL over RGB is that it is far more intuitive: you can guess at the colors you want, and then tweak. It is also easier to create sets of matching colors (by keeping the hue the same and varying the lightness/darkness, and saturation).</p>

<p><strong>Hue </strong>is represented as an angle of the color circle (i.e. the rainbow represented in a circle). This angle is given as a unitless {{cssxref("&lt;number&gt;")}}. By definition <strong>red=0=360</strong>, and the other colors are spread around the circle, so <strong>green=120</strong>, <strong>blue=240</strong>, etc. As an angle, it implicitly wraps around such that -120=240 and 480=120.</p>

<p>Saturation and lightness are represented as percentages.<br>
 <code>100%</code> is full <strong>saturation</strong>, and<code> 0%</code> is a shade of grey.<br>
 <code>100%</code> <strong>lightness</strong> is white, <code>0%</code> lightness is black, and <code>50%</code> lightness is “normal.”</p>

<pre class="brush: css" style="text-shadow: rgba(255,255,255,0.4) -1px -1px;">hsl(0,  100%,50%)    /* red */   
hsl(30, 100%,50%)                
hsl(60, 100%,50%)                
hsl(90, 100%,50%)                
hsl(120,100%,50%)    /* green */ 
hsl(150,100%,50%)                
hsl(180,100%,50%)                
hsl(210,100%,50%)                
hsl(240,100%,50%)    /* blue */  
hsl(270,100%,50%)                
hsl(300,100%,50%)                
hsl(330,100%,50%)                
hsl(360,100%,50%)    /* red */   

hsl(120,100%,25%)    /* dark green */  
hsl(120,100%,50%)    /* green */       
hsl(120,100%,75%)    /* light green */ 

hsl(120,100%,50%)    /* green */  
hsl(120, 67%,50%)                 
hsl(120, 33%,50%)                 
hsl(120,  0%,50%)                 

hsl(120, 60%,70%)    /* pastel green */ 

/* whitespace syntax */
hsl(120 60% 70%)  /* pastel green */ 

/* angle values for hue component; also accepts rad, grad, turn */
hsl(120deg 60% 70%)  /* pastel green */ 

/* optional alpha value */
hsl(240,100%,50%,0.05)  /* 5% opaque blue */ 
hsl(240,100%,50%,5%)  /* 5% opaque blue with percentage value for alpha */ 
hsl(240 100% 50% / 0.05) /* 5% opaque blue */
hsl(240 100% 50% / 5%) /* 5% opaque blue with percentage value for alpha */
</pre>

<h3 id="rgba()"><a id="rgba"><code>rgba()</code></a></h3>

<p>Colors can be defined in the Red-green-blue-alpha model (RGBa) in two ways:</p>

<dl>
 <dt>Hexadecimal notation <code>#RRGGBBAA and #RGBA</code></dt>
 <dd>
 <ul style="margin-bottom: 0;">
  <li>"<code>#</code>", followed by eight hexadecimal characters (0-9, A-F), where the first two digits represent the red part, the second two the green part, the third two the blue part and the last two the transparency.</li>
  <li>"<code>#</code>", followed by four hexadecimal characters (0-9, A-F), where the first digit represents the red part, the second the green part, the third one the blue part and the last one the transparency.</li>
 </ul>
 The four-digit RGB notation (<code>#RGBA</code>) and the eight-digit form (<code>#RRGGBBAA</code>) are equal, for example, <code>#f038</code> and <code>#ff003388</code> represent the same color.</dd>
 <dt>using the <code>rgba()</code> functional notation.</dt>
 <dd>RGBa extends the RGB color model to include the alpha channel, allowing specification of the opacity of a color.<br>
 <strong>a</strong> means opacity: 0=transparent; 1=opaque;</dd>
</dl>

<pre class="brush: css">#f030                /* 0% opaque red */  
#F03F                /* full opaque red */  
#ff003300            /* 0% opaque red */  
#FF003388            /* 50% opaque red */  
rgba(255,0,0,0.1)    /* 10% opaque red */  
rgba(255,0,0,0.4)    /* 40% opaque red */  
rgba(255,0,0,0.7)    /* 70% opaque red */  
rgba(255,0,0,  1)    /* full opaque red */ 

/* whitespace syntax */
rgba(255 0 0 / 0.4)  /* 40% opaque red */ 

/* percentage value for alpha */
rgba(255 0 0 / 40%)  /* 40% opaque red */ 
</pre>

<div class="note">
<p><strong>Note</strong>: In the CSS Color Module Level 4 spec, <code>rgba()</code> has been defined as a legacy function with identical grammar and behaviour to <code>rgb()</code>; in effect, an alias. Going forward, both can accept exactly the same parameters.</p>
</div>

<h3 id="hsla()"><a id="hsla"><code>hsla()</code></a></h3>

<p>Colors can be defined in the hue-saturation-lightness-alpha model (HSLa) using the <code>hsla()</code> functional notation. HSLa extends the HSL color model to include the alpha channel, allowing specification of the opacity of a color.<br>
 <strong>a</strong> means opacity: 0=transparent; 1=opaque;</p>

<pre class="brush: css" style="text-shadow: rgba(255,255,255,0.4) -1px -1px;">hsla(240,100%,50%,0.05)   /* 5% opaque blue */   
hsla(240,100%,50%, 0.4)   /* 40% opaque blue */  
hsla(240,100%,50%, 0.7)   /* 70% opaque blue */  
hsla(240,100%,50%,   1)   /* full opaque blue */ 

/* whitespace syntax */
hsla(240 100% 50% / 0.05) /* 5% opaque blue */ 

/* percentage value for alpha */
hsla(240 100% 50% / 5%) /* 5% opaque blue */ 

/* angle values for hue component; also accepts rad, grad, turn */
hsla(240deg 100% 50% / 5%) /* 5% opaque blue */ 
hsla(240deg,100%,50%, 0.4)  /* 40% opaque blue */ 
</pre>

<div class="note">
<p><strong>Note</strong>: In the CSS Color Module Level 4 spec, <code>hsla()</code> has been defined as a legacy function with identical grammar and behaviour to <code>hsl()</code>; in effect, an alias. Going forward, both can accept exactly the same parameters.</p>
</div>

<h3 id="System_Colors">System Colors</h3>

<p>Not all system colors are supported on all systems. {{deprecated_inline}} for use on public web pages.</p>

<dl style="font: small Tahoma,'Liberation Sans','Nimbus Sans L',sans-serif; border: 1px solid powderblue; padding: 0.5em 0pt 0.5em 0.5em; -moz-column-rule: 1px solid powderblue; -moz-column-width: 15em; background: #eee; -webkit-columns: 15em; -webkit-column-rule: 1px solid powderblue; columns: 17em; column-rule: 1px solid powderblue;">
 <dt>ActiveBorder</dt>
 <dd>Active window border.</dd>
 <dt>ActiveCaption</dt>
 <dd>Active window caption. Should be used with <code>CaptionText</code> as foreground color.</dd>
 <dt>AppWorkspace</dt>
 <dd>Background color of multiple document interface.</dd>
 <dt>Background</dt>
 <dd>Desktop background.</dd>
 <dt>ButtonFace</dt>
 <dd>Face background color for 3-D elements that appear 3-D due to one layer of surrounding border.  Should be used with the <code>ButtonText</code> foreground color.</dd>
 <dt>ButtonHighlight</dt>
 <dd>The color of the border facing the light source for 3-D elements that appear 3-D due to that layer of surrounding border.</dd>
 <dt>ButtonShadow</dt>
 <dd>The color of the border away from the light source for 3-D elements that appear 3-D due to that layer of surrounding border.</dd>
 <dt>ButtonText</dt>
 <dd>Text on push buttons. Should be used with the <code>ButtonFace</code> or <code>ThreeDFace</code> background color.</dd>
 <dt>CaptionText</dt>
 <dd>Text in caption, size box, and scrollbar arrow box. Should be used with the <code>ActiveCaption</code> background color.</dd>
 <dt>GrayText</dt>
 <dd>Grayed (disabled) text.</dd>
 <dt>Highlight</dt>
 <dd>Item(s) selected in a control.  Should be used with the <code>HighlightText</code> foreground color.</dd>
 <dt>HighlightText</dt>
 <dd>Text of item(s) selected in a control. Should be used with the <code>Highlight</code> background color.</dd>
 <dt>InactiveBorder</dt>
 <dd>Inactive window border.</dd>
 <dt>InactiveCaption</dt>
 <dd>Inactive window caption. Should be used with the <code>InactiveCaptionText</code> foreground color.</dd>
 <dt>InactiveCaptionText</dt>
 <dd>Color of text in an inactive caption.  Should be used with the <code>InactiveCaption</code> background color.</dd>
 <dt>InfoBackground</dt>
 <dd>Background color for tooltip controls. Should be used with the <code>InfoText</code> foreground color.</dd>
 <dt>InfoText</dt>
 <dd>Text color for tooltip controls.  Should be used with the <code>InfoBackground</code> background color.</dd>
 <dt>Menu</dt>
 <dd>Menu background. Should be used with the <code>MenuText</code> or  <code>-moz-MenuBarText</code> foreground color.</dd>
 <dt>MenuText</dt>
 <dd>Text in menus. Should be used with the <code>Menu</code> background color.</dd>
 <dt>Scrollbar</dt>
 <dd>Background color of scroll bars.</dd>
 <dt>ThreeDDarkShadow</dt>
 <dd>The color of the darker (generally outer) of the two borders away from the light source for 3-D elements that appear 3-D due to two concentric layers of surrounding border.</dd>
 <dt>ThreeDFace</dt>
 <dd>The face background color for 3-D elements that appear 3-D due to two concentric layers of surrounding border. Should be used with the <code>ButtonText</code> foreground color.</dd>
 <dt>ThreeDHighlight</dt>
 <dd>The color of the lighter (generally outer) of the two borders facing the light source for 3-D elements that appear 3-D due to two<br>
 concentric layers of surrounding border.</dd>
 <dt>ThreeDLightShadow</dt>
 <dd>The color of the darker (generally inner) of the two borders facing the light source for 3-D elements that appear 3-D due to two<br>
 concentric layers of surrounding border.</dd>
 <dt>ThreeDShadow</dt>
 <dd>The color of the lighter (generally inner) of the two borders away from the light source for 3-D elements that appear 3-D due to two concentric layers of surrounding border.</dd>
 <dt>Window</dt>
 <dd>Window background. Should be used with the <code>WindowText</code> foreground color.</dd>
 <dt>WindowFrame</dt>
 <dd>Window frame.</dd>
 <dt>WindowText</dt>
 <dd>Text in windows. Should be used with the <code>Window</code> background color.</dd>
</dl>

<h3 id="Mozilla_System_Color_Extensions">Mozilla System Color Extensions</h3>

<dl style="font: small Tahoma,'Liberation Sans','Nimbus Sans L',sans-serif; border: 1px solid powderblue; padding: 0.5em 0 0.5em 0.5em; -moz-column-rule: 1px solid powderblue; -moz-column-width: 17em; background: #eee; -webkit-columns: 17em; -webkit-column-rule: 1px solid powderblue; columns: 17em; column-rule: 1px solid powderblue;">
 <dt>-moz-ButtonDefault</dt>
 <dd>The border color that goes around buttons that represent the default action for a dialog box.</dd>
 <dt>-moz-ButtonHoverFace</dt>
 <dd>The background color of a button that the mouse pointer is over (which would be <code>ThreeDFace</code> or <code>ButtonFace</code> when the mouse pointer is not over it). Should be used with the <code>-moz-ButtonHoverText</code> foreground color.</dd>
 <dt>-moz-ButtonHoverText</dt>
 <dd>The text color of a button that the mouse pointer is over (which would be ButtonText when the mouse pointer is not over it).  Should be used with the <code>-moz-ButtonHoverFace background</code> color.</dd>
 <dt>-moz-CellHighlight</dt>
 <dd>Background color for selected item in a tree widget.  Should be used with the <code>-moz-CellHighlightText</code> foreground color. See also <code>-moz-html-CellHighlight</code>.</dd>
 <dt>-moz-CellHighlightText</dt>
 <dd>Text color for a selected item in a tree. Should be used with the <code>-moz-CellHighlight background</code> color. See also <code>-moz-html-CellHighlightText</code>.</dd>
 <dt>-moz-Combobox</dt>
 <dd>{{Gecko_minversion_inline("1.9.2")}} Background color for combo-boxes.  Should be used with the <code>-moz-ComboboxText</code> foreground color. In versions prior to 1.9.2, use <code>-moz-Field</code> instead.</dd>
 <dt>-moz-ComboboxText</dt>
 <dd>{{Gecko_minversion_inline("1.9.2")}} Text color for combo-boxes. Should be used with the <code>-moz-Combobox</code> background color.  In versions prior to 1.9.2, use <code>-moz-FieldText</code> instead.</dd>
 <dt>-moz-Dialog</dt>
 <dd>Background color for dialog boxes.  Should be used with the <code>-moz-DialogText</code> foreground color.</dd>
 <dt>-moz-DialogText</dt>
 <dd>Text color for dialog boxes. Should be used with the <code>-moz-Dialog</code> background color.</dd>
 <dt>-moz-dragtargetzone</dt>
 <dt>-moz-EvenTreeRow</dt>
 <dd>{{gecko_minversion_inline("1.9")}} Background color for even-numbered rows in a tree.  Should be used with the <code>-moz-FieldText</code> foreground color. In Gecko versions prior to 1.9, use <code>-moz-Field</code>.  See also <code>-moz-OddTreeRow</code>.</dd>
 <dt>-moz-Field</dt>
 <dd>Text field background color.  Should be used with the <code>-moz-FieldText</code> foreground color.</dd>
 <dt>-moz-FieldText</dt>
 <dd>Text field text color. Should be used with the <code>-moz-Field</code>, <code>-moz-EvenTreeRow</code>, or <code>-moz-OddTreeRow</code> background color.</dd>
 <dt>-moz-html-CellHighlight</dt>
 <dd>{{gecko_minversion_inline("1.9")}} Background color for highlighted item in HTML {{HTMLElement("select")}}s. Should be used with the <code>-moz-html-CellHighlightText</code> foreground color. Prior to Gecko 1.9, use <code>-moz-CellHighlight</code>.</dd>
 <dt>-moz-html-CellHighlightText</dt>
 <dd>{{gecko_minversion_inline("1.9")}} Text color for highlighted items in HTML {{HTMLElement("select")}}s.  Should be used with the <code>-moz-html-CellHighlight</code> background color. Prior to Gecko 1.9, use <code>-moz-CellHighlightText</code>.</dd>
 <dt>-moz-mac-accentdarkestshadow</dt>
 <dt>-moz-mac-accentdarkshadow</dt>
 <dt>-moz-mac-accentface</dt>
 <dt>-moz-mac-accentlightesthighlight</dt>
 <dt>-moz-mac-accentlightshadow</dt>
 <dt>-moz-mac-accentregularhighlight</dt>
 <dt>-moz-mac-accentregularshadow</dt>
 <dt>-moz-mac-chrome-active</dt>
 <dd>{{Gecko_minversion_inline("1.9.1")}}</dd>
 <dt>-moz-mac-chrome-inactive</dt>
 <dd>{{Gecko_minversion_inline("1.9.1")}}</dd>
 <dt>-moz-mac-focusring</dt>
 <dt>-moz-mac-menuselect</dt>
 <dt>-moz-mac-menushadow</dt>
 <dt>-moz-mac-menutextselect</dt>
 <dt>-moz-MenuHover</dt>
 <dd>Background color for hovered menu items. Often similar to <code>Highlight</code>. Should be used with the <code>-moz-MenuHoverText</code> or <code>-moz-MenuBarHoverText</code> foreground color.</dd>
 <dt>-moz-MenuHoverText</dt>
 <dd>Text color for hovered menu items. Often similar to <code>HighlightText</code>.  Should be used with the <code>-moz-MenuHover</code> background color.</dd>
 <dt>-moz-MenuBarText</dt>
 <dd>{{Gecko_minversion_inline("1.9.2")}} Text color in menu bars. Often similar to <code>MenuText</code>. Should be used on top of <code>Menu</code> background.</dd>
 <dt>-moz-MenuBarHoverText</dt>
 <dd>Color for hovered text in menu bars. Often similar to <code>-moz-MenuHoverText</code>. Should be used on top of <code>-moz-MenuHover</code> background.</dd>
 <dt>-moz-nativehyperlinktext</dt>
 <dd>{{Gecko_minversion_inline("1.9.1")}} Default platform hyperlink color.</dd>
 <dt>-moz-OddTreeRow</dt>
 <dd>{{gecko_minversion_inline("1.9")}} Background color for odd-numbered rows in a tree.  Should be used with the <code>-moz-FieldText</code> foreground color. In Gecko versions prior to 1.9, use <code>-moz-Field</code>. See also <code>-moz-EvenTreeRow</code>.</dd>
 <dt>-moz-win-communicationstext</dt>
 <dd>{{gecko_minversion_inline("1.9")}} Should be used for text in objects with <code>{{cssxref("-moz-appearance")}}: -moz-win-communications-toolbox;</code>.</dd>
 <dt>-moz-win-mediatext</dt>
 <dd>{{gecko_minversion_inline("1.9")}} Should be used for text in objects with <code>{{cssxref("-moz-appearance")}}: -moz-win-media-toolbox</code>.</dd>
</dl>

<h3 id="Mozilla_Color_Preference_Extensions">Mozilla Color Preference Extensions</h3>

<dl style="font: small Tahoma,'Liberation Sans','Nimbus Sans L',sans-serif; border: 1px solid powderblue; padding: 0.5em 0 0.5em 0.5em; background: #eee;">
 <dt>-moz-activehyperlinktext</dt>
 <dd>User's preference for text color of active links. Should be used with the default document background color.</dd>
 <dt>-moz-default-background-color</dt>
 <dd>{{Gecko_minversion_inline("5.0")}} User's preference for the document background color.</dd>
 <dt>-moz-default-color</dt>
 <dd>{{Gecko_minversion_inline("5.0")}} User's preference for the text color.</dd>
 <dt>-moz-hyperlinktext</dt>
 <dd>User's preference for the text color of unvisited links. Should be used with the default document background color.</dd>
 <dt>-moz-visitedhyperlinktext</dt>
 <dd>User's preference for the text color of visited links. Should be used with the default document background color.</dd>
</dl>

<h2 id="Specificações">Specificações</h2>

<table class="standard-table">
 <thead>
  <tr>
   <th scope="col">Specificação</th>
   <th scope="col">Estado</th>
   <th scope="col">Comentário</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>{{SpecName('CSS4 Colors', '#colorunits', '&lt;color&gt;')}}</td>
   <td>{{Spec2('CSS4 Colors')}}</td>
   <td>Added <code>rebeccapurple</code>, four- (<code>#RGBA</code>) and eight-digit (<code>#RRGGBBAA</code>) hexadecimal notations, <code>rgba()</code> and <code>hsla()</code> as aliases of <code>rgb()</code> and <code>hsl()</code> (both with identical parameter syntax), space-separated function parameters rather than commas, percentages for alpha values, and angles for the hue component in <code>hsl()</code> colors.</td>
  </tr>
  <tr>
   <td>{{SpecName('CSS3 Colors', '#colorunits', '&lt;color&gt;')}}</td>
   <td>{{Spec2('CSS3 Colors')}}</td>
   <td>Deprecated system-colors; added SVG colors; added <code>rgba()</code>, <code>hsl()</code>, <code>hsla()</code> functional notation.</td>
  </tr>
  <tr style="vertical-align: top;">
   <td style="vertical-align: top;">{{SpecName('CSS2.1', 'syndata.html#value-def-color', '&lt;color&gt;')}}</td>
   <td style="vertical-align: top;">{{Spec2('CSS2.1')}}</td>
   <td style="vertical-align: top;">Added the <code>orange</code> color and the system-colors.</td>
  </tr>
  <tr>
   <td style="vertical-align: top;">{{SpecName('CSS1', '#color-units', '&lt;color&gt;')}}</td>
   <td style="vertical-align: top;">{{Spec2('CSS1')}}</td>
   <td style="vertical-align: top;">Initial definition.</td>
  </tr>
 </tbody>
</table>

<h2 id="Browser_compatibility">Compatibilidade com navegadores</h2>

{{Compat("css.types.color")}}

<h2 id="Ver_também">Ver também</h2>

<ul>
 <li>The {{Cssxref("opacity")}} property, allowing to define the transparency of color at the element level.</li>
 <li>The {{Cssxref("color")}}, {{Cssxref("background-color")}}, {{Cssxref("border-color")}}, {{Cssxref("outline-color")}}, {{Cssxref("text-shadow")}}, {{Cssxref("box-shadow")}} properties.</li>
</ul>