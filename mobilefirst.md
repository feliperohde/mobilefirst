
# Mobile-first
Dispositivos móveis estão cada vez mais sofisticados e podemos pensar que talvez não seja assim tão importante pensar neles primeiro, visto que o hardware e features deles já estão bem avançados, mas não... Assim como o hardware e features destes dispositivos avançam, novas features surgem exigindo mais recursos, e não é somente uma questão de estética, é também e principalmente uma questão de conteúdo.

Pensando pela estética e reaproveitamento, é mais fácil ajustar o conteúdo e layout de dispositivos móveis para Desktop do que o contrário.

Dispositivos móveis tem features incríveis que podem ser usadas para proporcionar uma experiencia melhor levando-a a um nível que o desktop não poderá proporcionar, ao menos não tão cedo; O gps, giroscópio, multitouch, acelerometro e etc podem enriquecer muito a experiencia e proporcionar ao usuário uma visão mais imersiva daquilo que se quer mostrar ou vender.

Exibir a informação mais relevante para cada device é um fator decisivo para a permanência do usuário em um site, principalmente quando este esta em processo de compra ou pesquisa.

O responsive design busca solucionar isso através do reaproveitamento e o mobile first entra nesse jogo com um conceito que visa padronizar o fluxo do desenvolvimento através da exibição progressiva.


### Alguns dados
Uma espiada rápida em estatísticas de uso da internet mostra o crescimento muito rápido dos números que representam dispositivos móveis como tablets e celulares e também de conteúdo e apps feitos para esses dispositivos.
O celular é quase um extenção de nossa mente, usamos ele pra quase tudo, agendar coisas, ler noticias, comprar e pagar contas, jogar, discutir, reclamar e até mesmo estudar e trabalhar.

