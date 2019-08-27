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






# <b>Publicar iOS APP</b>

## 1º - Garantir ficheiros na máquina Apple
* <i>Provisioning Profiles</i> e os certificados têm de estar instalados na máquina.
* Pode ser obtidos no [<u>Apple Delevolper</u>](https://developer.apple.com/account/resources/profiles/list).

## 2º - Clean Geral da Solução
* <i>Right Click</i> na solução -> <i>Clean Solution</i>.

## 3º - Garantir o ambiente de <i>release</i> do projeto.
* Na barra superior, selecionar qual o ambiente para onde o projeto vai ser compilado.
* Neste caso, selecionar <i>release</i>. :warning: 

## 4º - Apagar ficheiros de <i>builds</i> anteriores.
* Pode não ser preciso, mas, para garantir que é feito mesmo um <i>rebuild</i> da aplicação, é necessário apagar a pasta <i>bin</i> e <i>obj</i>.

## 5º - Incrementar a versão da aplicação 
    (no caso de ser a primeira vez, ignorar este passo)
* <i>Right Click</i> no ficheiro '<i>Info.plist</i>' -> <i>Open With...</i> -> <i>iOS Manifest Editor</i>.
* Incrementar o campo onde indica ser a versão.

## 6º - Fazer <i>build</i> à solução 
* <i>Right Click</i> no projeto -> <i>rebuild</i>.

## 7º - Obter ficheiro .IPA
* <i>Right Click</i> no projeto em questão -> <i>Open Folder in File Explorer</i>.
* Seguir o Path: '<i>...\bin\iPhone\Release</i>'.
* Na pasta acima descrita estará o ficheiro .ipa com o nome <i>nome_do_projeto.ipa</i>.

## 8º - Publicar para a <u>App Store</u>
* Copiar o ficheiro para a máquina Apple.
* Abrir o software <i>Application Loader</i> 
* Selecionar o certificado correto :warning: 
* Fazer upload do ficheiro.
* Selecionar seguinte até o programa ficar a carregar o ficheiro para a App Store.
* Quando o carregamento estiver finalizado, selecionar concluir.

## 9º Aguardar resposta da <i>Apple</i>
* Se o passo anterior deu sucesso, neste momento apenas resta esperar pela informação de aprovação por parte da <i>Apple</i>.
