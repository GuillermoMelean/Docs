# <b>Publicar Android APP</b>

## 1º - Clean Geral da Solução
* <i>Right Click</i> na solução -> <i>Clean Solution</i>.

## 2º - Apagar ficheiros de <i>builds</i> anteriores.
* Pode não ser preciso, mas, para garantir que é feito mesmo um <i>rebuild</i> da aplicação, é necessário apagar a pasta <i>bin</i> e <i>obj</i>.

## 3º - Garantir o ambiente de <i>release</i> do projeto.
* Na barra superior, selecionar qual o ambiente para onde o projeto vai ser compilado.
* Neste caso, selecionar <i>RELEASE</i>. :warning:

## 4º - Incrementar a versão da aplicação 
    (no caso de ser a primeira vez, ignorar este passo)
* <i>Right Click</i> no projeto -> Propriedades.
* Ir para Tab <i>Android Manifest</i>.
* Incrementar o número da versão em <i>Version number</i>.

## 5º - Fazer <i>build</i> à solução 
* <i>Right Click</i> no projeto -> <i>rebuild</i>.

## 6º - fazer <i>archive</i> à solução
* <i>Right Click</i> no projeto -> <i>archive</i>.
* <u>Este processo pode ser demorado.</u> 

## 7º - Fazer a assinatura para o .APK
* Selecionar '<i>Distribute ...</i>' -> Ad Hoc.
* Selecionar o <i>Signing Identity</i> para a publicação.
    * Caso não exista, clickar em <i>Import...</i> -> Pelo <i>File Explorer</i> ir buscar a <i>keystore</i> e introduzir os dados pedidos.
* Selecionar <i>Save As</i>.
* O programa abre o <i>File Explorer</i> para guardar o ficheiro .apk.

## 8º - Publicar no <i>Google Play Console</i>
* Entrar no [<u>Google Play Console</u>](https://play.google.com/apps/publish/).
* Selecionar a aplicação em questão.
* Nas tabs selecionar '<i>Release Management</i>' -> '<i>App Releases</i>'.
* Na secção do <i>Alpha</i> selecionar em '<i>Manage</i>'.
* Selecionar '<i>Create Release</i>'.
* Fazer upload do ficheiro que foi extraido no passo anterior.
* Selecionar '<i>Review</i>'.
* Selecioanr '<i>Start Roll-Out</i>'.

## 9º Aguardar resposta da <i>Google</i>
* Se o passo anterior deu sucesso, neste momento apenas resta esperar pela informação de aprovação por parte da <i>Google</i>.
