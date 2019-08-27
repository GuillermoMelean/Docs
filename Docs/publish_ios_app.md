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
