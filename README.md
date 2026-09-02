# Painel Conciliação Tasy × Polo — Dashboard

Dashboard estático que lê os dados de um arquivo `data.json` publicado
junto com o site. **Não depende mais do Google Sheets.**

## Como o fluxo funciona
1. Você me manda os dois relatórios (Tasy + Polo).
2. Eu gero um `data.json` novo com os números do dia.
3. Eu publico esse `data.json` direto no repositório do GitHub (via API,
   com o token que você configurar).
4. O Vercel detecta o push e republica o site sozinho, em segundos.
5. Você não precisa abrir planilha nenhuma nem fazer upload manual.

## Configuração necessária (uma vez só)
1. Crie um repositório no GitHub (ex.: `painel-conciliacao`) com os
   arquivos `index.html` e `data.json` (o daqui mesmo, como primeira
   versão) na raiz.
2. Gere um **Personal Access Token** com permissão de escrita nesse
   repositório (de preferência um token "fine-grained", restrito só a
   esse repo) e me envie.
3. Conecte esse repositório ao Vercel (Add New → Project → selecionar o
   repositório → Deploy). Nenhuma configuração de build é necessária.
4. A partir daí, toda vez que eu publicar um `data.json` novo, o site
   atualiza sozinho.

## Arquivos
- `index.html` — o dashboard (não muda no dia a dia)
- `data.json` — os dados do dia (isso é o que eu atualizo a cada rodada)
- `publicar_dashboard.py` — script que gera o `data.json` a partir dos
  relatórios brutos (uso interno meu)

