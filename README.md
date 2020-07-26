# Acessibilidade Web

![Build Status](https://travis-ci.org/joemccann/dillinger.svg)[](https://github.com/nathy-mesquita/web-accessibility-front-end)
## Neste repositório abordamos os segintes tópicos:

- H1 na mesma página
- Atributos lang e alt
- CSS interfere no leitor de tela? Listas e display: none
- Roles e arias
- 

### H1 na mesma página
Atualmente é aceitável, semanticamente, uma página de um site possuir diversos 'h1' distribuídos em seções independentes.
Contudo, isso pode prejudicar a acessibilidade do site pois podem ler apenas o primeiro 'h1' ou simplesmente se perderem, e por consequência prejudicar a experiência do usuário no site. Principalmente usando o atalho para ler o que seria o ponto mais importante do site (comumente H + 1).

```
<h1>"Título do site"</h1>
    <h2>"Resumo do que se trata"</h2>
    <h2>"Título da seção"</h2>
        <h3>"Subtitulo hierarquia 2"</h3>
            <h4>"Subtítulo hierarquia 3"</h4>
```
> OBS.: Não tem um padrão exato a ser seguido, vai depender de  como queremos passar a mensagem para o usuário.
>Tomar cuidado com a marcação de conteúdo quando estamos utilizando elementos HTML5. Vale mais por uma 'div' do que usar um 'aside' ou 'details' erroneamente. 


### Atributos leang e alt
Podemos evitar sotaques com atributo lang. O atributo alt se refere a "texto alternativo" vinculado a imagens.  
É útil não apenas para usuários de leitor de tela, mas também se por algum motivo a imagem não for carregada na página. 
Com o apoio de texto, criamos uma experiência melhor na interface.

```
<html lang="pt-br">
<img src="img/android.png" alt="Android">
<a href="#" class="cabecalho-logo" title="Logotipo da Apeperia">
<b>todxs</b>
```
>OBS.: Utilizar o lang de forma correta, evitando sotaques para o ouvinte, caso tenha um fraguimento em outro idioma colocar o atributo lang na 'div'.
>Importante separar as responsabilidades entre o que é visual e o que é conteúdo. 
>Iconografia normalmente tem caráter visual, e o que for visual utilizar CSS, seja usando um background-image ou um ::after/::before.
>Se for interessante que a imagem seja indexada por buscadores, a imagem deve ser deixada no HTML. Porém, o alt ainda precisa ser declarado, mesmo que sem valor, para que o leitor de tela ignore a imagem.
>Os leitores de tela lêem a desc dos SVGs, isso usando o mouse, é recomendável adicionar um title no 'a' do arquivo svg e deixar a desc quando necessário.

### CSS interfere no leitor de tela? Listas e display: none
O CSS pode influenciar totalmente em como o leitor de tela interpreta e lê o conteúdo para seu usuário.
Pensando em listas acessíveis, (elemento < ul > por exemplo) podemos evitar que ele fale “bolinha” a cada item lido com a declaração list-style: none;
Quando queremos deixar nossa página mais acessível, devemos nos preocupar em tornar nosso código semântico e se o leitor de tela precisa ler o que estamos escondendo.

```
.secaoPlanos-plano-itens {
    /*list-style: disc;*/
    list-style: none;
}
.contatoCampo-checkbox {
  /*display: none;*/
  /*visibility: hidden;*/
  position: absolute;
  left: -9999;
  opacity: 0;
}
```
>OBS.: CSS também infuencia nos leitores de tela como é o exemplo do trecho de código assima. Onde o atribuito disc esta sendo lido como "bolinha".
>display: none;| visibility: hidden; - Devemos ter cuidado com essa declaração pois apesar de ser prática, pode inviabilizar o acesso para usuários de leitores de tela.

### Roles e arias
Fizemos um link âncora para uma tag < h1 >, que é o conteúdo principal ou resumo do site.
E o atributo role que serve para atribuir papeis aos elementos no nosso código, por exemplo, se queremos que uma < div > seja interpretada como um botão pelo leitor de tela, escreveremos role="button".
Através da WAI-ARIA podemos mudar o modo de relacionar o link com a < figpcation >, ou seja, que a legenda funcione como rótulo do link.

```
<a href="#conteudoPrincipal" class="pularNavegacao">Pular para conteúdo principal</a>
 <h1 class="secaoDestaque-titulo" id="conteudoPrincipal">
        APLICATIVOS NA MEDIDA
      </h1>
<main class="conteudo" role="main">


<a href="http://blog.apeperia.com.br/design/conheca-primeiras-etapas-criacao-logotipo-teste-teste"
          class="secaoDestaques-link" aria-labelledby="tituloDestaque1">
    <figure class="secaoDestaques-destaque">
        <img src="img/comecando-criar-logotipo.png" class="secaoDestaques-destaque-img"
        alt="Ferramentas de Design. Ilustração">
            <figcaption class="secaoDestaques-destaque-titulo" id="tituloDestaque1">
              Conheça as primeiras etapas na criação de um logotipo
            </figcaption>
    </figure>
</a>
```
>Para facilitar o direcionamento dos leitores de tela para o conteúdo principal podemos fazer de duas maneiras, utilizando um link < a > e o referenciando pelo ID na tag desejada 
>ou podemos atribuir uma role (escopo) em uma div como principal, dizendo que é um main, ou seja mudar a semântica de um elemento.
>Podemos usar html descritivo fazendo uso de "figure" e "figcaption" ao usar apenas "div" e "p", pois facilita a interpretação dos leitores de tela. Além disso utilizamos o 
>aria-labelledby="tituloDestaque1" (rotulado por) Atributo para adicionar semântica ao HTML e referênciar o link ao título do conteúdo e assim não repitir o "alt".

### Links de Apoio

| Link | Descrição |
| ------ | ------ |
|[NVDA](https://www.nvaccess.org/) |Leitor  de tela mais utilizado |
|[JAWS](https://www.freedomscientific.com/Products/software/JAWS/) |Leitor de tela |
|[VoiceOver](https://www.apple.com/br/accessibility/mac/vision/) |Leitor de tela  para Mac |
|[WebAIM](https://webaim.org/) |Site focado em acessibilidade web |
|[Palestra da Marina Domingues](https://pt.slideshare.net/MarinaDomingues7/acessibilidade-por-que-deixarmos-de-ser-amadores-para-um-pblico-que-espera-mais-de-ns)  |[Slides] Acessibilidade e números  |
|[Estudo Inclusivo](http://www.estudoinclusivo.com.br/) |Estudo Brasileiro sobre o uso de leitores de tela |
|[Palestra](https://www.youtube.com/watch?v=5FJJuEVt5sA)  |Lang e Alt - Reinaldo Ferraz  |
|[Blog](http://www.reinaldoferraz.com.br/acessibilidade-seo-e-svg/)  |Acessibilidade, SEO e SVG - Reinaldo Ferraz |
|[CSS in Action](https://webaim.org/techniques/css/invisiblecontent/)  |Invisible Content Just for Screen Reader Users  |
|[Atalhos NVDA](https://webaim.org/resources/shortcuts/nvda)  |Keyboard Shortcuts for NVDA  |
|[Palestra da Vanessa Me Tonini](https://www.youtube.com/watch?v=l_NBdzqYm44)  |WAI-ARIA: Acessibilidade em tempo real  |
|[WAI ARIA basics](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/WAI-ARIA_basics#What_is_WAI-ARIA)  |Documentação WAI ARIA|
|[The Roles Model](https://www.w3.org/WAI/PF/aria/roles)  |Lista com Roles Existentes  |
|[Basic screen reader commands for accessibility testing](https://developer.paciellogroup.com/blog/2015/01/basic-screen-reader-commands-for-accessibility-testing/)  |Atalhos básicos de leitores de tela para testes de acessibilidade (inglês)  |
|  |  |
|  |  |



License
----

MIT


**Free Software! ;)**

