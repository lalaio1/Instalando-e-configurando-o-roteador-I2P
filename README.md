<div itemprop="text">

<p>Boa tarde a todos.</p>

<p style="text-align:justify">Segue agora a seção 2 do tutorial do I2P. Mas antes apenas queria falar um pouco do projeto I2P. Apesar do foco do tutorial não ser para tratar da sua história, gostaria ao menos de fazer uma breve introdução sobre ela.</p>

<p style="text-align:justify">O projeto I2P (Invisible Internet Protocol) é uma rede P2P descentalizada, anônima e segura para estabelecer a comunicação entre os usuários e serviços. Na I2P é possível usar serviços como mensageiros IRC, XMPP, web services, e-mail e até mesmo torrents. A I2P nasceu de um fork da Freenet no ano de 2003, porém possui diferenças drásticas em relação a ela.</p>

<p style="text-align:justify">Há similaridades entre a I2P e o Tor, porém vale destacar algumas de suas vantagens. Sendo elas:</p>

<ul>

<li style="text-align:justify"><a rel="nofollow" href="https://geti2p.net/en/docs/how/garlic-routing" target="_blank">Garlic routing</a></li>

<li style="text-align:justify">Modelo P2P</li>

<li style="text-align:justify">Todos os participantes da rede contribuem para ela</li>

<li style="text-align:justify">Fechado na rede - não é possível acessar a surface através da I2P</li>

<li style="text-align:justify">Otimizado para hidden services</li></ul>

<p style="text-align:justify">Apesar disso, vale lembrar que o projeto é pequeno, desenvolvido por menos voluntários se comparado ao Tor e possui menos movimentação e financiamento para o seu desenvolvimento. Além disso, o Tor é um projeto muito mais maduro e bem documentado, algo que atrai mais usuários e desenvolvedores e torna a tarefa de encontrar e corrigir bugs mais fácil de ser realizada.&nbsp;</p>

<p style="text-align:justify">Esses são pontos importantes que devemos levar em conta ao escolher a tecnologia para as nossas necessidades. Nem sempre há tecnologias ruins, as vezes apenas as empregamos as ferramentas erradas na resolução de certos problemas.</p>

<p style="text-align:justify">Referências:</p>

<ul>

<li style="text-align:justify">https://geti2p.net/en/comparison/tor</li>

<li style="text-align:justify">https://geti2p.net/en/docs/how/garlic-routing</li>

<li style="text-align:justify">https://geti2p.net/en/about/intro</li>

<li style="text-align:justify">https://i2pd.readthedocs.io/en/latest/</li></ul>

<h2>2. Instalando e configurando o roteador</h2>

<p style="text-align:justify">Antes da criação do <a rel="nofollow" href="https://github.com/PurpleI2P/i2pdbrowser/releases/tag/1.3.3" target="_blank">I2PBrowserBundle</a>, a única forma de se conectar à I2P era pela configuração manual de proxy no navegador. Muita gente ou não sabe ou tem MUUUUUITA preguiça de fazer isso e ficam resistentes de entrar na I2P dada essa restrição.</p>

<p style="text-align:justify">Como eu quero ser um bom tutor eu farei do jeito mais "difícil", pois tanto eu desejo que vocês aprendam as nuances do processo como eu sei que vocês são inteligentes o suficiente para fazer isso.</p>

<p style="text-align:justify"></p>

<h3 style="text-align:justify">2.1 Instalação do router</h3>

<p style="text-align:justify">Atualmente nós temos duas implementações do I2P: Uma em Java e outra em C++ (i2pd). Usaremos nesse tutorial a versão em C++ dado o seu baixo uso de recursos e facilidade de instalação.</p>

<p style="text-align:justify">O I2Pd está disponível para Windows, Linux, MacOS e Android e possui binários pré-compilados nas <a rel="nofollow" href="https://github.com/PurpleI2P/i2pd/releases/tag/2.50.2" target="_blank">releases</a> do projeto no Github. Usuários de Linux podem instalá-lo através do respectivo gerenciador de pacotes da sua distribuição, porém algumas distros não oferecem o pacote diretamente nos reposítórios oficiais, necessitando do uso de PPAs (Ubuntu), COPR (Fedora/RHEL) e afins. Vocês podem conferir as instruções oficiais para cada sistema <a rel="nofollow" href="https://i2pd.readthedocs.io/en/latest/user-guide/install/" target="_blank">nessa página</a>.</p>

