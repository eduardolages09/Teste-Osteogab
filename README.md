# Caderno de Sessão (protótipo)

Protótipo de uma app para registar sessões de fisioterapia no ginásio, pensada para iPad.

- Um único ficheiro: `index.html` (HTML, CSS e JavaScript, sem dependências nem build).
- Os dados são fictícios e ficam guardados só no browser de cada aparelho (localStorage).
- Para entrar: escolher um terapeuta e usar o PIN `1234`.

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
