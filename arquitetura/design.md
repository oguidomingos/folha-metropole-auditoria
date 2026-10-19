---
name: folha-metropole-publicacao
version: 1.0
escopo: Nível 1 (texto): blog, post, push
idioma: pt-BR
uso: humano e agente de IA
---

# Folha Metrópole — design.md de publicação

Modelo reutilizável de formatação. Serve a quem escreve e a um agente de IA que recebe este arquivo como instrução. Tudo o que está em **REGRA** é verificável por código ou por revisão; o que está em **GUIA** é critério editorial.

## 0. Como usar

**Humano.** Escolha o canal (blog, post, push), copie o template, preencha os campos, rode o checklist da seção 7.

**Agente de IA.** Receba (a) a lista de fatos aprovados com fonte e (b) este arquivo. Produza **somente** os campos pedidos em cada template, em JSON, na ordem em que aparecem. Se faltar fato para preencher um campo, deixe `null` e explique em `pendencias`. Nunca invente número, nome, cargo, data nem citação.

### Regras absolutas (valem para todos os canais)

1. **Fatos, nunca texto de terceiros.** Escrever a partir da lista de fatos, não de parágrafos do veículo de origem. Citação curta só entre aspas e com autor.
2. **Fonte sempre presente.** Toda peça tem o bloco de fonte (seção 6). Sem fonte registrada, não publica.
3. **Selo de IA sempre presente** quando houve apoio de IA: *"Texto produzido com apoio de inteligência artificial e revisado pela redação."*
4. **Neutro e factual.** Sem adjetivo de opinião, sem ironia, sem juízo sobre pessoas. Opinião só em coluna assinada, e coluna fica fora da automação.
5. **Humano aprova antes de publicar.** O agente nunca dispara publicação.
6. **Nunca reutilizar foto, gráfico ou vídeo de outro veículo.**
7. **Nada de emoji em título, linha fina e push.** Nos posts, só se o editor escolher, e no máximo um.

## 1. Voz editorial

| Princípio | Como se aplica |
|---|---|
| Direto | Sujeito + verbo + dado. Primeira frase já diz o que aconteceu. |
| Neutro | "Imparcial sem militância": relata e atribui, não adjetiva. |
| Atribuído | Toda afirmação não verificada pelo jornal tem dono: "segundo a BBC", "informou o órgão". |
| Preciso | Números com unidade e período ("4,5% no terceiro trimestre"). Data relativa com data entre parênteses: "nesta segunda-feira (19)". |
| Sóbrio | Frases curtas (até ~25 palavras). Parágrafos de 2 a 4 linhas. Voz ativa na maior parte. |
| Responsável | Presunção de inocência; sem nome de menor; sem recomendação médica; acusação só com "segundo a polícia/denúncia". |

**Vocabulário.** Preferir "informou", "disse", "segundo", "de acordo com". Evitar: "bomba", "chocante", "polêmica", "escândalo", "veja", "você não vai acreditar" e qualquer isca de clique.

**Números.** Percentual com vírgula decimal e símbolo ("4,5%"). Moeda: "US$ 1,2 trilhão", "R$ 3 milhões". Sempre explicar sigla na primeira menção ("inteligência artificial (IA)").

## 2. Tokens visuais

> Origem: cores e fonte foram **observadas no site folhametropole.com na auditoria** (azul-petróleo, laranja, Poppins). Os demais valores são **derivados** para completar o sistema. O perfil do Instagram não foi auditado: validar com o material atual antes de produzir artes em escala.

### Cores