<p style="text-align:justify">Apesar desse tutorial ser voltado a usuários de desktop, o I2Pd também está disponível na loja do F-droid. Infelizmente poucos navegadores em Android permitem a configuração de proxies, porém na seção de Serviços na I2P eu tratarei brevemente de como se conectar a servidores de XMPP usando o ConversationI2P.</p>

<p style="text-align:justify">Para usuários de Windows, segue abaixo os binários para instalação.</p>

<ul>

<li style="text-align:justify"><a rel="nofollow" href="https://github.com/PurpleI2P/i2pd/releases/download/2.50.2/i2pd_2.50.2_win32_mingw.zip" target="_blank">Versão 32bits</a></li>

<li style="text-align:justify"><a rel="nofollow" href="https://github.com/PurpleI2P/i2pd/releases/download/2.50.2/i2pd_2.50.2_win64_mingw.zip" target="_blank">Versão 64bits</a></li>

<li style="text-align:justify"><a rel="nofollow" href="https://github.com/PurpleI2P/i2pd/releases/download/2.50.2/i2pd_2.50.2_winxp_mingw.zip" target="_blank">Versão para Windows XP</a> (pois é, kk)</li></ul>

<p style="text-align:justify">A instalação é simples e direta. Após ela apenas abram o I2Pd para que o router inicie a operação de busca e conexão com os peers. Para usuários de Linux, vocês precisam ativar o serviços através do comando <em>'</em>sudo systemctl start i2pd<em>'. </em>Se vocês desejam que o I2Pd inicie junto com o sistema usem o comando 'sudo systemctl enable --now i2pd'.</p>

<p style="text-align:justify">Se tudo estiver funcionando corretamente, vocês serão capazes de abrir o webconsole do I2Pd no navegador através do endereço: 127.0.0.1:7070.&nbsp;</p>

<p style="text-align:justify"><img alt="" src="https://i.postimg.cc/Z5TjxNpB/9-59-cleaned.png" style="height:468px; width:600px"></p>

<p style="text-align:justify"></p>

<h3 style="text-align:justify">2.2 Instalação e configuração do navegador</h3>

<p style="text-align:justify">Apesar de&nbsp; qualquer navegador ser capaz de usar a I2P não é recomendado que usem qualquer um, especialmente o navegador que você usam no seu dia-a-dia. Recomendo que usem um navegador próprio para usar na I2P ou isolem suas atividades em um perfil separado. Em navegadores baseado no Firefox isso é relativamente simples, bastando adicionar a opção '--profile' e o caminho do perfil que vocês desejam usar. Nesse tutorial eu vou mostrar como criar um perfil novo no Librewolf e configurar no lançador para iniciar o perfil e abrir em uma janela anônima. Essas instruções são análogas para todos os sistemas, excetuando aquelas configurações mais exóticas.</p>

<p style="text-align:justify"></p>

<h3 style="text-align:justify">2.2.1 Escolhendo o navegador</h3>

<p style="text-align:justify">Como citado, usarei o Librewolf como exemplo. Vocês podem baixar o instalador direto do site ou usar o gerenciador de pacotes do seu sistema no caso de Linux. Como é uma tarefa trivial eu não vou detalhar esse processo, pois todas as instruções estão em detalhes <a rel="nofollow" href="https://librewolf.net/installation/" target="_blank">no site do navegador. </a></p>

<p style="text-align:justify"></p>

<h3 style="text-align:justify">2.2.2 Criando um perfil e configurando o lançador</h3>

<p style="text-align:justify">Abram o navegador e digitem 'about:profiles' na barra de endereço. Criem um novo perfil clicando em 'Create New Profile'</p>

<p style="text-align:justify"><img alt="" src="https://i.postimg.cc/VL9DtgrP/8-55-cleaned.png" style="width:600px"></p>

<p style="text-align:justify"></p>

<p style="text-align:justify">Coloquem um nome no seu perfil e cliquem em Finalizar</p>

<p style="text-align:justify"><img alt="" src="https://i.postimg.cc/SRCVD7g8/7-47-cleaned.png" style="height:461px; width:610px"></p>

<p style="text-align:justify"></p>

<p style="text-align:justify">Perfis novos recém criados são iniciados por padrão. Se você deseja usar outro perfil por padrão deve mudar isso na seção 'about:profiles' do navegador.</p>

