# COMO BAIXAR UM CARROSEL DE IMAGENS DE UM POST DO INSTAGRAM

**Um robozinho amigo!**

Um script (escrito em Javascript) vai capturar os links das imagens de um post de carrousel do Instagram.

Este tutorial está escrito em linguagem muito simples para ser compreendido até por leigos.

*(E lembrando que a melhor versão é a de bookmarklet que posso disponibilizar o código se solicitado)*

## Se recomenda (embora opcional):

- A extensão de Navegador 'Copu All Urls', para abrir mais rapidamente aos links gerados.
	(https://chromewebstore.google.com/detail/copy-all-urls/djdmadneanknadilpjiknlnanaolmbfk)

- Usar o navegador Chrome ou Chromium (para melhor funcionamento das teclas de atalho).


## Passo a passo:

 - Abra uma publicação de carrousel de imagens. Exemplo para testes: https://www.instagram.com/p/DFNthdDgC6a
 - Verifique se a URL do post está 'livre' de parâmetros (do tipo: ?...etc...). Mas apenas como mostra o exemplo acima (instagram.com/p/xxxxx).
 - Após recarregada a página, pressione: `Control + Shift + J` (control + J maiúsculo), para abrir o Console.
 - Não se preocupe com as mensagens que aparecem no Console.
 - Limpe tudo pressionando: `Control + L` (L minúsculo).
 - Cole todo o código abaixo dentro do Console (tela preta) e tecle "ENTER" em seguida. _(Veja bem que não fique faltando nenhuma parte)_:
 
 ```javascript 
 
	let listaURL = [];
	let repeticao = 1;
	while(repeticao < 20){ 
		repeticao++; 
	   	await new Promise(resolve => setTimeout(resolve, 2000));
		let link1 = document.querySelectorAll('li img')[0].src;
		listaURL.push(link1);
	    	let link2 = document.querySelectorAll('li img')[1].src;
		listaURL.push(link2);
		try{
			// é preciso que o Instagram esteja em português (abaixo a palavra avança):
			document.querySelectorAll('button[aria-label="Avançar"]')[0].click();
		}
		catch(err){
			break;
		}
		await new Promise(resolve => setTimeout(resolve, 2100));
	}

	let filtrados = [...new Set(listaURL)].sort(); 
	let links = filtrados.join('\n');
	
 
 ```
 - Aguarde que automaticamente as imagens vão ser mudadas (rodadas). _(Não interfira no processo)_. Até chagar a última imagem do slide (carrousel).
 - Após chegar à última imagem, e parar de rodar, digite o seguinte comando dentro no Console (na tela preta) e tecle enter:

` copy(links); `

 - Pronto, todos os links das imagens estão no Clipboard do seu computador. 
 
 Agora, você pode fazer o seguinte:
 
 - Com a extensão do Chrome (Copy All Urls) que recomendamos, você clica no 'guardachuvinha' e em seguida em 'Paste'. Logo, todas os links serão abertos imediatamente no navegador. 
 - Ou você cola num bloco de notas todos os links que estão no clipboard (memória) com Ctrl + V, para abrí-los futuramente.
 
 - **Para salvar as imagens:** Quando as imagens estejas abertas nas abas do seu navegador, percorra uma a uma e pressione `Ctrl + S` para salvá-las em sua máquina. 
 
 Disfrute!
 
```
 
 
 
```