| Token | Hex | Uso | Contraste |
|---|---|---|---|
| `--fm-petroleo` | `#00334d` | Fundo de capas, cabeçalhos, títulos | base |
| `--fm-laranja` | `#ff9900` | Destaques, faixa de editoria, botão | texto escuro sobre laranja: 6,2:1 (ok) |
| `--fm-laranja-texto` | `#b35c00` | Laranja quando for **texto sobre claro** | 4,7:1 sobre branco (ok) |
| `--fm-papel` | `#ffffff` | Fundo de leitura | texto `#00334d` sobre branco: 13,3:1 |
| `--fm-fundo` | `#f4f6f7` | Cartões, blocos de fonte | |
| `--fm-tinta` | `#1a2a33` | Texto de corpo | 13,6:1 sobre `#f4f6f7` |
| `--fm-cinza` | `#5b6b75` | Texto secundário, crédito | 5,5:1 sobre branco |
| `--fm-alerta` | `#b91c1c` | Plantão, errata | 6,5:1 sobre branco |

**REGRA.** Laranja `#ff9900` **nunca** como cor de texto sobre fundo claro (contraste 2,1:1, ilegível). Em texto sobre claro, usar `--fm-laranja-texto`.

### Tipografia

Família única: **Poppins** (títulos, interface e arte social). Corpo de leitura longa no blog: a do tema do site (manter), com fallback `system-ui`.

| Nível | Peso | Tamanho (blog) | Tamanho (arte 1080 × 1350) |
|---|---|---|---|
| Rótulo da editoria | 600, caixa-alta, espaçamento +0,12em | 12–13 px | 34 px |
| Título (H1) | 700 | 32–36 px / 1,2 | 76–88 px, até 4 linhas |
| Linha fina (H2) | 400 | 18–20 px | 40 px |
| Intertítulo (H2 do corpo) | 600 | 22–24 px | n/a |
| Corpo | 400 | 17–18 px / 1,7 | 38–42 px (card de texto) |
| Crédito/fonte | 400 | 13–14 px, `--fm-cinza` | 28 px |

### Hierarquia na arte (Instagram)

1. Faixa laranja com a **editoria** (topo).
2. **Título** em branco sobre petróleo (ou sobre foto escurecida a 60%).
3. **Selo da fonte** ("Fonte: BBC News") em linha própria no rodapé do card, nunca escondido.
4. Logo no canto inferior direito. Margens de 80 px.
5. Um fato por card de texto, até 35 palavras.

## 3. Template do POST (Nível 1)

Canais: Instagram (feed/carrossel), Facebook, X. O conteúdo é o mesmo; muda o tamanho.

### 3.1 Estrutura (ordem fixa)

1. **Headline**: igual ao título do blog ou versão curta (até 90 caracteres no Instagram).
2. **Lide**: 1–2 frases com o fato principal e o dado mais forte.
3. **Corpo**: 2–4 itens curtos (marcadores) com os números ou fatos de apoio.
4. **Atribuição da fonte**: linha própria, *"Fonte: <veículo>, com dados de <órgão>."* + selo de IA.
5. **CTA**: um só, *"Leia a matéria completa: link na bio."* (Instagram) ou o link (Facebook/X).
6. **Hashtags**: no fim, 3 a 5.

### 3.2 Limites por canal (REGRA)

| Canal | Limite duro | Alvo | Observação |
|---|---|---|---|
| Instagram, legenda | 2.200 caracteres | 500–900 | As ~125 primeiras aparecem antes do "mais": headline e lide têm que caber aí. |
| Instagram, hashtags | 30 | 3–5 | No fim da legenda. |
| Instagram, texto da arte | n/a | título ≤ 90 caracteres; card ≤ 35 palavras | |
| Facebook | ~63.000 | 300–600 | Link da matéria no corpo. |
| X | 280 (link conta 23) | até 260 com link | Sem hashtag se estourar; atribuição "Fonte: X" é obrigatória. |

### 3.3 Hashtags

Fixa: `#FolhaMetrópole`. Mais 2 a 4 temáticas (assunto, não clichê): `#Economia #China #ComércioExterior`. Sem hashtag de opinião, de político ou de torcida. Com acento, conforme a grafia correta.

### 3.4 Modelo para preencher

```
{headline}

{lide}

{rotulo_lista}:
• {fato_1}
• {fato_2}
• {fato_3}

{frase_de_contexto_ou_risco, opcional}

Fonte: {veiculo}, com dados de {orgao_primario}. Texto produzido com apoio de IA e revisado pela redação.

Leia a matéria completa: link na bio.

#FolhaMetrópole #{tema1} #{tema2}
```

