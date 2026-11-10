# Como publicar o Credenciais · Cases IA

Versão derivada da v2 (11.2026) para prospecção em que IA é central. Mantém as
telas institucionais da v2, o índice de cases, e troca os cases por quatro:
**Lake Baikal · Agrícola Famosa · Núcleo de Marcas · Odontoprev (Mães e Pais)**.
Sem capas de cliente.

Repositório próprio, **histórico novo** — não tem nenhum commit da v2, então um
push aqui nunca mexe no `wtag-credenciais-v2`.

## Primeira publicação

1. No GitHub, organização **wtag**, criar o repositório **vazio**
   `wtag-credenciais-casesIA` (sem README, sem `.gitignore`, sem licença).
   Visibilidade: a mesma da v2 (Pages em repo privado exige plano pago).
2. Abrir o **GitHub Desktop** → *File → Add Local Repository…* → escolher
   `~/Projetos/wtag-credenciais-casesIA`.
3. Conferir o commit inicial e clicar **Publish repository** (organização
   `wtag`, mesmo nome). Ou, pelo terminal, se o Desktop já autenticou:

   ```bash
   cd ~/Projetos/wtag-credenciais-casesIA
   git remote add origin https://github.com/wtag/wtag-credenciais-casesIA.git
   git push -u origin main
   ```

4. No repositório: **Settings → Pages** · Source `Deploy from a branch` ·
   Branch `main` · pasta `/ (root)` · Save.
5. Em 1–2 minutos o deck está em
   `https://wtag.github.io/wtag-credenciais-casesIA/`
   e a versão de celular em `.../mobile.html`.

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
