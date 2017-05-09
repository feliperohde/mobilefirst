
## Como desenvolver mobile-first
O desenvolvimento mobile first ainda é motivo de pesadelos para designers e desenvolvedores; Para designers pq pensam que terão que fazer um brainstorm totalmente diferente ou que perderão parte da criação por não pensar em telas maiores e para desenvolvedor por pensar em como vai desenvolver tudo aquilo do desktop para o celular. A criação e desenvolvimento mobile-first é basicamente criar coisas de maneira progressiva ao invés de adaptar toda a parafernalha de desktops para celulares, isso sim seria doloroso, não tem haver com ignorar telas maiores ou migrar features desenvolvidas para elas, e sim pensar nas telas maiores depois.

Ao final deste testo teremos uma pagina simples, mobile-first responsiva que poderemos ter como base para projetos no futuro, e principalmente, uma página que vamos gostar de acessar no celular.

A ideia aqui não é criar um novo framework, pois já existem vários que levam a tarefa mobile-first bem a sério e funcionam muito bem, a exemplo o famoso bootstrap; Mas sim entender o por que das coisas serem feitas do jeito que são, inclusive nesses frameworks, para melhorar a criação e desenvolvimento e evitar mal uso de ferramentas assim.

Para isso revisaremos alguns pontos e vamos aplicando em nosso código.

### Dominio e urls
É comum encontrar sites que usam segmentos ou subdomínios para servir conteúdo para dispositivos móveis. Isso geralmente acontece pois o site foi migrado para dar suporte a dispositivos móveis, então para separar o código e infraestrutura cria-se essa separação; Isso não é necessário, o usuário deve ter o sentimento de estar acessando o mesmo site e o mesmo conteúdo, esse tipo de abordagem pode gerar um pouco de insegurança quanto ao conteúdo que está sendo mostrado, não é uma má pratica mas o conteúdo móvel pode ser servido na mesma url mesmo quando este foi adaptado de um site desktop.

### ResponsiveUI e componentes reutilizáveis
Desenvolvedor e designer devem estar em sintonia aqui, não é tao fácil criar um elemento gráfico que se adapte em todos os contextos, mas é preciso, pois não queremos ter esforço para adaptar a informação de um celular pra um tablet ou desktop, na verdade não queremos faze-lo; Um componente gráfico responsivo tem muita responsabilidade e ele deve diminuir ao máximo o esforço para adaptação de conteúdo entre as telas.

Os cards, eles cairam no gosto, são simples, podem acomodar imagens, videos, textos, botoes... São amigáveis a gestos, agradam visualmente e mais do que isso: os usuários entendem os cards; São um ótimo exemplo de componentes visuais reutilizáveis e responsivos.

Também são fácies de serem escritos.

https://material.io/guidelines/components/cards.html

### É tudo lista
Mais alguém reparou que a web de celulares (e não só de celulares) e apps são basicamente listas de coisas? Lista de texto, lista de imagem, lista de texto e imagem, lista horizontal e vertical, lista de listas, lista de opções, lista de reações, lista de paginas... é tudo lista, elas estão em todos os lugares mostrando listas de todo o tipo de informação as vezes de mais de um tipo ao mesmo tempo.
As listas estão juntas a outros dois pilares fundamentais para apresentar informações, os textos e as imagens e videos; Então é importante imaginarmos nossos componentes visuais no design e no desenvolvimento como listas, esses componentes básicos serão amplamente reaproveitados, devemos ter muito foco neles no inicio.

A gente usa e não percebe que é uma lista, mas é, o feed do facebook, os cards de apps nas lojas do google e app store, os resultados do google, o alt+tab do OS, está em toda parte e tem um motivo pra isso: Listas são naturais, existiam muito antes de surgir o primeiro computador, estão no nosso dia-a-dia além dos computares e celulares, não exigem esforço para serem compreendidas, faz parte do setup básico da nossa mente.

E o que é mais legal, listas são nativas! são fáceis de ser escritas, ocupam pouquíssima marcação, não exigem muito estilo para ficarem bonitas e juntando elas com outras coisas básicas podemos melhorá-las muito, adicionar comportamento e gestos básicos como slide/swipe, que maravilha!

Sempre que a informação puder estar em uma lista, coloque-a em uma lista, apresente-a bem e todos saberão usar.

### Setup básico
A maioria dos browsers móveis modernos usam uma forma de exibir sites não otimizados para dispositivos móveis, isto é, eles definem um viewport maior para o site e acomodam todo o conteúdo escalado, o usuário então pode fazer zoom na área de interesse usando os gestos nativos de seu aparelho, isso proporciona uma melhor usabilidade para sites que não são otimizados para celulares, essa forma de exibição se tornou padrão nos navegadores; Esse comportamento é otimo para conteúdo nao otimizado para celulares, mas como estamos otimizando nosso conteúdo para navegadores móveis, devemos informar a eles a largura do viewport que ele deve usar.

