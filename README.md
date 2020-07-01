# Acessibilidade Web

![Build Status](https://travis-ci.org/joemccann/dillinger.svg)[](https://github.com/nathy-mesquita/web-accessibility-front-end)
## Neste repositório abordamos os segintes tópicos:

- H1 na mesma página
- Atributos lang e alt
- 
- 
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
Podemos evitar sotaques com atributo lang e o atributo alt se refere a "texto alternativo" vinculado a imagens.  
É útil não apenas para usuários de leitor de tela, mas também se por algum motivo a imagem não for carregada na página. 
Com o apoio de texto, criamos uma experiência melhor na interface.

```
<html lang="pt-br">
<img src="img/android.png" alt="Android">
<a href="#" class="cabecalho-logo" title="Logotipo da Apeperia">
```
>OBS.: Utilizar o lang de forma correta, evitando sotaques para o ouvinte, caso tenha um fraguimento em outro idioma colocar o atributo lang na 'div'.
>Importante separar as responsabilidades entre o que é visual e o que é conteúdo. 
>Iconografia normalmente tem caráter visual, e o que for visual utilizar CSS, seja usando um background-image ou um ::after/::before.
>Se for interessante que a imagem seja indexada por buscadores, a imagem deve ser deixada no HTML. Porém, o alt ainda precisa ser declarado, mesmo que sem valor, para que o leitor de tela ignore a imagem.
>Os leitores de tela lêem a desc dos SVGs, isso usando o mouse, é recomendável adicionar unm title no 'a' do arquivo svg e deixar a desc quando necessário.



### Links de Apoio

| Link | Descrição |
| ------ | ------ |
|  [NVDA](https://www.nvaccess.org/) | Leitor  de tela mais utilizado |
| [JAWS](https://www.freedomscientific.com/Products/software/JAWS/) | Leitor de tela |
| [VoiceOver](https://www.apple.com/br/accessibility/mac/vision/) |Leitor de tela  para Mac |
| [WebAIM](https://webaim.org/) | Site focado em acessibilidade web |
|[Palestra da Marina Domingues](https://pt.slideshare.net/MarinaDomingues7/acessibilidade-por-que-deixarmos-de-ser-amadores-para-um-pblico-que-espera-mais-de-ns)  |[Slides] Acessibilidade e números  |
|[Estudo Inclusivo](http://www.estudoinclusivo.com.br/) |Estudo Brasileiro sobre o uso de leitores de tela |
|[Palestra](https://www.youtube.com/watch?v=5FJJuEVt5sA)  |Lang e Alt - Reinaldo Ferraz  |
|[Blog](http://www.reinaldoferraz.com.br/acessibilidade-seo-e-svg/)  | Acessibilidade, SEO e SVG - Reinaldo Ferraz |
|  |  |
|  |  |




License
----

MIT


**Free Software! ;)**

