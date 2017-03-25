# asplande-rj
Projeto Mulheres em Rede - Compartilhando Saberes

Guia para alteração/exclusão/inclusão dos banners de entrada do site via código:

Acessar a Central do Cliente em https://www.locaweb.com.br/default.html

Acessar "Produtos >> Hospedagem de Sites"

Clicar em mulheresnarede.org.br

Clicar em PUBLIQUE SEUS ARQUIVOS

Em "Gerenciador de arquivos web", clicar em "Acessar o gerenciador"

Preencher os campos: Host, Usuário e Senha

Clicar no botão do "Check" verde

Na área maior, onde há os campos "Nome do arquivo", "Tamanho", "Tipo", etc.:

Acessar a pasta /public_html/img/carousel

Clicar em "Enviar >> From computer"

Na janela que abrir, clicar em "Navegar em seu computador"

Selecionar as fotos que deseja fazer o upload (enviar)

Clicar em "Enviar"

Após finalizar esta parte, a foto estará disponível para ser carregada via HTML.
Mas ainda é preciso alterar/incluir o código que fará o carregamento.

Para isso, é preciso mexer direto no código-fonte da página.

Dessa forma, volte para /public_html e clique com o botão DIREITO do mouse em index.php

Selecione "Abrir com... >> Source Editor"

A partir da linha 113 (<!-- Carousel -->), está o código dos banners

As imagens são carregada nas linhas 126, 132, 138 e 144
	
	<img src="img/carousel/nome_da_foto.jpg" class="img-centered" alt="Slide #">

Para alterar as imagens, basta substituir nome_da_foto_atual.jpg por nome_da_foto_nova.jpg ou nome_da_foto_nova.png, dependendo do formato da foto escolhida.

O padrão atual é de 4 fotos/slides. 

Caso queira diminuir a quantidade de fotos/slides, basta deletar o seguinte trecho:

	<div class="item">
   		<img src="img/carousel/nome_da_foto.jpg" class="img-centered" alt="Slide (1 a n)">
    	<!-- <div class="carousel-caption">
    	<h3>Caption Text</h3>
    	</div> -->
    </div>

e deletar o trecho correspondente logo acima em <!-- Indicators -->:

	<li data-target="#carousel-example-generic" data-slide-to="(0 a (n-1))"></li>


Caso queira aumentar a quantidade de fotos/slides, basta incluir o seguinte trecho:

	<div class="item">
   		<img src="img/carousel/nome_da_foto_nova.jpg" class="img-centered" alt="Slide (1 a n)">
    	<!-- <div class="carousel-caption">
    	<h3>Caption Text</h3>
    	</div> -->
    </div>

e incluir o trecho correspondente logo acima em <!-- Indicators -->:

	<li data-target="#carousel-example-generic" data-slide-to="(0 a (n-1))"></li>
	

Após as alterações, clique em "Salvar" no canto superior esquerdo da tela

Logo em seguida, clique em "Fechar"

Atualize a página (F5) para garantir o carregamento das alterações pelo navegador

Verifique se as alterações foram feitas em http://mulheresnarede.org.br/

Obs.: a dimensão atual das imagens é 1440px x 864px, mas pode ser maior desde que todas tenham exatamente as mesmas dimensões.

Caso prefira, pode baixar o arquivo index.php para o seu computador, alterá-lo nesta IDE: (https://code.visualstudio.com/Download) e enviar o arquivo atualizado via "Gerenciador de arquivos web". Desta forma, não estaremos mexendo direto na Produção, ou seja, as mudanças só se tornarão públicas após o envio do arquivo atualizado.
