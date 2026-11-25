# Como apresentar o sistema do Brechó (para quem não programa)

## 1. Como abrir
Dê **dois cliques** no arquivo `index.html`. Ele abre no navegador. Não precisa instalar nada nem ter internet.

## 2. O que falar sobre o sistema (roteiro de 1 minuto)
> "Nosso sistema é um controle simples de brechó, feito em HTML. Ele tem três telas:
> na tela **Produtos** a gente cadastra cada peça com categoria, tamanho e preço;
> na tela **Clientes** cadastramos o nome, telefone e cidade de quem compra;
> e a tela **Visão geral** mostra o resumo: quantas peças temos, quantos clientes e o valor total do estoque.
> Os dados ficam salvos na memória do próprio navegador, então não se perdem ao fechar a página."

## 3. Demonstração ao vivo (nesta ordem)
1. Abra em **Produtos** → cadastre uma peça (ex: *Jaqueta jeans, Jaqueta, M, 89.90*) → clique em **Cadastrar produto**. Ela aparece na tabela abaixo.
2. Vá em **Clientes** → cadastre um cliente → ele aparece na lista.
3. Vá em **Visão geral** → mostre que os números mudaram sozinhos e leia a frase do resumo.

## 4. Se o professor perguntar "como isso funciona?"
O arquivo tem três partes, e cada uma está comentada no código:
- **HTML** = o esqueleto (os textos, campos e botões que aparecem na tela)
- **CSS** = a aparência (cores, tamanhos, espaçamentos)
- **JavaScript** = o que acontece quando alguém clica num botão (guardar o produto na lista e desenhar a tabela)

As três telas estão no mesmo arquivo: o sistema esconde duas e mostra só a que foi clicada.

## 5. Dica
Para apresentar com a tela já cheia, cadastre 3 ou 4 produtos e 2 clientes **antes** da apresentação — eles ficam salvos.
Para limpar tudo e começar do zero, abra o sistema, aperte `F12`, vá na aba *Application* → *Local Storage* e apague os itens — ou simplesmente apague os cadastros clicando em **Excluir**.