## 4. Template do BLOG

### 4.1 Estrutura (ordem fixa)

| # | Elemento | Regra |
|---|---|---|
| 1 | **Rótulo de editoria** | Uma das editorias do jornal (Política, Economia, Mundo, Polícia, Educação, Saúde, etc.). |
| 2 | **Título (H1)** | 80–110 caracteres, declarativo, sujeito + verbo + número quando houver. Sem ponto final. |
| 3 | **Subtítulo / linha fina (H2)** | 1 frase, 100–160 caracteres, traz consequência ou próximo passo. |
| 4 | **Imagem de capa** + crédito | Linha própria: `Foto: <crédito>` ou `Arte: Folha Metrópole`. |
| 5 | **Lide** | 1º parágrafo: quem, o quê, quando, onde. Data relativa: "nesta segunda-feira (19)". |
| 6 | **Banner afiliado** | Slot do Mercado Livre depois do 2º parágrafo (preservar). |
| 7 | **Corpo com intertítulos (H2)** | 3 a 6 intertítulos, frases nominais, um a cada 2–3 parágrafos. |
| 8 | **Bloco de fonte e crédito** | Obrigatório. Seção 6. |
| 9 | **Selo de IA** | Dentro do bloco de fonte. |

**Tamanho.** Notícia factual: 450–700 palavras. Explicativa: até 1.300. Nunca encher texto para bater número.

### 4.2 SEO (REGRA)

| Campo | Regra |
|---|---|
| **Título SEO** | até 60 caracteres, palavra-chave no início, sem caixa-alta |
| **Meta description** | 140–160 caracteres, uma frase completa, com a palavra-chave e o dado principal, sem aspas duplas |
| **Slug** | minúsculas, sem acento, hífens, até 8 palavras, sem artigos e preposições desnecessários, sem data (o WordPress já põe `/AAAA/MM/`) |
| **Palavra-chave principal** | 1 expressão (2–4 palavras), presente no título SEO, na meta description, no 1º parágrafo e em 1 intertítulo |
| **Palavras-chave secundárias** | 2 a 4, viram as tags |
| **Imagem** | nome do arquivo = slug; `alt` descritivo (sem "imagem de"); legenda com crédito |
| **Links** | 1 link para o original (no bloco de fonte), 1 a 2 links internos para matérias relacionadas |

### 4.3 Modelo para preencher

```
editoria: {editoria}
titulo_h1: {80-110 caracteres}
linha_fina: {100-160 caracteres}
titulo_seo: {ate 60}
meta_description: {140-160}
slug: {ate 8 palavras}
palavra_chave: {2-4 palavras}
tags: [{2-4 tags}]
capa: {descricao} | credito: {Foto: ... | Arte: Folha Metrópole}
corpo_md: |
  {lide}

  {2o paragrafo}

  ## {intertitulo_1}
  {paragrafos}
  ## {intertitulo_2}
  {paragrafos}
fonte_bloco: (ver seção 6)
```

## 5. Template do PUSH / notificação

### 5.1 Estrutura e limites (REGRA)

| Campo | Limite | Regra |
|---|---|---|
| **Título** | até 40 caracteres | O fato em uma linha; começa pelo sujeito; sem ponto final; sem caixa-alta |
| **Corpo** | até 100 caracteres | O dado que faz clicar, sem repetir o título; sem isca |
| **Rótulo** (opcional) | até 12 caracteres | Só em plantão: "PLANTÃO" |
| **Destino** | URL da matéria | Sempre a matéria completa, nunca um post de rede social |

### 5.2 Urgência e horário

| Nível | Quando | Quando enviar | Aprovação |
|---|---|---|---|
| **U1, plantão** | Fato de grande impacto, confirmado por **2 fontes** (ou fonte primária) | Na hora, **a qualquer horário** | Humano obrigatório, sem exceção |
| **U2, destaque** | Notícia relevante do dia | Janela 07h–21h (Brasília), primeira janela livre | Humano |
| **U3, resumo** | Compilado ou utilidade pública | 07h30 e 18h (no máximo 2 resumos/dia) | Humano na fase inicial |

