#### Commit
to commit changes made in order to have a descriptive commit message
```
ECHO OFF
CLS
:MENU
ECHO.
ECHO ...............................................
ECHO Qual o tipo da atividade?
ECHO ...............................................
ECHO.
ECHO 1 - Novo Requisito
ECHO 2 - Melhoria
ECHO 3 - Correcao nao impactante
ECHO 4 - Correcao Quente
ECHO 5 - Bug
ECHO 6 - Configuracao
ECHO 7 - Outros
ECHO 0 - EXIT
ECHO.
SET /P M=Escolha uma opcao de 1 a 7 ou 0 para sair: 
SET TAG =
IF %M%==0 EXIT


IF %M%==1 SET TAG=NOVO
IF %M%==2 SET TAG=MELHORIA
IF %M%==3 SET TAG=CORRECAO
IF %M%==4 SET TAG=HOTFIX
IF %M%==5 SET TAG=BUG
IF %M%==6 SET TAG=SETUP
IF %M%==7 SET TAG=OUTROS


@Echo ------------------------------------------------------------------------
SET /P V=Versao do Sistema: 

@Echo ------------------------------------------------------------------------
SET /P A=Atividade Numero (sem #): 

@Echo ------------------------------------------------------------------------
SET /P D=Descricao do Commit:  

@Echo ------------------------------------------------------------------------

SET commitMessage = %V% 
SET commitMessage = %commitMessage% and %TAG% 
SET commitMessage = %commitMessage% and %A% 
SET commitMessage = %commitMessage% and %D%  

@Echo ------------------------------------------------------------------------
SET "commitMessage=%V% [%TAG%] #%A% - %D%"

@Echo Mensagem de Commit: %commitMessage%
ECHO Conformar Commit? 
ECHO 1 - Confirmar 
ECHO Qualquer outra tecla - Cancelar 
SET /P C= Informe a opcao e tecle enter 
@Echo ------------------------------------------------------------------------
IF NOT %C% == 1 EXIT
@Echo ------------------------------------------------------------------------
@Echo Adicionando arquivos ao commit
@Echo ------------------------------------------------------------------------
git add .
@Echo ------------------------------------------------------------------------
@Echo Executando commit
@Echo ------------------------------------------------------------------------
git commit -m "%commitMessage%"
@Echo ------------------------------------------------------------------------
@Echo Executando push
@Echo ------------------------------------------------------------------------
git config --global push.default current
git push origin
@Echo ------------------------------------------------------------------------
@Echo Finalizado. 
SET /P TO_EXIT=Aperte qualquer tecla para sair 
EXIT
```