<p style="text-align:justify">Agora vamos configurar o lançador do LibreWolf para iniciar o perfil do i2p e em uma janela anônima. Usarei o XFCE como referência para essa tarefa, mas saibam que o processo é análogo em sistemas como Windows ou DEs como KDE. Se quiserem também podem lançar via terminal através do comando 'librewolf --profile `caminho_do_perfil` --private-window'.</p>

<p style="text-align:justify">Cliquem com o botão direito no ícone do Librewolf e abram as propriedades do atalho.</p>

<p style="text-align:justify">Na guia lançador, no campo Comando, adicionem no final a opção '--private-window' e a opção '--profile `caminho_do_perfil`'. O caminho do perfil é aquele mostrado na seção 'about:profiles' do Librewolf.</p>

<p style="text-align:justify"><img alt="" src="https://i.postimg.cc/tT1BVHPB/6-46-cleaned.png" style="width:600px"></p>

<p style="text-align:justify"></p>

<h3 style="text-align:justify">2.2.3 Configurando o proxy</h3>

<p style="text-align:justify">Com o lançador configurado, abra o navegador nesse perfil. Vamos configurar o proxy para se conectar ao I2P agora.</p>

<p style="text-align:justify">Abra as configurações digitando 'about:preferences' na barra de endereço. Na seção 'Geral' abra as configurações de rede (Network Settings)</p>

<p style="text-align:justify"><img alt="" src="https://i.postimg.cc/pXMsy4dB/4-07-cleaned.png" style="width:600px"></p>

<p style="text-align:justify"></p>

<p style="text-align:justify">Configure o seu proxy como na figura abaixo.</p>

<p><img alt="" src="https://i.postimg.cc/59CP4bf0/3-30-cleaned.png" style="width:600px"></p>

<p></p>

<p>Fecha as configurações. Se o seu proxy foi configurado corretamente tente abrir algum desses eepsites.</p>

<ul>

<li style="text-align:justify">http://identiguy.i2p</li>

<li style="text-align:justify">http://notbob.i2p</li>

<li style="text-align:justify">http://reg.i2p</li></ul>

<p>Se tudo ocorreu como conforme, a página será carregada.</p>

<p><img alt="" src="https://i.postimg.cc/Cxm7PKsv/2-03-cleaned.png" style="width:600px"></p>

<p style="text-align:justify"></p>

<p style="text-align:justify">OBSERVAÇÃO: A busca pelos peers é um pouco demorada, levando de 2 a 5 minutos para que um número mínimo necessário de peers sejam encontrados para estabelecer uma conexão estável. Você pode ver a lista de inbound e outbound tunnels na seção Tunnels do WebConsole (localhost:7070)</p>

<p style="text-align:justify"><img alt="" src="https://i.postimg.cc/5237hgbS/1-58-cleaned.png" style="width:600px"></p>

<p style="text-align:justify"></p>

<p style="text-align:justify">IMPORTANTE: Apesar do Librewolf possuir defaults seguros, eu recomendo que vocês instalem as seguintes extensões para aumentar ainda mais a sua proteção.</p>

<ul>

<li style="text-align:justify">noScript</li>

<li style="text-align:justify">JShelter</li></ul>

<p style="text-align:justify">Lembrem-se que vocês precisam desativar o proxy para acessar a clearnet. Depois disso reativem-no nas configurações.</p>

<p style="text-align:justify">Outro detalhe: Se vocês tentarem digitar um endereço .i2p na barra de endereços do navegador sem especificar o protocolo (http), ao invés do Librewolf ir ao endereço ele vai realizar uma pesquisa. Para corrigir esse problema, vocês precisam adicionar a seguinte configuração do tipo boolean em 'about:config' como mostrado na imagem.</p>

<p style="text-align:justify"></p>

<p style="text-align:justify"><img alt="" src="https://i.ibb.co/7bLNJ5V/10-34.png" style="width:600px"></p>

<p style="text-align:justify"></p>

<p style="text-align:justify">Reiniciem o navegador e testem. Se tudo deu certo vocês não precisam especificar o protocolo ao digitar um endereço .i2p, bastando apenas digitar o endereço simplificado.</p>

<p style="text-align:justify">Por fim, terminamos essa parte do tutorial. Na próximo parte trataremos de como podemos nos conectar a serviços hospedados na I2P como XMPP.</p>

<p style="text-align:justify">Até a próxima. By :: Grom :: lalaio1 </p></div>
