# BRECHÓ DA GIOVANNA
# Manual do Sistema

> Este documento explica o que o sistema faz, como usá-lo e como ele foi construído.
> Ele foi escrito para ser entendido por qualquer pessoa, inclusive quem nunca programou.

**Equipe:** Giovanna · Vitória Moraes · Daniela · Yasmin
**Período:** 25/10/2026 a 25/11/2026
**Arquivo do sistema:** `index.html`

---

# PARTE A — ENTENDENDO O SISTEMA

## A.1 Qual problema a gente resolveu?

Num brechó, as peças chegam uma a uma, cada uma é diferente da outra e cada uma tem um preço próprio. Não existe "20 unidades da camiseta tamanho M": existe *aquela* camiseta. Controlar isso em caderno dá nisso:

- a dona não sabe de cabeça quantas peças tem na loja;
- não sabe quanto dinheiro está parado em estoque;
- os clientes que já compraram não ficam registrados em lugar nenhum.

O sistema resolve esses três pontos e nada mais que isso — essa foi uma escolha da equipe, explicada na parte C.2.

## A.2 O que o sistema faz, em uma frase

Cadastra as peças da loja, cadastra os clientes e mostra um resumo com os totais.

## A.3 O que o sistema NÃO faz (e por quê)

| Não faz | Motivo |
|---|---|
| Registrar a venda / baixar do estoque | Fugia do prazo de um mês; quando a peça sai, ela é removida manualmente |
| Controlar caixa e formas de pagamento | Exigiria uma parte financeira inteira |
| Emitir nota fiscal | Precisaria de integração com a prefeitura |
| Funcionar em vários computadores ao mesmo tempo | Precisaria de um servidor na internet |

---

# PARTE B — COMO USAR (passo a passo)

## B.1 Para abrir

Dois cliques no arquivo `index.html`. Ele abre no navegador. **Não precisa instalar nada e não precisa de internet.**

## B.2 A tela

Do lado esquerdo há um menu fixo com três opções. Clicando em cada uma, muda o conteúdo do lado direito.

```
+----------------+--------------------------------------+
|  BRECHÓ DA     |                                      |
|  GIOVANNA      |        conteúdo da opção             |
|                |        escolhida no menu             |
|  Visão geral   |                                      |
|  Produtos      |                                      |
|  Clientes      |                                      |
+----------------+--------------------------------------+
```

## B.3 Cadastrando uma peça

1. Clique em **Produtos** no menu da esquerda.
2. Preencha os quatro campos:

| Campo | Obrigatório? | Exemplo |
|---|---|---|
| Nome da peça | **Sim** | Jaqueta jeans |
| Categoria | Sim (já vem escolhida) | Jaqueta |
| Tamanho | Não | M |
| Preço | **Sim** | 89.90 |

3. Clique em **Cadastrar peça**.
4. A peça aparece na **Vitrine**, logo abaixo, no formato de uma etiqueta de roupa.

> **Atenção ao preço:** digite com **ponto**, não com vírgula. Escreva `89.90`, não `89,90`.

Para tirar uma peça da loja (porque vendeu ou foi devolvida), clique em **remover** na etiqueta dela.

## B.4 Cadastrando um cliente

1. Clique em **Clientes**.
2. Preencha nome, telefone e cidade. Somente o **nome é obrigatório**.
3. Clique em **Cadastrar cliente**. Ele aparece na lista como uma fichinha, com a inicial do nome num círculo.

## B.5 Lendo a visão geral

Clique em **Visão geral**. Aparecem três números e uma frase de resumo:

| Número | O que significa |
|---|---|
| Peças no estoque | Quantas peças estão cadastradas neste momento |
| Clientes cadastrados | Quantas pessoas estão na base |
| Valor do estoque | A soma do preço de todas as peças cadastradas |

Nesta tela **não se cadastra nada**: ela só mostra o que já existe.

## B.6 Onde os dados ficam salvos

Na memória do próprio navegador, naquele computador. Consequências práticas:

- ✅ Fechar o navegador ou desligar o computador **não** apaga nada.
- ⚠️ Os dados **não** aparecem em outro computador nem em outro navegador.
- ⚠️ Se alguém limpar os dados de navegação do navegador, os cadastros vão embora.

**Por isso: cadastre tudo no mesmo computador que será usado na apresentação.**

---

