# Caderno de Sessão (protótipo)

Protótipo de uma app para registar sessões de fisioterapia no ginásio, pensada para iPad.

- Um único ficheiro: `index.html` (HTML, CSS e JavaScript, sem dependências nem build).
- Os dados são fictícios e ficam guardados só no browser de cada aparelho (localStorage).
- Para entrar: escolher Gabriel Nunes (diretor clínico) e usar o PIN `1234`. O resto da equipa é adicionado por ele: nome no canto de cima → **Equipa** (nome, função, PIN de 4 algarismos e se pode editar protocolos). A equipa fica guardada no iPad e mantém-se ao repor os dados de demonstração.

Para abrir localmente, basta abrir `index.html` no browser.

## Biblioteca de exercícios

A biblioteca (cerca de 385 exercícios, em 12 regiões) está no topo do `<script>`, na constante `LIB`, em texto simples:

```
# Região
## Tipo
= Família (as variantes da mesma família são alternativas umas das outras)
Nome | material | medida | prescrição | u | id
```

- Medida: `r` repetições, `s` segundos, `n` minutos, `m` metros, seguida de `k` (carga em kg) ou `b` (cor do elástico).
- Prescrição: `3x12@2` = 3 séries de 12 com 2 kg (ou com o elástico de nível 2, nos exercícios com `b`).
- `u` marca um exercício unilateral (regista esquerdo e direito em separado).

Os exercícios criados ou editados na app pelo diretor clínico ficam guardados no aparelho e têm prioridade sobre a biblioteca.

## Miniaturas animadas

Onze exercícios têm uma miniatura animada (constante `DEMO`, antes do bloco "Render"): pêndulo, wall slide, rotação externa com elástico, elevação lateral, flexão na parede, agachamento goblet, step-up, peso morto romeno, ponte glútea, elevação de gémeos e bird dog. Aparece ao lado do nome sempre que se escolhem exercícios ("Preparar treino", "+ Exercício" na sessão e biblioteca), para reconhecer o exercício de relance. A app é de uso interno: não há explicações para o paciente. Na versão final, a ideia é trocar as miniaturas por vídeos curtos gravados na clínica.

## Outros nomes (pesquisa)

A constante `AKA`, logo a seguir à `LIB`, junta a cada exercício outros nomes por que é conhecido (inglês, nomes de ginásio, abreviaturas), no formato `Nome exato: outro nome; outro nome`. A pesquisa encontra o exercício por qualquer um deles e mostra "também: …" quando o encontrou por outro nome. Também se editam na ficha do exercício (diretor clínico). A lista final decide-se com a equipa.

## iPad

Está afinada para o iPad, tanto ao alto como deitado:
- **iPad ao alto (744 a 1000 px):** a barra de cima fica numa só linha. O "Preparar treino" e a sessão mantêm as duas colunas. Abaixo de 700 px (Split View e telemóvel) passa ao layout de uma coluna.
- **Toque:** sem zoom com toque duplo nos botões + e −, efeito de pressão nos botões e hover só onde há rato.
- **Safari:** nenhum campo abaixo de 16 px, para o iOS não fazer zoom ao escrever. A página inteira não "puxa" e o ecrã não se apaga durante a sessão.
- **Ecrã principal:** ícone com o logo da Osteogab em fundo branco (pasta `icons/` e `manifest.webmanifest`), ecrã inteiro e zonas seguras (a barra de baixo do iPad não tapa o rodapé). No Safari: Partilhar → Adicionar ao ecrã principal.

## Ideias para a app (provisório, só no piloto)

O botão **Ideia**, na barra de cima, está sempre à mão, também a meio da sessão. Serve para a equipa anotar o que mudaria, o que faltou ou o que correu mal. Cada ideia guarda quem a escreveu, quando e onde estava na app (por exemplo, "Sessão · Pêndulo de Codman"). Em "Ver as ideias" aparecem todas, e "Enviar todas" abre o menu de partilha do iPad (WhatsApp, email…) ou copia o texto. As ideias ficam no aparelho (`D.ideas`) e "Repor dados de demonstração" não as apaga. Para retirar o botão no fim do piloto, pôr `PILOTO = false` no script.
