# <b>Publicar um Web Job no Portal Azure Manualmente</b>
## 1º - Clean Geral da Solução
* <i>Right Click</i> na solução -> <i>Clean Solution</i>.
## 2º - Alterar as <i>connectionstrings</i> do Projeto Models
* Clean do Projeto.
* <i>Models</i> -> <i>App.Config</i>. 
* Colocar a apontar para a base de dados correta.

## 3º - Alterar as <i>connectionstrings</i> do WebJob
* Projeto em Questão -> <i>App.Config</i>. 
* Caso o projeto faça diferenciação de PRD/PP
    * <i>App.Debug.Config</i> tem de ficar com as <i>connectionstrings</i> iguais ao ficheiro .<i>App.Release.Config</i>.
* <i>Models</i> -> <i>App.Config</i> colocar a apontar para a base de dados correta.

## 4º - Alterar Configuração da Solução
* Na tab de do Projeto, selecionar <i>Release</i> como configuração da solução.
    * Caso não exista, clickar em <i>Configuration Manager...</i> -> <i>Active Solution Configuration</i> -><i><New...></i> e criar estas duas novas entradas

        | Name | Copy settings from | Create new project configurations |
        | ---- | ---- | ----- |
        | Debug    | Debug  | selected   |
        | Release  | Release  | selected   |

* <i>Right Click</i> no projeto em questão -> <i>Build</i> 

## 5º - Obter o ficheiro
* <i>Right Click</i> no projeto -> <i>Open Folder in File Explorer</i>
* Seguir para a pasta: <i>/bin/Release/</i>
* Remover as <i>.dll</i> desnecessárias.
* Reunir todos os restantes ficheiros e <i>zippar</i>.

## 6º - Publicar no Azure
* Entrar no [<u>Portal do Azure</u>](https://portal.azure.com).
* Selecionar a <i>app service</i> em questão.
* Depois seguir <i>Settings</i> -> <i>WebJobs</i> -> <i>Add</i> -> Introduzir um nome, o ficheiro gerado anetiormente e o tipo.
    * Caso seja <i>Continuous</i> ter atenção se é single ou multi instância
    * Caso seja <i>Triggered</i> e se for Scheduled ter atenção às normas da [<u>CRON Expression</u>](https://go.microsoft.com/fwlink/?LinkId=823235).