# PARTE C — COMO O SISTEMA FOI FEITO

## C.1 Com o que ele foi construído

Um único arquivo `index.html`, usando as três linguagens básicas da web:

| Linguagem | Papel | Comparação |
|---|---|---|
| HTML | O esqueleto: textos, campos e botões | A estrutura da casa |
| CSS | A aparência: cores, tamanhos, espaços | A pintura e a decoração |
| JavaScript | O cérebro: o que acontece ao clicar | O morador, que faz as coisas |

Não foi usado banco de dados nem servidor. Quem guarda as informações é um recurso do próprio navegador chamado `localStorage`.

## C.2 Decisões que a equipe tomou (e os motivos)

**Decisão 1 — Um arquivo só, sem instalação.**
Qualquer integrante consegue abrir e apresentar o sistema em qualquer computador, sem configurar nada. O preço disso é não funcionar em rede, o que foi considerado aceitável para um brechó de uma única loja.

**Decisão 2 — Peça em etiqueta, não em tabela.**
No brechó cada peça é única. Uma linha de tabela trata a peça como um item de planilha; a etiqueta mostra a peça como ela é na loja, com categoria, tamanho e preço bem visíveis.

**Decisão 3 — Visão geral só de leitura.**
O professor pediu resumo nessa tela. Deixar cadastro ali também confundiria o usuário sobre onde se cadastra o quê.

**Decisão 4 — Validar apenas o essencial.**
O sistema só reclama se faltar o nome ou o preço da peça. Tamanho e telefone podem ficar vazios, porque no dia a dia da loja nem sempre essa informação existe.

## C.3 Onde está cada coisa dentro do arquivo

| Parte do arquivo | O que tem lá |
|---|---|
| Comentário do topo | Explicação geral do sistema |
| Dentro de `<style>` | Toda a aparência (para mudar a cor, é aqui) |
| Do `<body>` em diante | Os textos, campos e botões que aparecem na tela |
| Dentro de `<script>` | O cérebro, dividido em 7 blocos numerados e comentados |

Os 7 blocos do cérebro: 1) onde os dados ficam · 2) trocar de tela · 3) cadastrar peça · 4) desenhar a vitrine · 5) clientes · 6) visão geral · 7) o que roda ao abrir a página.

## C.4 Perguntas que o professor pode fazer

**"Como o sistema troca de tela se é um arquivo só?"**
As três telas estão todas no arquivo ao mesmo tempo. O cérebro esconde duas e mostra apenas a que foi clicada.

**"Onde o produto fica guardado quando eu clico em cadastrar?"**
Numa lista dentro do programa (uma *array*). Em seguida essa lista é gravada na memória do navegador, e a vitrine é redesenhada do zero com base nela.

**"Como o valor do estoque é calculado?"**
O sistema percorre a lista de peças uma por uma e vai somando os preços. Não existe um campo "total" guardado: ele é calculado na hora, o que garante que nunca fique desatualizado.

---

# PARTE D — QUEM FEZ O QUÊ

| Integrante | Função | O que entregou |
|---|---|---|
| **Giovanna** | Líder / Coordenadora | Definição do escopo, divisão das tarefas, testes finais, documentação e roteiro de apresentação |
| **Vitória Moraes** | Front-end e Web Design | Identidade visual, menu lateral, montagem das três telas e a tela de visão geral |
| **Daniela** | Gerente da loja | Levantamento das necessidades reais da loja e cadastro das peças no sistema |
| **Yasmin** | Back-end | Definição dos dados de produto e cliente e o funcionamento dos dois cadastros |

**Cronograma completo:** arquivo `CRONOGRAMA.md`, representado no Gráfico de Gantt.
**Marcos:** 03/11 escopo e dados definidos · 12/11 telas prontas · 19/11 sistema funcionando · 25/11 entrega.

---

# PARTE E — SE DER PROBLEMA

| Problema | Solução |
|---|---|
| Cliquei em cadastrar e apareceu um aviso | Faltou o nome ou o preço da peça |
| O preço aparece errado na etiqueta | Foi digitado com vírgula; use ponto (`89.90`) |
| Os cadastros desapareceram | O navegador foi limpo, ou o sistema foi aberto em outro computador/navegador |
| Quero zerar tudo para apresentar do zero | Clique em **remover** em cada item, ou aperte F12 → aba *Application* → *Local Storage* e apague os itens |
