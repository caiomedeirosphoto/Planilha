# Como publicar a Planilha Financeira

São três partes, uns 20 minutos no total, feitos uma vez só. Tudo é grátis.

## Parte 1: Firebase (onde ficam os seus dados)

1. Entre em **console.firebase.google.com** com a sua conta Google.
2. Toque em **Criar um projeto**, dê o nome `planilha-financeira` e continue. O Google Analytics pode ficar desligado.
3. No menu da esquerda, abra **Criação** (ou *Build*) e depois **Authentication**. Toque em **Vamos começar**.
4. Na aba **Método de login**, escolha **E-mail/senha**, ligue a primeira chave e salve.
5. Volte em **Criação** e abra **Firestore Database**. Toque em **Criar banco de dados**.
   - Local: **southamerica-east1 (São Paulo)**.
   - Modo: **produção**.
6. Ainda no Firestore, abra a aba **Regras**. Apague o que estiver lá, cole o conteúdo do arquivo `firestore.rules` desta pasta e toque em **Publicar**.
7. Toque na engrenagem, ao lado de "Visão geral do projeto", e abra **Configurações do projeto**. Em **Seus apps**, toque no ícone **</>** (Web).
   - Apelido: `planilha`.
   - **Não** marque o Firebase Hosting.
   - Toque em **Registrar app**.
8. Vai aparecer um código com `const firebaseConfig = { ... }`. Abra o arquivo `firebase-config.js` desta pasta num editor de texto e troque cada `COLE_AQUI` pelo valor correspondente, mantendo as aspas e as vírgulas. Salve.

Se preferir, mande esse bloco de configuração no chat que o arquivo volta pronto. Ele não é segredo: a proteção dos dados está nas regras do passo 6, que só deixam cada conta ver os próprios dados.

## Parte 2: GitHub Pages (onde o app fica no ar)

1. Crie uma conta grátis em **github.com**, se ainda não tiver.
2. Toque em **New repository**.
   - Nome: `planilha`.
   - Marque **Public**.
   - Toque em **Create repository**.
3. Na página do repositório, toque em **uploading an existing file**. Arraste **tudo o que está dentro** desta pasta, inclusive a pasta `icons`, e toque em **Commit changes**.
4. Abra **Settings** e depois **Pages**.
   - Em **Source**, escolha **Deploy from a branch**.
   - Em **Branch**, escolha **main** e **/(root)**.
   - Toque em **Save**.

   Em um ou dois minutos aparece o endereço, no formato `https://SEU-USUARIO.github.io/planilha/`.
5. Volte ao Firebase, abra **Authentication**, depois **Configurações** e **Domínios autorizados**. Adicione `SEU-USUARIO.github.io`.

## Parte 3: instalar e trazer os dados

**No iPhone:** abra o endereço no **Safari**, toque em **Compartilhar** e depois em **Adicionar à Tela de Início**. Abra pelo ícone novo e toque em **Criar conta**.

**No computador:** abra o endereço no **Chrome** ou no **Edge** e toque no ícone de instalar, na ponta direita da barra de endereço. Entre com a mesma conta.

**Para trazer os dados que você já tem:**
1. Na versão atual, dentro do Claude, vá em **Ajustes** e toque em **Baixar backup**.
2. No app novo, já com a conta criada, vá em **Ajustes**, toque em **Restaurar backup** e escolha o arquivo.

Tudo vem junto: lançamentos, limites, contas fixas, metas, orçamentos e a base do preço.

## Quando houver uma versão nova

Substitua o `index.html` no GitHub: **Add file**, depois **Upload files**, arraste o arquivo novo com o mesmo nome e toque em **Commit changes**. O app pega a versão nova na próxima vez que abrir com internet.