Para isso usamos a metatag de nome viewport; Essa tag aceita os seguintes valores em seu conteúdo:
**width** - serve para definir a largura do viewport virtual
**device-width** - serve para resgatar a largura do viewport do device
**height** - serve para definir a altura do viewport virtual
**device-heigh**t - serve para resgatar a altura do viewport do device
**initial-scale** - serve para definir o escalonamento (zoom) inicial do browser onde 1 é equivalente a sem zoom
**minimum-scale** - serve para definir o minimo de zoom que o site pode ter onde 1 é equivalente a sem zoom
**maximum-scale** - serve para definir o maximo de zoom que o site pode ter onde 1 é equivalente a sem zoom
**user-scalable** - serve para definir se usuário poderá usar os gestos para dar zoom ou não, seus valores sao "yes" ou "no"

É muito importante não setar valores para **minimun-scale**, **maximum-scale** e **user-scale**, visto que poderá causar muito desconforto para o usuário que quer dar zoom ou tirar zoom no site.

Então temos a seguinte metatag para adicionar ao nosso header:
```html
<meta name="viewport" content="width=device-width, initial-scale=1" />
```

Nela, dizemos para o browser que ele vai criar um viewport virtual da largura da tela do device e que o zoom inicial será 1, ou seja, sem zoom; Dessa forma o navegador móvel não tentará escalonar o conteúdo da nossa pagina automaticamente, ainda que através dos gestos do device o usuário possa dar zoom ou tirar zoom de nosso conteúdo.

