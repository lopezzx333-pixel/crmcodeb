# codeboost CRM

CRM simples de clientes em um único arquivo (`index.html`), sem bibliotecas e sem servidor próprio.
Com o banco compartilhado configurado, todas as alterações aparecem para todos em até 5 segundos.

## Arquivos

- `index.html`: o CRM completo.
- `database.rules.json`: regras do Firebase Realtime Database.
- `.nojekyll`: faz o GitHub Pages servir o arquivo exatamente como está.

## 1. Criar o banco compartilhado (Firebase)

1. Acesse https://console.firebase.google.com e crie um projeto.
2. Em **Build > Realtime Database**, clique em **Create Database**.
3. Na aba **Rules**, cole o conteúdo de `database.rules.json` e clique em **Publish**.
4. Copie a URL do banco, por exemplo `https://meu-projeto-default-rtdb.firebaseio.com`.

## 2. Ligar o CRM ao banco

Abra o `index.html` em um editor de texto, procure `const DB_URL=''` e cole a URL entre as aspas:

```js
const DB_URL='https://meu-projeto-default-rtdb.firebaseio.com';
```

Com `DB_URL` vazio, o CRM funciona em modo local, só no navegador de quem usa.

## 3. Publicar no GitHub Pages

1. No repositório, clique em **Add file > Upload files** e envie todos os arquivos desta pasta.
2. Vá em **Settings > Pages**, escolha **Deploy from a branch**, branch `main`, pasta `/ (root)`, e salve.
3. Em cerca de um minuto o CRM abre em `https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO/`.

## Avisos

- Qualquer pessoa com o link pode ver, editar e excluir cadastros.
- Telefones, e-mails e observações ficam visíveis para todos; são dados pessoais de terceiros (LGPD).
- Se duas pessoas editarem o mesmo cliente ao mesmo tempo, vale a última gravação.
- Use **Exportar backup** de vez em quando.
