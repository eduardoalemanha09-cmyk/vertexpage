# Vertex — contexto de produto e marca

> Registro `brand`: neste projeto o design **é** o produto. Um site com aparência de
> template desqualifica o negócio antes de qualquer argumento de venda.

## O negócio

Vertex cria sites sob medida para restaurantes, hotéis e empresas, com base em Curitiba (PR)
e atendimento a todo o Brasil. Nos bastidores a operação é de duas pessoas (design/animações
e desenvolvimento), mas **o site fala em voz de estúdio — "a Vertex", "nós" — sem nomear
pessoas** (decisão do Eduardo, jul/2026, revertendo a diretriz anterior de plural nomeado).

Orçamento por projeto, calculado a partir de escopo e tempo; **não há tabela de preços e o site
não publica valores** (decisão do Eduardo, jul/2026).

Site: vertexpage.com.br · Repositório: `eduardoalemanha09-cmyk/vertexpage` · Deploy: Vercel

Contatos: WhatsApp (41) 99741-1544 · Vertex.page@outlook.com · Instagram @Vertexpage

## Restrições invioláveis

1. **Nenhuma prova social inventada.** Até jul/2026 a Vertex não tinha clientes. Depoimentos,
   métricas de volume ("150+ projetos") e percentuais de satisfação foram removidos por serem
   fictícios. Depoimento falso atribuído a pessoa nomeada é publicidade enganosa (CDC art. 37).
   Nada volta ao site sem confirmação explícita do Eduardo de que é real.
2. **Sem portfólio de trabalhos que não existem.** A seção "Estudos de design" (3 maquetes
   conceituais) foi removida a pedido do Eduardo (jul/2026) — "não temos templates prontos".
   Não recriar maquetes fictícias nem rotular concept como cliente. Prova de trabalho = o
   próprio site.
3. **Arquivo único.** `index.html` com CSS e JS embutidos. Sem build, sem framework, sem
   dependência de pacote. `vercel.json` é o único arquivo de apoio.
4. **Sem preço na página.** O caminho é o qualificador → WhatsApp com escopo já montado.
5. **Voz de estúdio, sem nomes.** "A Vertex", "nós" — sem citar Nicoly ou Eduardo no conteúdo
   público (decisão do Eduardo, jul/2026). Tom profissional de empresa. Não inventar tamanho de
   equipe nem cargos específicos ("nosso time de 10", "departamento de X") — a operação é enxuta;
   descrever capacidades (design estratégico, animações, desenvolvimento), não headcount.

## Identidade

**Paleta** — Carvão quente `#0d0c0a` como base, latão `#d9a441` como único acento.
Deliberadamente quente: o público é hotelaria e gastronomia, onde azul de tecnologia soa
deslocado. A moldura é neutra de propósito, para que as maquetes coloridas dos estudos
sejam o ponto focal — a casa é neutra, o trabalho é colorido.

**Tipografia** — Fraunces nos títulos (serifada, com caráter editorial), Inter no texto.

**Marca** — V facetado: duas faces encontrando-se numa aresta central, uma iluminada
(`#d9a441`) e uma na sombra (`#966e2e`). Há um vão físico entre as faces para que a aresta
seja definida por forma, não por cor — assim a marca sobrevive em monocromático, em vinil
e a 20 px. Duas versões: solta (site) e contida em quadrado arredondado (favicon, Instagram).

**Assinatura** — No hero, a marca se monta a partir de partículas dispersas, começando pelo
vértice e crescendo para as arestas. O movimento é a tese do negócio em forma: disperso
convergindo em um ponto. Canvas 2D vanilla, sem biblioteca.

## Três clichês proibidos

O site anterior tinha os três. Nenhum volta:

1. Gradiente azul→roxo em títulos e botões
2. Partículas flutuantes decorativas (a animação atual **forma a marca** — tem função)
3. Card de vidro `rgba(255,255,255,.03)` com borda branca translúcida repetido à exaustão

## Padrões técnicos

- Contraste mínimo AA em todo texto; a paleta atual entrega 6,4:1 no tom mais fraco
- `prefers-reduced-motion` sempre respeitado — animações viram estado final estático
- Animar apenas `transform` e `opacity`; easing de saída, nunca `ease` genérico
- Ícones em SVG inline via sprite `<symbol>`. **Nunca** reintroduzir Font Awesome ou
  qualquer CDN de ícone: eram ~100 KB para 15 glifos
- Todo `<a target="_blank">` leva `rel="noopener"`
- JSON-LD precisa espelhar o conteúdo visível — se o FAQ mudar, o schema muda junto
