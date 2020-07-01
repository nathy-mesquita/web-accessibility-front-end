# Acessibilidade Web

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://github.com/nathy-mesquita/web-accessibility-front-end)
## Neste repositório abordamos os segintes tópicos:

- H1 na mesma página
- 
- 
- 
- 

### H1 na mesma página
Atualmente é aceitável, semanticamente, uma página de um site possuir diversos <h1> distribuídos em seções independentes.
Contudo, isso pode prejudicar a acessibilidade do site pois podem ler apenas o primeiro <h1> ou simplesmente se perderem, e por consequência prejudicar a experiência do usuário no site. Principalmente usando o atalho para ler o que seria o ponto mais importante do site (comumente H + 1).

```sh
<h1>"Título do site"</h1>
    <h2>"Resumo do que se trata"</h2>
    <h2>"Título da seção"</h2>
        <h3>"Subtitulo hierarquia 2"</h3>
            <h4>"Subtítulo hierarquia 3"</h4>
```
> OBS.: Não tem um padrão exato a ser seguido, vai depender de  como queremos passar a mensagem para o usuário.
>Tomar cuidado com a marcação de conteúdo quando estamos utilizando elementos HTML5. Vale mais por uma <div> do que usar um <aside> ou <details> erroneamente. 


### Links de Apoio

| Link | Descrição |
| ------ | ------ |
|  [NVDA](https://www.nvaccess.org/) | Leitor  de tela mais utilizado |
| [JAWS](https://www.freedomscientific.com/Products/software/JAWS/) | Leitor de tela |
| [VoiceOver](https://www.apple.com/br/accessibility/mac/vision/) |Leitor de tela  para Mac |
| [WebAIM](https://webaim.org/) | Site focado em acessibilidade web |
|[Palestra da Marina Domingues](https://pt.slideshare.net/MarinaDomingues7/acessibilidade-por-que-deixarmos-de-ser-amadores-para-um-pblico-que-espera-mais-de-ns)  |[Slides] Acessibilidade e números  |
|[Estudo Inclusivo](http://www.estudoinclusivo.com.br/) |Estudo Brasileiro sobre o uso de leitores de tela |
|  |  |
|  |  |





License
----

MIT


**Free Software! ;)**

