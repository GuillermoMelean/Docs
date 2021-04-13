# <b>Publicar um Serviço Windows</b>
## 1º - Clean Geral da Solução
* <i>Right Click</i> na solução -> <i>Clean Solution</i>.
## 2º - Alterar as <i>connectionstrings</i> do Projeto Service
* Clean do Projeto.
* <i>SFSDataExtractionWindowsService</i> -> <i>App.Config</i>. 
* Colocar a apontar para a base de dados correta.
  
  
## 3º - Alterar Configuração da Solução e compilar o projeto do instalador
* Na tab de do Projeto, selecionar <i>Release</i> como configuração da solução.
    * Caso não exista, clickar em <i>Configuration Manager...</i> -> <i>Active Solution Configuration</i> -><i><New...></i> e criar estas duas novas entradas

        | Name | Copy settings from | Create new project configurations |
        | ---- | ---- | ----- |
        | Debug    | Debug  | selected   |
        | Release  | Release  | selected   |

* <i>Right Click</i> no projeto em questão -> <i>Build</i> 

## 4º Abrir a máquina através do <i>Remote Desktop Connection</i>
* Introduzir credenciais de acesso à máquina

## 5º Desativar o service
* Ir aos serviços do windows.
* Procurar por <i>SFSDataExtractionWindowsService</i>
* Botão direito -> Parar / Stop

## 6º Remover o serviço antigo
* Ir ao ambiente de trabalho à pasta <i> WindowsServiceMambu </i>
  * Diretório: <i>/"desktop"/WindowsServiceMambu/</i>
* Correr o <i>setup.exe</i> para fazer a remoção do mesmo.
* Criar a pasta "old" + incremento da versão antiga (por exemplo, "Old14").
* Colocar os 2 ficheiros de instalação dentro da pasta.

## 7º Adicionar a nova atualização do serviço
* Ir buscar os novos ficheiros gerados no passo 3.
* <i>Right Click</i> no projeto -> <i>Open Folder in File Explorer</i>
* Seguir para a pasta: <i>/bin/Release/</i>
* Copiar os ficheiros dessa pasta (em princípio serão 2 também).
* Adicioná-los onde estavam os antigos
  * Diretório: <i>/"desktop"/WindowsServiceMambu/</i>

## 8º Instalar o novo serviço.
* Fazer run do aplicativo <i>setup.exe</i> e fazer "seguinte" sem alterar qualquer definição. 

## 9º Ativar o serviço.
* Ir aos serviços do windows.
* Procurar por <i>SFSDataExtractionWindowsService</i>
* Botão direito -> Correr / Run