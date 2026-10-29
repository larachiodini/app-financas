# Minhas Finanças

App pessoal de finanças que roda direto no navegador, sem servidor e sem login. É um único arquivo (`index.html`).

## O que tem

- **Início**: saldo do mês, entradas e saídas, barra de proporção e avisos de contas que vencem nos próximos 7 dias (ou atrasadas).
- **Lançar**: adicionar entradas, saídas e contas a pagar (com opção de repetir todo mês).
- **Dashboard**: gastos por categoria, comparação dos últimos 6 meses e resumo do mês.
- **Parcelados**: quanto falta de cada dívida, valor da parcela, próximo vencimento e mês em que termina.
- **Faturas**: envio de arquivos. CSV e OFX viram lançamentos (com revisão antes de importar); PDF e imagens ficam guardados para consulta. 

- **Ajustes**: senha de 4 dígitos para abrir o app, bloqueio automático e backup dos dados.

## Como publicar no GitHub Pages

1. Crie um repositório no GitHub (ex.: `minhas-financas`).
2. Envie o arquivo `index.html` para a raiz do repositório (botão **Add file → Upload files**).
3. Vá em **Settings → Pages**.
4. Em **Source**, escolha **Deploy from a branch**, branch `main`, pasta `/ (root)` e clique em **Save**.
5. Em 1 ou 2 minutos o app estará em `https://SEU-USUARIO.github.io/minhas-financas/`.

## Onde ficam os dados

Os dados ficam salvos **só no navegador** em que você usa o app (localStorage e IndexedDB). Nada vai para o GitHub, então mesmo com o repositório público suas finanças ficam privadas.

Por isso:
- Use **Exportar backup** de vez em quando.
- Para usar em outro aparelho, exporte o backup em um e importe no outro.
- Limpar os dados do navegador apaga as informações do app.

## Importar faturas

- **CSV**: precisa ter colunas de data e valor (descrição é opcional). Funciona com o CSV da fatura do Nubank e com a maioria dos extratos que usam `;` ou `,`.
- **OFX**: o formato de extrato que quase todo banco exporta.
- Na revisão, marque “Valores positivos são gastos” para faturas de cartão de crédito e desmarque para extratos de conta corrente.

## Lembretes

O botão **Ativar lembretes** mostra uma notificação do navegador quando há conta vencendo hoje ou amanhã. A notificação aparece ao abrir o app (não funciona com o app fechado).

## Senha de acesso

Em **Ajustes** você cria uma senha de 4 números. O app passa a pedir a senha toda vez que é aberto e, se você quiser, também depois de 1 minuto fora dele. Após 5 tentativas erradas, o teclado trava por 30 segundos.

A senha é guardada como hash, não em texto. Ela impede que alguém abra o app no seu aparelho, mas não criptografa os dados: quem tiver acesso técnico ao navegador ainda conseguiria lê-los.

Se esquecer a senha, a opção “Esqueci a senha” apaga todos os dados para liberar o app. Depois é só importar seu último backup.
