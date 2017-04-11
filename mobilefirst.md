![Alguns pontos interessantes sobre o conceito mobile-first](http://i.imgur.com/8ZcN71H.jpg)

# Mobile-first
Dispositivos móveis estão cada vez mais sofisticados e presentes em nossas vidas. Ainda assim, muitas vezes eles não recebem a devida importância durante o processo de criação e desenvolvimento de nossos sites. Dotados de características específicas, requerem atenção especial para que ofereçam a melhor experiência possível a seus usuários. Foi nesta busca por otimização que nasceu o **mobile first**: o foco na experência do usuário em dispositivos móveis.

Já esclarecendo: mobile first **não é uma nova tecnologia**. Mobile first é um conceito, uma quebra de padrões, vícios e paradigmas que foram adquiridos no decorrer dos anos, enquanto o pensamento sempre esteve voltado para aplicações desktop. Além de tudo, é uma estratégia e um jeito diferente de enxergar o conteúdo que realmente importa em um site.

**O que muda em um desenvolvimento pensado como mobile first?**

Ao contrário da forma com que historicamente vínhamos trabalhando, focados na experiência de navegação em um computador de mesa ou notebook (e a versão para dispositivos móveis era feita na base do improviso), quando pensamos em mobile first, todas as etapas até a publicação de uma aplicação são feitas com foco no mobile, desde o UX, passando pelo design e desenvolvimento e finalmente chegando à redação de conteúdo. 

Dispositivos móveis tem features incríveis que podem ser usadas para proporcionar uma experiência de navegação e interação superior, levando a um nível que, ao menos não tão cedo, o desktop não poderá proporcionar. GPS, giroscópio, multitouch e acelerômetro, por exemplo, são funcionalidades que podem enriquecer (e muito!) a experiência do usuário.


## Certo, mas isso é realmente necessário?
Uma espiada rápida em estatísticas de uso da internet mostra o rápido crescimento dos números referentes ao uso de dispositivos móveis, como tablets e celulares, e também de conteúdo e apps feitos para esses dispositivos.

![Acesso a internet por celulares ultrapassa os computadores](http://i.imgur.com/hITNGQf.jpg)

#### O celular é o meio de acesso a internet mais usado no Brasil
Uma pesquisa realizada em 2014 e divulgada em 2016 pelo IBGE, mostra que pela primeira vez os **celulares passaram os computadores de mesa** no acesso a internet pelos brasileiros.
**Fonte:** http://agenciabrasil.ebc.com.br/economia/noticia/2016-04/celular-e-principal-meio-de-acesso-internet-na-maioria-dos-lares

#### Pagamento de contas pelos celulares
Ainda no Brasil, **cerca de 45%** das pessoas usam o smartphone para pagamento de contas básicas como água e luz, um dado de 2015. Outro dado interessante é de que cerca de 7 milhões de brasileiros acessa a internet apenas pelo celular.
**Fonte:** http://avellareduarte.com.br/fases-projetos/conceituacao/demandas-do-publico/pesquisas-de-usuarios-atividades-2/dados-sobre-o-publico-alvo/dispositivos-moveis-2015-dados-e-fontes/

Recentemente, o WhatsApp anunciou que esta avaliando a possibilidade de permitir pagamentos através de seu app.
**Fonte:** https://olhardigital.uol.com.br/noticia/usuarios-vao-poder-fazer-pagamentos-pelo-whatsapp/67249

#### Tráfego apenas pelos celulares
O tráfego em sites utilizando smartphone cresceu **600% em 2010**.
**Fonte:** http://news.bango.com/2010/02/16/600-percent-growth-in-mobile-web-usage/

#### Aumento na venda através de dispositivos móveis
Em 2015, no Brasil, as vendas através de dispositivos móveis cresceram cerca de 20%.
**Fonte:** http://opus-software.com.br/estatisticas-uso-celular-brasil/

#### Maior número de acessos "mobile only"
Em uma visão global o cenário não é muito diferente, em 2015 o número de acessos a internet "mobile only" ultrapassou os números de acesso "desktop only" em pouco mais de 1%.
**Fonte:** http://comscore.com/Insights/Blog/Number-of-Mobile-Only-Internet-Users-Now-Exceeds-Desktop-Only-in-the-U.S

#### Em média, checamos o celular 150 vezes ao dia.
Junte a isso com o fato de que a maior parte das pessoas checa o celular dentro de 15 minutos após acordar. O celular e, em especial, as notificações push, se tornaram o novo "horário nobre". 
**Fonte:** https://www.thinkwithgoogle.com/articles/win-every-micromoment-with-better-mobile-strategy.html

> O celular vem se tornando uma extensão de nossa mente, usamos ele pra praticamente tudo e dispomos de atenção para ele virtualmente o tempo todo. 

## Ainda não estou convencido. Por que eu devo mudar minha forma de conceber sites e pensar "mobile first"?

![Mobile first = content first](http://i.imgur.com/e3OrboR.jpg)

### 1 – Conteúdo realmente relevante
Via de regra, o usuário que visita seu site ou aplicação está ali pelo conteúdo, não pelo design, código ou qualquer outra coisa. Se a  criação de conteúdo em si já apresenta desafios diversos, quando passamos para uma área de leitura muito mais limitada, o desafio se torna ainda maior. Dispositivos móveis não deixam espaço para conteúdo irrelevante, sendo primordial fornecer uma comunicação concisa e coesa, para que o seu público-alvo tenha fácil acesso ao que realmente importa.

### 2 - Arquitetura da informação pensando no worst-case scenario
Uma coisa que ainda se pensa muito sobre responsividade e mobile first é que isso é uma adaptação que deve ser feita somente no processo de desenvolvimento, fazendo com que muitas premissas de mobile-first não sejam cumpridas, pois isso não é verdade. O processo criativo é tão importante quando o desenvolvimento quando iniciamos a construção ou adaptação para criar algo realmente mobile-first.

Organizar a informação para dispositivos móveis é um desafio, e por isso deve ser feito primeiro. A tela menor que o monitor, a área de toque dos dedos maior que do ponteiro do mouse e a falta de um ponteiro para demonstrar possíveis interações (hover), são alguns dos motivos que tornam a arquitetura da informação para dispositivos móveis um desafio. Menus dropdown, o floating button ou o famoso menu drawer do [material design](https://material.io/guidelines/) são soluções criadas visando solucionar problemas de poluição visual em dispositivos móveis.

Uma vez concebida uma solução que funcione bem em um device móvel, esta pode ser facilmente adaptável a um dispositivo com tela maior.

### 3 – Conexões 3g/4g limitadas = máxima preocupação com performance!

Imagine um cenário onde, no celular, algumas informações que estão presentes no desktop não serão exibidas. O caminho mais curto seria esconder no celular esse conteúdo, a estética estaria resolvida, problema solucionado, certo? 

Errado. Essa abordagem fará com que o dispositivo móvel carregue todo o conteúdo e depois o esconda, fazendo com que justamente o device que tem menos recursos de processamento e acesso a internet tenha que baixar coisas que não serão vistas e, de forma alguma, aproveitadas.

A abordagem correta neste caso (onde o device móvel e desktop diferem em conteúdo) é fazer uma exibição progressiva, mobile first. Isso significa que, em vez de esconder em mobile o que não será utilizado, o componente será inserido apenas na versão desktop, evitando assim o desperdício de poder de processamento e alguns kb do precioso plano de dados do seu usuário. 

Se isso não for possível, deve-se ao menos fazer com que o conteúdo esteja naturalmente escondido e depois fazer com que o desktop o exiba, evitando assim processamento desnecessário de renderização por parte do celular.

### 4 – Maior SEO
Uma atualização no crawler do Google, feita em 2015, dá prioridade a sites que sejam feitos pensados para dispositivos móveis. Depois desse update, o famoso buscador (que foi um dos primeiros a apresentar uma proposta envolvendo mobile first), prioriza para seus usuários conteúdos otimizados para celulares, e isso não vale somente se este está realmente buscando por um dispositivo móvel, sites otimizados para celulares ganham relevância mesmo quando buscados por computadores de mesa.
**Fonte:** https://webmasters.googleblog.com/2015/02/finding-more-mobile-friendly-search.html


![Mobile first não é uma nova tecnologia e nem algo que vai encarecer o projeto](http://i.imgur.com/uzE85gS.jpg)

### 5 – Tudo isso, sem custo adicional, muito pelo contrário
É comum o receio por optar por mobile first, pois imagina-se que será mais caro. Isso não é verdade!

Um projeto pensado como desktop first geralmente custa mais caro, pois tende a gastar todos os recursos para uma versão desktop e depois ainda exige esforço adicional para uma versão mobile. E aí acaba saindo ainda mais caro, pois essa adaptação exige esforço. Já um projeto mobile first, tende a administrar bem os recursos para construir algo para o celular e depois gastar essa economia em uma versão enriquecida para desktop, neste fluxo, a adaptação é muito mais fácil e exige bem menos esforço.

Há de se pensar também que, nas vezes onde o design responsivo for bem aplicado, não exigirá mudanças para telas maiores.
**Fonte:** https://webmasters.googleblog.com/2015/02/finding-more-mobile-friendly-search.html


## Conclusão
Os dispositivos móveis vieram para ficar: Eles conquistaram seu espaço e as pessoas que, em sua maioria, preferem o celular para acessar a internet e interagir socialmente (o que só tende a aumentar mais, nos próximos anos). Não há mais espaço para falhar, e sites que não levarem isso em consideração perderão acessos e clientes.

Ao fazer mobile first, não só nos adaptamos a esta realidade, oferecendo experiência, performance e conteúdo otimizados para nossos usuários, mas evoluímos cada vez mais este conceito, nos preparando para os novos cenários e desafios que a sociedade e a tecnologia irão criar.