O tráfego em sites utilizando smartphone cresceu 600% em 2010 (https://news.bango.com/2010/02/16/600-percent-growth-in-mobile-web-usage/)

No brasil o acesso a internet usando o celular ultrapassou o computador em 2014 (http://agenciabrasil.ebc.com.br/economia/noticia/2016-04/celular-e-principal-meio-de-acesso-internet-na-maioria-dos-lares)

Em 2015, no brasil, as vendas através de dispositivos móveis cresceu cerca de 20% (http://www.opus-software.com.br/estatisticas-uso-celular-brasil/).

Ainda no Brasil, cerca de 45% das pessoas usam o smartphone para pagamento de contas básicas como água e luz, um dado de 2015. Outro dado interessante é de que cerca de 7 milhões de brasileiros acessa a internet apenas pelo celular. (http://www.avellareduarte.com.br/fases-projetos/conceituacao/demandas-do-publico/pesquisas-de-usuarios-atividades-2/dados-sobre-o-publico-alvo/dispositivos-moveis-2015-dados-e-fontes/)

Em uma visão global o cenário não é muito diferente, em 2015 o número de acessoas a internet "mobile only" ultrapassou os numeros de acesso "desktop only" em pouco mais de 1%. (https://www.comscore.com/Insights/Blog/Number-of-Mobile-Only-Internet-Users-Now-Exceeds-Desktop-Only-in-the-U.S)

Recentemente, o WhatsApp anunciou que esta avaliando a possibilidade de permitir pagamentos através de seu app. (http://g1.globo.com/tecnologia/noticia/whatsapp-avalia-entrada-em-mercado-de-pagamento-digital-na-india.ghtml)

O mundo está, claramente gastando mais tempo na internet usando o celular, é muito sensato desenvolver pensando primeiramente nessas pessoas.

### A exibição tem que ser progressiva
Mobile first = content first

Imagine o cenário onde no celular algumas informações que estão presentes no desktop não serão exibidas, o caminho mais curto seria esconder no celular esse conteúdo, a estética estaria resolvida, problema solucionado, mobile first não é? NÃO! essa abordagem fará com que o dispositivo móvel carregue todo o conteúdo e depois o esconda; Justamente o device que tem menos recursos de processamento e acesso a rede tem que baixar coisas que nem serão vistas e de forma nenhuma serão aproveitadas; Haverá perda de performance e o usuário será obrigado a gastar banda de sua conexão móvel para baixar conteúdo que nunca verá.

A abordagem correta neste caso, onde o device movel e desktop diferem em conteúdo é usar o design adaptativo. Se isso não for possível, deve-se ao menos fazer com que o conteúdo esteja naturalmente escondido e depois fazer com que o desktop o exiba, evitando assim processamento desnecessáro de renderizaçao por parte do celular.

### O SEO
Uma atualização no crawler do Google, feita em 2015, da prioridade a sites que sejam feitos pensados para dispositivos móveis. Depois desse update, o famoso buscador, prioriza para seus usuários conteúdos otimizados para celulares, e isso não vale somente se este está realmente buscando por um dispositivo móvel, sites otimizados para celulares ganham relevância mesmo quando buscados por computadores de mesa.

https://webmasters.googleblog.com/2015/02/finding-more-mobile-friendly-search.html

### O design
Uma coisa que se pensa ainda muito sobre responsividade e mobile first é de que isso é uma adaptação que deve ser feita somente no processo de desenvolvimento, fazendo com que muitas promessas de mobile-first não sejam cumpridas pois isso não é verdade; O processo criativo é tão importante quando o desenvolvimento quando iniciamos a construção ou adaptação para criar algo mobile-first.

#### O que é design responsivo?
Esse conceito surgiu inicialmente para solucionar problemas de arquitetura em grandes cidades, um jeito de tentar resolver problemas para espaços pequenos, algo como móveis que pudessem ser dobrados, camas que pudessem ser guardadas na parede, tudo para dar a espaços pequenos o mesmo conforto de um espaço maior.

Na web o conceito começou a surgir por volta de 2000, com o surgimento de telas lcd e com o surgimento de novos notebooks e padrões de tela; Mas isso ainda não justificava a criação de um novo padrão de design. Somente com o surgimento dos celulares foi que uma reformulação no design se fez necessária.

O design responsivo visa ajustar esteticamente o conteúdo para os diferentes tipos de tela que devemos dar suporte, para podermos ter uma leitura desse conteúdo da maneira mais confortável em cada dispositivo ou resolução.


#### O que é design adaptativo
Sutilmente diferente do design responsivo, e como uma variação dele, o design adaptativo não muda somente a estética, mas sim todo o conteúdo; Um exemplo seria um artigo para leitura rápida em um celular e um artigo completo com imagens e videos no desktop, o conteúdo mudou mas a informação que se passa ainda é a mesma.


#### O que é Mobile-first?
A definição simples é: fazer tudo pensando primeiro em dispositivos móveis. E isso inclui desde os processos de criação até a arquitetura e engenharia no desenvolvimento.

#### Qual a diferença entre Mobile-first e design responsivo/adaptativo?
Há uma confusão entre estes termos, e é comum, visto que cada vez mais aparecem novos termos para definir coisas que surgem na TI, muitas vezes somente para renomear o que ja existe e precisa de atenção novamente; Mas estas são coisas diferentes sim. O mobile first é um conceito de desenvolvimento, uma maneira de pensar sobre aquilo que irá ser desenvolvido e além disso ele dá uma direção clara e objetiva, já o design responsivo ou responsive design é um método de desenvolvimento, este método visa reaproveitar ao máximo tanto o código como os blocos no layout, isso para satisfazer os diferentes padrões e tamanhos de tela sem aumentar muito o esforço para isso; Fazer com que algo do desktop possa ser reaproveitado no mobile ou na TV ou no notebook.

`O que o mobile first faz, é usar esta metodologia do design responsivo/adaptativo para viabilizar o seu conceito`.

### Os custos
É comum o receio pelo mobile first na questão de custos pois pensa-se que por isso ter se tornado um serviço devido a sua rápida ascensão deve custar mais caro; Isso não é verdade.
Um projeto pensado em desktop first geralmente custa mais caro, pois tende a gastar todos os recursos para uma versão desktop e depois cortar custos para uma versão mobile, e nesse ponto é onde fica mais caro, pois essa adaptação exige esforço; Já um projeto mobile first, tende a administrar bem os recursos para construir algo para o celular e depois gastar essa economia em uma versão enriquecida para desktop, neste fluxo, a adaptação é muito mais fácil exige bem menos esforço.
Há de se pensar também que em algumas vezes, o design responsivo bem aplicado não exigirá mudanças para telas maiores.
https://webmasters.googleblog.com/2015/02/finding-more-mobile-friendly-search.html

### O remanejamento
Adicionar conteúdo em dispositivos de mesa como desktops é relativamente fácil; Dispositivos móveis limitam isso bastante, não deixando espaço para conteúdo irrelevante, a seleção das informações que devem ser mostradas em um dispositivo móvel exige alguns passos a mais já que é necessário mostrar somente o que seu mercado (público) quer ver.

Organizar a informação para dispositivos móveis é um desafio, e por isso deve ser feito primeiro; Não somente de design, mas também de arquitetura de software.  Menus dropdown, o floating button ou o famoso menu drawer do material design foram criados para solucionar problemas de poluição visual em dispositivos móveis.
Uma feature que funcione bem em um device móvel poderá ser usada sem problemas em um dispositivo com tela maior, algumas vezes pequenos ajustes estéticos podem ser feitos.


### É melhor mesmo pensar em mobile primeiro?
Existe uma quebra no paradigma/tradição tando de criação quanto de desenvolvimento; O que quase sempre acontece é que em determinada altura no desenrolar do projeto, alguém meio que de maneira mágica percebe que o site deve funcionar também no celular ou percebe que ele não está funcionando bem no celular justamente por estar vendo ele em seu dispositivo móvel; Neste ponto o designer passa as vezes dias fazendo o famoso "aperta pra caber" e isto tem um graves problemas, pois o designer não esta pensando em proporcionar um bom conteúdo para os usuários que vêem o site através de dispositivos móveis menos ainda em proporcionar um boa experiencia e isso faz muitas vezes com que  este desista do que o site tem a oferecer; Outro grave problema nisso está no desenvolvimento, pois a adaptação do código seguindo o fluxo de desktop para mobile quase sempre implica em código a mais, perda de performance e código de difícil manutenção e escalabilidade. Tudo isso devido o fato de dispositivos móveis aparecerem de surpresa em um projeto não pensado para eles.

    Concluindo: sim, se o projeto vai poder ser acessado por dispositivos móveis, faça primeiro para esses dispositivos.

### Como descobrir a importância do design responsivo e mobile first para um projeto
Algumas perguntas podem ajudar a mensurar a importância dos dispositivos para cada projeto.

Qual o publico-alvo deve ser atingido?
Em qual hora do dia o publico costuma acessar o site?
Quais os recursos ele usa ou deve poder usar no desktop? e no celular?
Estamos reformulando o site, então, quais as estatísticas de acesso de cada device?
O site possui recursos de interação social, como compartilhamentos, comentários...?

Se seu público é jovem, por exemplo, muito provavelmente ele irá acessar o conteúdo de deu site atravéz de um dispositivo móvel.

Se estou vendendo algo, como um restaurante por ex, é provável que a audiência suba por volta do meio-dia e também por volta das 20hrs e seu site deve estar preparado para dar acesso fácil a endereço e telefone, pois é provável que seu possível cliente esteja na rua ou no carro e essa informação precisa ser vista rapidamente.

### Conclusão
Sabemos que o devices móveis conquistaram seu espaço e sabemos que as pessoas em sua maioria preferem o celular para acessar a internet e interagir socialmente. Usuários estão cada vez mais exigentes quanto a isso, logo não haverá mais espaço para falhar com isso e sites que não são desenvolvidos pensando nessas pessoas perderão acessos e clientes.
É muito importante trabalhar para viabilizar uma boa experiencia e conteúdo para esse publico, não somente para conquista-los mas também para evoluir este conceito e se preparar para os novos cenários que isso irá criar.

```css
.c-component {}

+above(960px) {
    .c-component {
        background: #ff0;
        float: left;
    }
}
```
