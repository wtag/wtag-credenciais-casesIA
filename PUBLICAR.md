# Como publicar o Credenciais · Cases IA

Versão derivada da v2 (11.2026) para prospecção em que IA é central. Mantém as
telas institucionais da v2, o índice de cases, e troca os cases por quatro:
**Lake Baikal · Agrícola Famosa · Núcleo de Marcas · Odontoprev (Mães e Pais)**.
Sem capas de cliente.

Repositório próprio, **histórico novo** — não tem nenhum commit da v2, então um
push aqui nunca mexe no `wtag-credenciais-v2`.

## Primeira publicação

O repositório `wtag/wtag-credenciais-casesIA` **já foi criado** no GitHub (vazio).
Por isso o botão *Publish repository* do GitHub Desktop dá erro ("name already
exists"): ele tenta criar o repositório de novo. O caminho é só ligar a pasta a
ele e enviar:

1. Ligar a pasta ao repositório (uma vez só):

   ```bash
   cd ~/Projetos/wtag-credenciais-casesIA && git remote add origin https://github.com/wtag/wtag-credenciais-casesIA.git
   ```

2. No GitHub Desktop, o botão do topo vira **Publish branch** / **Push origin**:
   clicar. O envio usa o login do Desktop.
3. No repositório: **Settings → Pages** · `Deploy from a branch` · `main` ·
   `/ (root)` · Save.
4. Em 1–2 minutos: `https://wtag.github.io/wtag-credenciais-casesIA/`
   (celular: `.../mobile.html`).

**Regra para as próximas versões** — escolha UM dos dois caminhos, nunca os dois:
- **Sem criar nada no GitHub antes:** Desktop → *Add Local Repository* →
  *Publish repository* (escolhendo a organização `wtag`). Ele cria e envia.
- **Ou** criar o repositório vazio no GitHub e seguir os passos 1–3 acima.

## Depois de mexer no conteúdo

```bash
python3 gerar-mobile.py      # regera o mobile.html a partir do index.html
```

Mexeu em `css/` ou `js/`? Suba o `?v=NN` no `index.html` (e rode o
gerar-mobile, que copia o número). Depois: commit e push no GitHub Desktop.

## O que NÃO entra no repositório

- `_Assets/` — material bruto recebido (fotos em alta, vídeos de origem, docx).
  O deck usa as versões tratadas em `assets/`.
- `WT.AG_*.pdf`, `index_pdf_*.html`, `index_review.html` — gerados.

## PDF (quando precisar)

`python3 gerar-pdf.py` gera `WT.AG_Credenciais_CasesIA_PT/EN.pdf`.
`publicar-pdf.py` agora publica em `WTA_Credenciais/PDF_CasesIA` no Drive —
pasta separada de propósito: o script manda para `_refugo/` todo PDF que
estiver na pasta de destino, e na pasta `PDF` estão os da v2. Crie a pasta
`PDF_CasesIA` antes da primeira rodada.