**REGRAS de horário.**
- Fora de 07h–21h, só U1.
- No máximo **3 pushes por dia** na soma de U2 e U3; U1 não conta no limite, mas cada plantão precisa de justificativa escrita.
- Intervalo mínimo de **60 minutos** entre pushes (exceto U1).
- Nunca push de matéria em quarentena, sob correção ou em editoria de risco sem humano.
- Sem push sobre tragédia com vítimas identificáveis antes de confirmação oficial.

### 5.3 Modelo para preencher

```
titulo: {ate 40}
corpo: {ate 100}
urgencia: U1 | U2 | U3
agendar_para: {data e hora de Brasília, dentro da janela}
url: {link da matéria}
```

## 6. Bloco de fonte e crédito (obrigatório em todo blog; versão curta em todo post)

**Blog:**

```
Fonte: {veiculo} ({reportagem de {autor}, se houver}, {data}), com dados de {orgao_primario}.
Matéria original: {url}
Texto reescrito pela redação da Folha Metrópole com apoio de inteligência artificial e revisado por {editor}.
```

**Post:** `Fonte: {veiculo}, com dados de {orgao}. Texto produzido com apoio de IA e revisado pela redação.`

**REGRAS.** O veículo de origem é citado pelo nome, não por "imprensa" ou "agências". Se houve mais de um veículo, citar todos ("BBC News e Wall Street Journal"). Se a informação foi só confirmada pelo segundo veículo, ele entra no bloco de fonte mesmo sem ser citado no corpo. Quando o veículo for de linha editorial declarada (perfil C), o corpo atribui a ele cada afirmação ("segundo a Revista X").

## 7. Checklist de validação (humano ou agente)

| # | Verificação | Falhou, então |
|---|---|---|
| 1 | Todos os campos do template preenchidos, nenhum `null` sem pendência | devolver |
| 2 | Título 80–110 caracteres (blog); push ≤ 40; X ≤ 280 contando link como 23; Instagram ≤ 2.200 | encurtar |
| 3 | Meta description 140–160; título SEO ≤ 60; slug ≤ 8 palavras | ajustar |
| 4 | Bloco de fonte presente, com link do original e selo de IA | bloquear |
| 5 | Cada número e nome do texto existe na lista de fatos | bloquear |
| 6 | Teste de cópia: 8-gramas ≤ 3% e nenhuma sequência literal > 12 palavras (exceto nomes e termos de dado) | reescrever |
| 7 | Sem adjetivo de opinião, sem isca de clique, sem emoji no título | reescrever |
| 8 | Sem foto, gráfico ou vídeo de terceiros | bloquear |
| 9 | Push: dentro da janela de horário e do limite diário | reagendar |
| 10 | Editoria de risco (Polícia, Justiça, Saúde, Política) ou menção a empresa do dono: humano marcado como obrigatório | bloquear |

## 8. Exemplos preenchidos

Notícia real usada: **BBC News**, *China's growth accelerates as AI boom helps boost exports*, de Osmond Chia, 19/10/2026 (<https://www.bbc.co.uk/news/articles/cm5yn098xz8lo>). Confirmação do número de 4,5% pelo título do Wall Street Journal (*China's Economy Expanded 4.5% in Third Quarter, Powered by Exports*). As URLs de publicação abaixo são ilustrativas, a matéria **não foi publicada**.

### 8.1 Post, Instagram

```
Economia da China cresce 4,5% no 3º trimestre, puxada por exportações ligadas à IA

O ritmo supera o do trimestre anterior, o menor em três anos, mas fica no piso da meta de Pequim (4,5% a 5%).

O que pesou:
• Vendas de bens de alta tecnologia: +14,3%
• Produção de baterias e de robôs industriais: mais de 29%
• Investimento imobiliário: queda de mais de 20% em nove meses

Analistas alertam para a dependência de um "único motor externo": as exportações.

Fonte: BBC News, com dados do Escritório Nacional de Estatísticas da China. Texto produzido com apoio de IA e revisado pela redação.

Leia a matéria completa: link na bio.

#FolhaMetrópole #China #Economia #ComércioExterior #InteligênciaArtificial
```