Outra metatag interessante é a **theme-color**, que faz com que a toolbar de devices móveis fique de uma determinada cor, possibilitando o front-end adequar a cor da toolbar para a paleta de cores do site; O conteúdo desta tag aceita cores em hexadecimal.
```html
<!-- Chrome, Firefox OS and Opera -->
<meta name="theme-color" content="#4285f4">
<!-- Windows Phone -->
<meta name="msapplication-navbutton-color" content="#4285f4">
<!-- iOS Safari -->
<meta name="apple-mobile-web-app-status-bar-style" content="#4285f4">
```
<iframe width='100%' height='265' scrolling='no' title='Exemplo Mobile first' src='//codepen.io/feliperohde/embed/rmzeNX/?height=265&theme-id=0&default-tab=html,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/feliperohde/pen/rmzeNX/'>Exemplo Mobile first</a> by Felipe Rohde (<a href='http://codepen.io/feliperohde'>@feliperohde</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

### Gestos, eventos e ações
Os sistemas operacionais de celulares estão cada vez mais usando gestos para realizar ações e é importante refletir isso em nossas páginas, pois não precisaremos ensinar o usuário a usar nosso site; O básico: swipe, longpress, tap e doubletab são os gestos mais usados e que praticamente todo usuário deve saber usar e o que esperar deles.

Em nosso exercício vamos encontrar uma forma de usa-los.

<iframe height='265' scrolling='no' title='Exemplo Mobile first - Eventos' src='//codepen.io/feliperohde/embed/WjdZMd/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/feliperohde/pen/WjdZMd/'>Exemplo Mobile first - Eventos</a> by Felipe Rohde (<a href='http://codepen.io/feliperohde'>@feliperohde</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

No exemplo acima, adicionamos um simples evento de longpress nos itens da nossa todo-list para exibir algumas informações e opções uteis para o contexto.

<iframe weidth="100%" height='265' scrolling='no' title='Exemplo Mobile first - Gestos e ações' src='//codepen.io/feliperohde/embed/oWGjEy/?height=265&theme-id=0&default-tab=js,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/feliperohde/pen/oWGjEy/'>Exemplo Mobile first - Gestos e ações</a> by Felipe Rohde (<a href='http://codepen.io/feliperohde'>@feliperohde</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

Já neste exempo, aproveitamos o scroll da lista para simular o gesto "pan" dos celulares, parecido com swipe.

### Chamadas de assets
Aqui, além de respeitar as boas práticas sobre como fazer as chamadas de css e js, aquilo sobre por scripts no final da página sempre que possível mantendo no head somente chamadas de assets que setam a estética inicial do site, polyfills e coisas que infuenciarão no parseamento do restante do documento.

É interessante separar os arquivos de css para displays maiores, mas pq? Usando breakpoints responsivos podemos fazer com que somente o desktop realize alguma tarefa estetica, mas se esta regra estivar no mesmo arquivo css, mesmo que dispositivos móveis ignorem a regra, ele ainda terá que baixar o arquivo inteiro, é um questão de payload, se o device não precisa da regra ou não a interpretará ele nao deve fazer download não é?
```html
<link rel="stylesheet" type="text/css" href="style.css" media="screen, handheld" />
<link rel="stylesheet" type="text/css" href="enhanced.css" media="screen  and (min-width: 40.5em)" />
```

Desta forma, o navegador somente fará download do arquivo quando a largura do viewport for proporcional a 40.5em (que é basicamente 648px, veremos isso mais pra frente).

Infelizmente na tag script o atributo media não é suportado e não sabemos se um dia será, então para carregar javascript baseados em proporções de tela ainda é um trabalho que pode se tornar complicado, mais ainda se for o back-end quem inclui esses assets no front.

<iframe width="100%" height='265' scrolling='no' title='Carregando script somente no desktop' src='//codepen.io/feliperohde/embed/ybzLoJ/?height=265&theme-id=0&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/feliperohde/pen/ybzLoJ/'>Carregando script somente no desktop</a> by Felipe Rohde (<a href='http://codepen.io/feliperohde'>@feliperohde</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

Neste exemplo simples, verifica-se se o evento **ontouchstart** está disponível na janela e se não escreve-se no DOM um novo script, fazendo com que o navegador baixe esse arquivo e disponibilize-o para  a pagina.

<iframe width="100%" height='265' scrolling='no' title='Carregando script somente no desktop baseado em proporção' src='//codepen.io/feliperohde/embed/zwEYEd/?height=265&theme-id=0&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/feliperohde/pen/zwEYEd/'>Carregando script somente no desktop baseado em proporção</a> by Felipe Rohde (<a href='http://codepen.io/feliperohde'>@feliperohde</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

Já neste exemplo, podemos informar em qual proporção o script será adicionado.

### Os links
Exitem algumas pequenas mudanças em links que podem melhorar a experiência para o usuário que nevega pelo seu smartphone; O browser disponibiliza algumas formas de interação mais intima com o aparelho, links de telefone e até mesmo links para aplicativos instalados. parece pouco mas faz diferença.

Podemos fazer uma chamada para o discador do smartphone simplesmente criando um link como esse:

```html
<a href="tel:1-562-867-5309">1-562-867-5309</a>
```
extra: O seo desta para este tipo de informação pode ser otimizado para que quando for encontrada por buscadores como o google, um card de ações seja exibido:

```html
<div itemscope itemtype="http://schema.org/LocalBusiness">
    <h1 itemprop="name">Beach Bunny Swimwear</h1>
    Phone:
      <span itemprop="telephone">
        <a href="tel:+18506484200">
           850-648-4200
        </a>
      </span>
  </div>
```
https://css-tricks.com/the-current-state-of-telephone-links/

De forma muito semelhante podemos chamar o app do whatsApp desta forma:
<a href="whatsapp://send?text=Hello World!&phone=+9198********1">wpp</a>
Esse link pode ser usado para compartilhar informaçao atravéz do wpp, é incomum usar o parametro phone pois o wpp somente funciona com os contatos que o usuário tem no celular, não sendo possível que um link para uma conversa de um contato inexistente na lista pessoal funcione.

Links para email também são muito uteis, e ja é possivel através do link passar parametros para o preenchimento do formulario de envio de email:
 <a href="mailto:someone@yoursite.com?cc=someoneelse@theirsite.com, another@thatsite.com, me@mysite.com&bcc=lastperson@theirsite.com&subject=Big%20News&body=Body-goes-here">Email Us</a>
 Desta forma, o app encarregado por envios de email no celular será chamado e automaticamente os campos informados ja estrão preenchidos para o usuário, lindo!

### Os inputs
http://bradfrost.com/blog/mobile/better-numerical-inputs-for-mobile-forms/
Ainda é comum encontrar formulários cheios de input text, input text pra todo tipo de informação; Problema disso não é nem a liberdade de o usuário poder digitar qualquer coisa no campo, a ideia de usar os input types adequados não é a validação e sim o conforto do contexto; Todos os browsers modernos possúem suporte para os input types mais conhecidos, disponibilizando para o usuário um teclado contextual muito mais adequado para o tipo de informação que deve ser inserida, isso é **incrível**.


```html
  <!--   html inputs -->
  <input type="number" min="0" max="100" step="10" value="30" pattern="[0-9]*" />
  <input type="number" />
  <input type="time"/>
  <input type="url"/>
  <input type="color"/>
  <input type="date"/>
  <input type="datetime-local"/>
  <input type="email"/>
  <input type="month"/>
  <input type="range" min="0" max="10" />
  <input type="search"/>
  <input type="tel"/>
  <input type="week"/>
```

### Selects e elementos personalizados
Semelhante as máscaras, gosto de pensar que selects padrao iram satisfazer a todos os usuários, ja um select personalizado pode deixar alguém irritado.
Um dos maiores problemas de selects personalizados em dispositivos móveis é que eles tiram o comportamento padrão do elemento quando deveriam somente mudar a estética; Cada sistema operacional trabalha de uma maneira diferente para mostar a lista de um select e os usuários estao acostumados com isso e esperam qua isso funcione; No IOS por exemplo, quando clico em um select o sistema operacional mostra uma lista, semelhante ao bottom sheet do android, disponibilizando sempre a informaçao do select neste padrão, isso é prático e fácil de usar, alem disso, esperamos que funcione assim, pois todo o ecossistema envolta funciona assim.

A aparência estética de um select, input, input radio ou checkbox podem ser alteradas com css. Existem atributos nativos que permitem seleção de datas e horários.

Um comportamento extra pode ser adicionado desde que não remova um comportamento existente, ou ainda, desde que tenhamos a responsabilidade de tratar esse comportamento de forma a respeitar o ecossistema de cada usuário.

##### extra:
Um atributo que pode melhorar a experiencia é o **autocapitalize**, que como o nome sugere, coloca em caixa alta caracteres, palavras ou frases.

```html
 <input type="text" id="name" autocapitalize="words">
 <input type="text" id="initials" autocapitalize="characters">
 <textarea id="todolist" autocapitalize="sentences">
```

### Quanto as máscaras?
Gosto de pensar que um input sem máscara nunca irá prejudicar ninguém enquanto que um input mascarado sem dúvida deixará uma parte dos usuários desconfortável e por vezes os impossibilitará de inserir a informação, fazendo-os desistirem do preenchimento.
Máscaras tem a função de instruir o usuário sobre a forma de preenchimento do input e também formatar a informação que está sendo inserida; Problema é que o usuário não sabe se tem que inserir a informaçao de acordo com o placeholder da máscara ou se ela o fará automaticamente; Alguns usuários gostam de digitar a pontuaçao e a máscara remove, tornando o compartamento confuso pois não se sabe se algo deu errado;

O usuário não deve precisar aprender a usar um input, ele só precisa poder digitar.

Existem muitos plugins de mascaramento, além dos kbites a mais que será necessário que o usário baixe, esses plugins mudam muitos comportamentos nativos dos campos fazendo com que o usuário tenha que reaprender o funcionamento.

A instrução de como formatar um input devem estar no atributo placeholder e a formatação para melhor leitura pode ser feita depois que termina-se o preenchimento, no evento blur do input.

Inputs ja suportam o atributo pattern, que apesar de não atuar como máscara, dá suporte de validação para a informação inserida, impossibilitando a submissão de informações em desacordo.

### Modais e alertas
É preciso ter cuidado com esses dois elementos, a informação tem que ser muito importante para estar em uma modal e mais ainda para estar em um alerta e o mais importante, não abra modais se o usuário não pedir.

Alertas continuam sendo úteis e não tente transformar um alerta em uma modal, existe um componente nativo no sistema operacional do celular para isso com o qual nosso querido usuário já está habituado;

A estética deve se diferente também, a tela é pequena e devemos aproveita-la ao máximo, uma modal no celurar vai parecer uma nova tela, podemos usar um gesto de swipeDown para fecha-la e uma transição pode dar instrução ao usuário de que aquilo é uma modal e não uma nova página.


### Transições e animações
O sensação de movimento e transições entre os elementos aumenta muito a imersão e entendimento da informação que se quer mostrar, mas novamente, em um celular não há muito espaço para piruetas e devemos nos ater ao básico.

Se for fazer algum efeito, que este possa de alguma forma educar o usuário sobre o significado/representação do elemento que esta sendo animado.

Animar somente por animar não tem muito sentido. A animação tem que dizer algo pro usuário ou suavizar o aparecimento de um novo elemento na tela.

### As medidas
A tipografia é parte essencial no design e também no desenvolvimento, seu principal atributo é o tamanho; Quando se lê um jornal ou revista o tamanho da fonte é fixo, se estiver pequeno posso traze-lo mais para perto ou mais para longe se estiver grande. Na web precisamos de um tamanho relativo, pois existem muitos tamanhos de tela.
Lembra-se de quanto acessava sites e mesmo aplicando zoom a fonte permanecia do mesmo tamanho? Hoje esse isso não acontece mais devido a evolução dos browsers.

Ainda há dificuldade em entender as medidas relativas para a tipografia na web, pensa-se as vezes que as medidas relativas são responsáveis por uma ***adaptaçao mágica*** de tamanhos de um device para outro, na verdade não é bem isso; Por exemplo, as vezes um titulo deve ter a proporção de 24px no celular e de 40px no desktop e espera-se que isso aconteça simplesmente por mudar a medida para uma medida proporcional, e acaba gerando decepção pois não é isso que acontece; Se no desktop foi previsto um titulo proporcionalmente maior, devo setar um tamanho maior para o desktop, uma medida relativa não fará a magia, ao menos não toda a mágica.
Medidas relativas, tem muito mais haver com o padrão do browser e o zoom, por padrão, os navegadores tem a seguinte regra: 1em = 12pt = 16px = 100%, mas nada me impede de mudar isso e setar o font-size padrão do meu browser para 18px.

E isso é útil pois assim como posso trazer o jornal mais pra perto, na web posso aumentar o tamanho padrão; Dessa forma elementos com medidas relativas respeitarão a nova medida padrão do browser ao contrário de uma medida fixa em px.
no exemplo abaixo, temos dois titulos com o mesmo tamanho, mas o que acontece se mudarmos o tamanho padrão do browser? no exemplo fazemos isso setado o font-size no html e no body.

<iframe width="100%" height='265' scrolling='no' title='some unit example' src='//codepen.io/feliperohde/embed/gWRjXO/?height=265&theme-id=0&default-tab=html,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/feliperohde/pen/gWRjXO/'>some unit example</a> by Felipe Rohde (<a href='http://codepen.io/feliperohde'>@feliperohde</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

Esse tipo de medida é muito mais comum de se aplicar para a tipografia, mas é recomendável também que margens, paddings e bordas também respeitem a medida relativa.

### Breakpoints
Acima! Pare de usar max-with em seus mediaqueries, não é legal; Criar intervalos nos mediaqueries também é um sinal de que algo no design falhou.

Quando estamos desenvolvendo pensando em mobile-first, a principal coisa que se deve ter em mente é que as media queries devem ser sempre pensadas para resoluções **a partir de** e não **abaixo de**, mas por que?
Se estamos desenvolvendo para o celular, façamos o código para o celular, não há motivo para criar um breakpoint para o celular sendo que ele é o principal dispositivo para o qual estamos desenvolvendo, façamos então todas as regras de estética do celular serem as regras padrão, que ficarão fora de qualquer breakpoint; Logo quando o diagramação ou conteúdo não for mais bem apresentada conforme acessamos o conteúdo em telas maiores, mapeamos isso e então vejamos a partir de qual ponto precisaremos reaver nossas regras ou incrementa-las.

Use mediaqueries sempre com min-width, isso torna obrigátorio que escrevamos nosso código primeiro pra telas menores, consequentemente escrevemos um código mais limpo e simples, separamos as responsabilidades de cada breakpoint e o reaproveitamento de propriedades aumenta muito.

<iframe width="100%" height='265' scrolling='no' title='Mobile first - Media queries' src='//codepen.io/feliperohde/embed/aWygLV/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/feliperohde/pen/aWygLV/'>Mobile first - Media queries</a> by Felipe Rohde (<a href='http://codepen.io/feliperohde'>@feliperohde</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

Uma dica também é não colocar o media querie dentro do componente, e sim o componente dentro do media querie, mas pq? Existem casos em que por exemplo, um status irá modificar  o componente; Uma classe 'is-loading' pode ser adiconada ao componente e essa classe modificará seus filhos em alguma largura, não teriamos como modificar o elemento se o media querie estivesse dentro do componente, teriamos que criar uma nova variação do componente sendo filho desse modificador de estatus e colocar o novo media querie dentro dele e isso é eliminado se o componente estiver dentro do media querie.

<iframe width="100%" height='265' scrolling='no' title='Mobile first - Media queries' src='//codepen.io/feliperohde/embed/qmXzoY/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/feliperohde/pen/qmXzoY/'>Mobile first - Media queries</a> by Felipe Rohde (<a href='http://codepen.io/feliperohde'>@feliperohde</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

### Pare de usar breakpoints para padrões de tela
A cada dia surgem novos dispositivos com novos tamanhos e padrões de tela, em algum ponto se tornará insustentável suportar breakpoints para toda essa gama de telas, hoje são os celulares e tables, amanhã talvez as tvs ou os relógios de pulso e por que não óculus de realidade virtual?, então qual a solução para ajustar o conteúdo?

Os breakpoints devem ser usados para o conteúdo e não para as telas, ficou confuso? calma, os breakpoints ainda são para uma medida de tamanho de tela mas não para devices. O ponto é que devemos ter como base o nosso conteúdo, deve-se criar uma ponto de interrupção somente quando e se o conteúdo exigir; O conteúdo deve ser nosso guia para criar os breakpoints, por exemplo, se a exibição e diagramação do conteúdo ainda esta funcionando bem no tablet, por que eu deveria criar um breakpoint para os tablets?

### Use medidas relativas para os media queries

Assim como as medidas de fontes, as medidas de para media queries devem ser relativas, visto que o usuário pode querer dar zoom no conteúdo, um conteúdo com zoom pode ser adaptado e ter uma visualização ainda melhor...
Um media querie com unidades fixas ignora o zoom visto que uma pagina com zoom ainda continua tendo a mesma quantidade de pixeis; Por que isso é importante? Pense que o usuário esta dando zoom em determinado artigo, isso o fará perder acesso a sidebar por exemplo ou ainda criar aquela barra de rolagem horizontal que as vezes é muito desconfortável, se minha media querie for relativa ao conteúdo que cabe na pagina, quando adicionar ou remover zoom os mediqueries farão o trabalho de ajustar o conteúdo.

### Os icones
![enter image description here](http://blog.froont.com/content/images/2014/11/09_Vectors-vs-Images-1.gif)
Logo quando começamos a adaptar conteúdo para diversos tipos de tela, era muito comum usar um sprite@2x, por exemplo, para dar suporte a telas retina, mas não temos controle sobre as telas que surgirão, isso tem evoluido muito rápido, e ao menos para icones e assets que estarão sempre no nosso site, precisamos de um jeito mais consistente para exibir imagens.

O svg é uma delas, e ele tem suporte básico a partir do IE9+, sua renderização é proporcional e não interpolada como das imagens, portando não é necessário um novo svg para exibir a mesma imagem em uma tela com densidade maior ou  se simplesmente queremos exibir uma imagem maior.

Os arquivos de fonte são outra forma, e para ícones é o preferido no desenvolvimento, ferramentas como **icomoon** e  **fontawesome** cairam no gosto tanto de designers quanto dos desenvolvedores.

### Os fontfaces
Já entrou em um site que aparentemente estava vazio, quando de repente, todo o conteúdo aparece; Muitas vezes isso acontece pois o conteúdo que está ali esta usando uma fonte que não é nativa.

Não há problemas em carregar uma fonte para o site, desde que nao seja uma dúzia, mas existe problema em não dar fallback para elementos que ussam essa nova fonte; A propriedade **font-family** do css permite que inúmeras familhas de fontes seja atribuida a ela, fazendo com que, da direita pra a esquerda o browser tente encontrar a fonte para exibir o conteúdo. Logo um elemento com font-face, principalmente se for um elemento que exibe um conteúdo, um artigo por ex, deve ter uma font-family de fallback, para que seja usada enquanto o browser baixa a nova fonte ou mesmo se o browser nao conseguir baixar a fonte ou nao encontra-la.

```css
font-family: "My awesome font", "Times New Roman", Georgia, Serif;
```

Entendemos que é meio estranho o conteúdo carregar com uma fonte e depois mudar, mas ainda é melhor do que não conseguir ler nada. Dessa forma ainda é possível repensar font-faces para conteúdo. Ainda, é possível testar através de javascript se o browser conseguiu fazer download da font ou esta em processo e então talvez avisar nosso querido usuário alguma forma.

document.fonts.onloadingdone
document.fonts.ready.then

### Navegação Menus e elementos com posicionamento fixo

Celulares tem um tamanho de tela limitado, e é comum usar um navigation drawer, hamburger menu, header fixo ou call to action fixos para facilitar o acesso a alguns links e aprimorar a navegação, mas não faça tudo de uma vez, por favor, pois o usuário só vai guardar uma referência de onde estão os links importantes.

A guideline material design possui boas referências para isso, disponibilizando navigation drawer, bottom navigation, floating button e menus contextuais, cada um instiga o usuário para uma ações e comportamentos diferentes.

Na web é comum usar a navigation drawer para exibir uma lista de links internos uteis, como acesso aos principais pontos do site (about, trabalhos, contato) assim como links relacionados ao perfil logado (deslogar, alterar foto)

Em nosso exemplo, criaremos uma lista simples com link + icone e texto junto com um botão flutuante para chamar esse menu e inicialmente ficará off-canvas.

<iframe width="100%" height='265' scrolling='no' title='Exemplo Mobile first - Navegação' src='//codepen.io/feliperohde/embed/zwdqdr/?height=265&theme-id=0&default-tab=html,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/feliperohde/pen/zwdqdr/'>Exemplo Mobile first - Navegação</a> by Felipe Rohde (<a href='http://codepen.io/feliperohde'>@feliperohde</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

### Sliders e carouseis
Dois componentes que podemos dizer que todo site tem, exibem desde listas de imagens a lista de produtos; Mas como usa-lo bem e qual a melhor forma de escrever o código pra isso?

Navegadores móveis não exibem a barra de rolagem, ela só é exibida enquanto o evento scroll esta acontecendo.

Setas são comumente usadas para informar o usuário que existem mais pra se ver, mas esse não é o unico jeito de fazer o usuário perceber a existencia de uma lista escondida em um slider; Um jeito também muito comum de fazer isso é mostrar parte do conteúdo escondido, incentivando o usuário a usar o scroll para verificar o conteúdo, claro que existe aplicaçao para os dois e temos que escolher o melhor jeito de fazer com que o usuário entendar a existencia de conteúdo extra.

Também depende de layout e diagramaçao, um hero slider por examplo é muito melhor apresentado quando ocupa toda a largura da tela, entao nesta caso, o uso das setas vem a calhar; Já em uma listagem de produtos ou produtos relacionados a exibiçao parcial do proximo item se torna mais interessante e deixa a interface mais limpa para o que é importante, o produto; Pode-se ainda instruir o usuário da existencia de conteúdo extra utilizando uma animação que exemplifique o comportamento.

<iframe height='265' scrolling='no' title='Exemplo Mobile first - Sliders e carrouseis' src='//codepen.io/feliperohde/embed/MmvrQq/?height=265&theme-id=0&default-tab=html,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/feliperohde/pen/MmvrQq/'>Exemplo Mobile first - Sliders e carrouseis</a> by Felipe Rohde (<a href='http://codepen.io/feliperohde'>@feliperohde</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

###  Imagens
http://www.responsivebreakpoints.com/

Um dos fatores cruciais em um site é o tempo de carregamento e as imagens tem muita responsabilidade neste ponto, portanto, é importante disponibilizar a imagem certa.

Durante muito tempo isso foi um trabalho árduo, felizmente a web evolui rapido e hoje temos o atributo **srcset** nas imagens, esse atributo permite que coloquemos um pouquinho de regra para que o navegador escolha a url de onde baixar o arquivo.

o jeito mais simples de uso é esse:
<iframe width='100%' height='265' scrolling='no' title='responsive image request example simple' src='//codepen.io/feliperohde/embed/VbWqYw/?height=265&theme-id=0&default-tab=html,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/feliperohde/pen/VbWqYw/'>responsive image request example simple</a> by Felipe Rohde (<a href='http://codepen.io/feliperohde'>@feliperohde</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

Basicamente mantemos o atributo src como fallback e adiconamos duas urls no atributo srcset separadas por virgula, note que ao final de cada url existe um modifiador **1x** ou **2x** separado com um espaço da url; Isso diz ao browser que a url descrita com o modificador 1x deve ser usada quando a densidade de pixels for 1, e a 2x quando for 2 no caso de dispositivos retina.

Mas podemos ir muito mais alem, fazendo srcsets mais elaborados em conjunto com o atributo **sizes**. Esse atributo esta diretamente ligado com o css, e nos permite fazer mediaqueries para nossos sources, veja:

```html
sizes="(min-width: 400px) 80vw, 100vw"
```

com isso estamos informando ao browser que em resoluçoes acima de 400px a imagem ocupará 80% do viewport, caso contrário ela ocupará 100% do viewport. Vale lembrar que isso não dita regra estética, somente para escolha de source.

<iframe width="100%" height='265' scrolling='no' title='responsive image request example medium' src='//codepen.io/feliperohde/embed/RVgEpR/?height=178&theme-id=0&default-tab=html,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/feliperohde/pen/RVgEpR/'>responsive image request example medium</a> by Felipe Rohde (<a href='http://codepen.io/feliperohde'>@feliperohde</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

Então, suponhamos que a tela do navegador tenha 320px de largura e que a densidade de pixels seja 1, qual das duas imagens o navegador escolherá para exibir? vamos fazer as contas.

nosso media querie informa ao browser que acima de 400pacimax de largura a imagem ocupará 80% do viewport, mas estamos abaixo entao o browser sabe que a imagem deverá ocupar 100% do viewport, vejamos

nossa formula: largura da imagem / (fator * (largura do device * densidade de pixels))

375 / (1*(320 * 1)) = *1.171875*  - **(375 dividido por 100% de 320 é igual a)**
1500 / (1*(320 * 1)) = *4.6875* - **(1500 dividido por 100% de 320 é igual a)**

1.17 está mais proximo de 1 (que é a nossa densidade de pixels) entao  para dispositivos com largura de 320px que acessao esta imagem, o navegador fará o download da primeira imagem

e se for uma tela retina? vamos fazer as contas novamente.

375 / (1*(320 * 2)) = 0.5859375 **(375 dividido por 100% de 640 é igual a)**
1500 / (1*(320 * 2)) = 2.34375 **(1500 dividido por 100% de 640 é igual a)**

2.34 esta mais proximo de 2 do que 0.58 entao neste caso o browser fará download da segunda imagem.

mas e se o navegador tirver mais que 400px de largura? dissemos a ele que neste caso as imagem ocupariam 80% do viewport, vamos conferir os calculos para ver qual imagem o browser vai escolher para baixar. vamos imaginar que a largura agora é 900px e que a densidade de pixels é 1.

375 / (.8*(900 * 1)) = 0.5208333333333334 **(375 dividido por 80% de 900 é igual a)**
1500 / (.8*(900 * 1)) = 2.0833333333333335 **(1500 dividido por 80% de 900 é igual a)**

neste caso 0.5 esta mais proximo da nossa densidade de pixel do que 2.08 e o browser fará download da imagem 1; Portanto para uma resoluçao de 900px de largura com densidade de 1px uma imagem de qualidade inferior será exibida, vamos corrigir isso incrementando nosso srcset. Adicionamos uma src para uma imagem com 900px de largura e informamos para o srcset que ela tem 900px de largura usando 900w no final. isso deve resolver o problema.

<iframe width="100%" height='265' scrolling='no' title='responsive image request example medium' src='//codepen.io/feliperohde/embed/Njgeez/?height=265&theme-id=0&default-tab=html,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/feliperohde/pen/Njgeez/'>responsive image request example medium</a> by Felipe Rohde (<a href='http://codepen.io/feliperohde'>@feliperohde</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

mas note que agora em um navegador com largura superior a 375px e 1 de densidade o navegador baixa a imagem com 900px de largura, mas por que? definimos que o fator será de 80% apenas acima de 400px

900 / (1*(376 * 1)) = 2.393617021276596
375 / (1*(376 * 1)) = 0.9973404255319149

900 / (.8*(376 * 1)) = 2.9920212765957444
375 / (.8*(376 * 1)) = 1.2466755319148937

Acontece que o navegador tentará não fazer upscaling caso a regra corrente não seja satisfeita e haja disponível uma imagem maior para ser exibida, e isso pode ser um complicador veja:

<iframe width="100%" height='265' scrolling='no' title='responsive image request example medium' src='//codepen.io/feliperohde/embed/XRgOJJ/?height=265&theme-id=0&default-tab=html,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/feliperohde/pen/XRgOJJ/'>responsive image request example medium</a> by Felipe Rohde (<a href='http://codepen.io/feliperohde'>@feliperohde</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

Por isso é importante criar uma regra satisfatória ou disponibilizar uma ampla gama de imagens com pequenos intervalos.

O que confunde muito aqui é que devido a forte ligaçao com css, somos de certa forma forçados a pensar que o valor do atributo sizes, definirá a largura estética da imagem quando na verdade ela somente dará uma base de calculo para o navegador escolher uma imagem, nada impede de informar ao navegador para que baixe uma imagem com fator de 80% e exibi-la no front com 100% de largura, no entando é recomendável respeitar a proporção informada visto que esse é o motivo dela existir.

Tem um jeito mais fácil de aplicar isso, sem precisar elaborar ou entender todos esses cálculos malucos? sim, veja bem, é muito mais fácil setar somete o srcset para intervalos de imagens e também disponibilizar uma versão em 2x, veja:

<iframe width="100%" height='265' scrolling='no' title='responsive image request example complex' src='//codepen.io/feliperohde/embed/BRZGEL/?height=265&theme-id=0&default-tab=html,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/feliperohde/pen/BRZGEL/'>responsive image request example complex</a> by Felipe Rohde (<a href='http://codepen.io/feliperohde'>@feliperohde</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

Também existem ferramentas para facilitar esse trabalho, uma delas se chama responsivebreakpoints, e foi criada justamente pra salvar-nos desse trabalho:
http://www.responsivebreakpoints.com/

Agora também temos que ter uma pequena infraestrutura para servir toda essa gama de imagens, para isso precisamos de algum endpoint que me devolva imagens redimensionadas para os formatos que preciso, sem precisar, claro, fazer upload de todos esses formatos e sim somente da maior imagem; O thumbor ( http://thumbor.org/) é um otimo canditado para isso, é facil de integrar e existem receitas prontas para subir containers docker com ele, como esta, disponibilizada no github:
https://github.com/APSL/docker-thumbor

seguindo o exemplo do repositório, após implementado, nossas urls na srcset ficariam assim:

```html
/unsafe/100x100/http://www.google.com/images/srpr/logo3w.png 100w,
/unsafe/200x200/http://www.google.com/images/srpr/logo3w.png 200w,
/unsafe/375x375/http://www.google.com/images/srpr/logo3w.png 375w
```

e assim por diante até satisfazer todos os intervalos importantes para determinada imagem.

tentar fazer um codepen pra isso, problema, crossdomain

#### Exibição progressiva
No post anterior falamos da importância de exibir o conteúdo progressivamente, ou seja, ir exibindo as coisas conforme os breakpont são satisfeitos; Mas podemos ir além e fazer não só a exibição progressiva mas também fazer carregamento progressivo; É aqui que o javascript entra em cena. Suponhamos que em nosso layout de tablet algo a mais deve ser exibido, ao invéz então de já ter esse conteúdo carregado mas com display none, faremos melhor, veja:

<iframe width="100%" height='265' scrolling='no' title='dWRaNR' src='//codepen.io/feliperohde/embed/dWRaNR/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/feliperohde/pen/dWRaNR/'>dWRaNR</a> by Felipe Rohde (<a href='http://codepen.io/feliperohde'>@feliperohde</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

Neste exemplo simples, ao atingir 40em de proporção horizontal, o device mostra uma div e também inicia um request ajax carregando conteúdo extra para aquela div; Isso poder ser muito útil quando queremos incrementar o conteúdo para um dispositivo com mais capacidade, no nosso caso, somente carregamos uma imagem a mais, mas poderia ser uma galeria, videos relacionados ou artigos do mesmo autor.

#### Conclusão
Até mesmo ferramentas automatizadas como wix, ux.pin e squarespace já estão sendo capazes de criar bons exemplos de paginas mobile-first responsivas, mostrando que é possível vencer essa etapa sem sofrimento e sem perda de brainstorm.

Ferramentas como essas estão lentamente removendo desenvolvedores que não se preocupam com isso do mercado; Pessoas e empresas que se preocupam com mobile-first só farão ferramentas assim evoluir e surgir novas, sempre com o foco no querido usuário. A receita não é perfeita e sempre haverá espaço para melhorar esse conceito e também essas ferramentas, esperamos que, assim como nós (rs), você também se preocupe com a maneira que o usuário acessa seu conteúdo.