# Relatório de Campo — Coelho Guedes Assessoria Naval

Aplicativo web (PWA) para relatórios de inspeção com registro fotográfico.
Gera o mesmo relatório da planilha-modelo, em PDF A4.

## 1. Publicar no GitHub Pages (uma vez, ~10 minutos)

1. Crie uma conta em github.com (se ainda não tiver) e clique em **New repository**.
2. Nome sugerido: `relatorio-campo`. Marque **Public** e crie.
3. Na página do repositório: **Add file → Upload files** e arraste TODOS os arquivos
   desta pasta (`index.html`, `manifest.webmanifest`, `sw.js` e os quatro ícones).
   Clique em **Commit changes**.
4. Vá em **Settings → Pages**. Em *Source*, escolha **Deploy from a branch**,
   branch `main`, pasta `/ (root)`. Salve.
5. Em 1 a 2 minutos o endereço aparece no alto da mesma tela, no formato
   `https://SEU-USUARIO.github.io/relatorio-campo/`. Esse é o endereço do aplicativo.

O endereço é https, e é isso que faz o GPS funcionar e o atalho na tela inicial aparecer.

## 2. Instalar no celular

**Android (Chrome, Edge, Mi Browser):** abra o endereço, toque no menu de três pontos e
escolha **Instalar aplicativo** (ou *Adicionar à tela inicial*). O ícone da Coelho Guedes
fica na tela inicial e o app abre em tela cheia.

**iPhone (só pelo Safari):** abra o endereço no **Safari**, toque no botão Compartilhar
(quadrado com seta) e escolha **Adicionar à Tela de Início**. O Chrome do iPhone não
oferece essa opção — no iOS, apenas o Safari instala.

Depois de instalado, o app abre e funciona **sem internet**. A internet só é usada para
converter coordenadas em endereço.

## 3. Senha da equipe

A senha vem definida como `CG2026`. Para trocar, abra `index.html`, procure a linha:

```js
const SENHA = "CG2026";
```

Troque o texto entre aspas, salve e envie o arquivo de novo ao repositório.

A senha serve para manter o link fora do alcance de curiosos. Como o aplicativo roda
inteiro no navegador, quem entende de tecnologia consegue ler o código-fonte da página e
ver a senha — não use aqui uma senha que você usa em outro lugar. Nenhum relatório é
enviado para servidor nenhum: tudo fica no próprio aparelho.

## 4. Publicar uma versão nova

Ao substituir o `index.html`, abra também o `sw.js` e mude o número da versão:

```js
const VERSAO = "cg-relatorio-v1";   // v2, v3...
```

Sem isso, os celulares que já instalaram continuam abrindo a versão antiga guardada.

## 5. Mudar para o domínio da empresa

Quando quiser `relatorio.coelhoguedes.com.br`, basta apontar um subdomínio para o
GitHub Pages (Settings → Pages → Custom domain) ou copiar estes mesmos arquivos para uma
pasta do site atual. Nada no aplicativo precisa ser alterado — todos os caminhos são
relativos.

## Arquivos

| Arquivo | Para que serve |
|---|---|
| `index.html` | O aplicativo inteiro |
| `manifest.webmanifest` | Nome, ícone e cores da instalação |
| `sw.js` | Faz o app funcionar sem internet |
| `icon-192.png`, `icon-512.png`, `icon-maskable-512.png` | Ícones Android |
| `apple-touch-icon.png` | Ícone iPhone |