Arte (capa 1080 × 1350): faixa laranja "ECONOMIA"; título em branco sobre petróleo; selo "Fonte: BBC News"; sem foto de terceiros, com um mini-gráfico próprio (4,5% vs. 5% no 1º trimestre).

### 8.2 Post, X

```
Economia da China cresce 4,5% no 3º trimestre, puxada por exportações ligadas à IA. Resultado fica no piso da meta de Pequim; investimento imobiliário cai mais de 20% no ano. Fonte: BBC. https://folhametropole.com/2026/10/china-cresce-45-terceiro-trimestre-exportacoes-ia/
```

(210 caracteres contando o link como 23.)

### 8.3 Blog

```
editoria: Economia
titulo_h1: Economia da China cresce 4,5% no 3º trimestre, puxada por exportações ligadas à inteligência artificial   (103)
linha_fina: Resultado fica no piso da meta oficial de Pequim, enquanto a queda de mais de 20% no investimento imobiliário continua pesando sobre o consumo.   (143)
titulo_seo: PIB da China cresce 4,5% no 3º trimestre de 2026   (48)
meta_description: PIB da China avança 4,5% no 3º trimestre de 2026, no piso da meta de Pequim, com exportações ligadas à IA; investimento em imóveis cai mais de 20%.   (147)
slug: china-cresce-45-terceiro-trimestre-exportacoes-ia
palavra_chave: PIB da China
tags: [China, PIB, exportações, inteligência artificial, economia]
capa: infográfico próprio com os dados | credito: Arte: Folha Metrópole, com dados do Escritório Nacional de Estatísticas da China
```

O corpo completo (417 palavras, quatro intertítulos) está em [`exemplo/rascunho.md`](exemplo/rascunho.md) e na seção 4 do documento de arquitetura. Trechos que mostram o padrão:

- **Lide:** "A economia da China avançou 4,5% no terceiro trimestre de 2026, segundo dados oficiais divulgados nesta segunda-feira (19)."
- **Intertítulos:** *Exportações de tecnologia sustentam o resultado* · *Consumo e imóveis seguem fracos* · *O que dizem os analistas* · *Pressão externa*
- **Bloco de fonte:**

```
Fonte: BBC News (reportagem de Osmond Chia, 19/10/2026), com dados do Escritório Nacional de Estatísticas da China.
Matéria original: https://www.bbc.co.uk/news/articles/cm5yn098xz8lo
Texto reescrito pela redação da Folha Metrópole com apoio de inteligência artificial e revisado por {editor}.
```

### 8.4 Push

```
titulo: China cresce 4,5% no 3º trimestre
corpo: Exportações de tecnologia ligadas à IA seguram o resultado; imóveis seguem em queda.
urgencia: U2
agendar_para: 19/10/2026, 18h30 (Brasília)
url: https://folhametropole.com/2026/10/china-cresce-45-terceiro-trimestre-exportacoes-ia/
```

(título 33 caracteres, corpo 84.)

## 9. Origem e pendências deste arquivo

- Produzido pela Expoente para a Folha Metrópole em 19/10/2026. Não existia um design.md oficial da Expoente na VPS; este arquivo é o padrão de **publicação** da Folha Metrópole e deve ser revisado pelo Charles.
- O **Claude Design** (claude.ai/design) não estava acessível nesta execução (exige autorização interativa, `/design-login`). Os tokens aqui foram montados por observação do site e podem ser importados ao Claude Design depois, para gerar os cartões visuais.
- Pendente: auditar o Instagram `@folhametropole` (login e token), confirmar o tema da fonte de leitura do blog e a ferramenta de push usada pelo site.
