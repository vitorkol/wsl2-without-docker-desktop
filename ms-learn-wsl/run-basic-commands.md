# Prática de comandos usando WSL
Já vimos alguns comandos administrativos básicos do WSL, incluindo `wsl --install` e `wsl --list --online`, bem como alguns comandos básicos do Linux, incluindo `mkdir` para criar um diretório e `sudo apt install` <x> para instalar software, mas vamos explorar outros e tentar concluir algumas tarefas comuns.

## Testar alguns comandos WSL básicos
Os comandos WSL neste treinamento são listados em um formato compatível com PowerShell ou CMD (Prompt de Comando do Windows). Para executar esses comandos em uma linha de comando Bash/de distribuição do Linux, você deve substituir `wsl` por `wsl.exe`. Isso ocorre porque o WSL é gerenciado no sistema de arquivos do Windows como um arquivo executável... mas os arquivos executáveis do Windows também podem ser executados no Linux, desde que você inclua a extensão do arquivo.

Abra uma linha de comando do PowerShell e vamos testar algumas tarefas básicas de gerenciamento do WSL usando os comandos de administração do WSL:
1. Verifique qual versão do WSL você instalou usando: `wsl --version`. Você verá uma versão listada para:

- WSL
- o kernel do Linux usado pelo WSL
- a versão do WSLg, que executa aplicativos de GUI do Linux
- a versão do MSRDC, que representa o cliente Área de Trabalho Remota da Microsoft que dá suporte ao WSL
- as versões do Direct3D e DXCore, usadas para renderização de gráficos
- a versão do Windows que você está executando

2. Use o comando: `wsl --update` para garantir que tenhamos as atualizações mais recentes do WSL.

3. Liste as distribuições do Linux que você instalou no momento inserindo: `wsl --list --verbose`.

4. Verifique quais distribuições estão disponíveis por meio da Microsoft Store, use `wsl --list --online` e tente instalar uma nova distribuição, inserindo: `wsl --install <Distribution Name>`. Confirme se a distribuição foi instalada usando o comando `wsl --list` novamente.

5. Tente alterar a distribuição padrão do Linux do Ubuntu (ou o que você instalou pela primeira vez se não for o padrão) para a distribuição que acabou de instalar usando o comando: `wsl --set-default <Distribution Name>`. Você pode alterar novamente usando o mesmo comando.

6. Abra sua linha de comando Bash (da distribuição Linux definida como padrão) para o diretório inicial do seu sistema de arquivos WSL inserindo o comando: `wsl ~` de dentro do PowerShell. Você verá que permanece dentro da mesma janela de linha de comando do PowerShell, mas seu prompt será alterado para Bash, com uma aparência semelhante a: **<user>@<CPU-name>:~$**. Insira o comando `pwd` para confirmar que o caminho do diretório agora é algo como **/home/<username>**. Insira o comando: `explorer.exe .` para abrir o diretório no Explorador de Arquivos do Windows File (certifique-se de incluir o ponto, que indica para abrir o caminho do diretório atual). Depois de aberto, você poderá confirmar se o caminho do arquivo é semelhante a: **\\wsl.localhost\Ubuntu\home\<username>**.

![Captura de tela do terminal do PowerShell com o comando wsl ~ inserido mostrando o caminho.](//images/wsl-home-command.png)

7. Saia da linha de comando do Bash de volta para o PowerShell usando: `exit`. Use o comando `pwd` novamente para ver o caminho em que você está agora. Deverá ser algo como **C:\Users\<username>\...**. Assim, você poderá ver que alternou entre o sistema de arquivos do Windows (unidade C:\) e o sistema de arquivos do Linux (unidade de rede \\wsl.localhost\<distro name>). Vamos tentar abrir o diretório atual do sistema de arquivos do Windows no Bash usando o comando: wsl sem o ~ (que indica abrir o Bash no diretório inicial do Linux). Você verá que o caminho do diretório agora é algo como **/mnt/c/Users/<username>/...**, pois o Bash está apontando para o caminho do sistema de arquivos do Windows na unidade C montada. O diretório da unidade C está montado porque agora você está exibindo-o de dentro do sistema de arquivos do Linux.

Para ver a lista completa de comandos, execute `wsl --help`.

## Resumo

Você instalou a distribuição padrão do Ubuntu do Linux da Microsoft Store. Você também aprendeu como instalar distribuições adicionais, usando o Ubuntu para uma coisa e o Kali para outra, com prompts de comando personalizados sendo executados lado a lado no Terminal do Windows.

Você aprendeu como listar distribuições disponíveis na loja, que pode importar distribuições que não estão na loja ou até mesmo criar sua própria distribuição personalizada.

Você aprendeu sobre diferentes ambientes em que o WSL pode ser usado, como o Windows Server ou a criação de uma imagem para distribuir em sua empresa ou organização.

Você testou alguns comandos básicos, misturando comandos Bash e PowerShell.

Você aprendeu um pouco sobre como trabalhar entre os sistemas de arquivos do Windows e do Linux, bem como a aparência de um ambiente de desenvolvedor e fluxo de trabalho WSL padrão.

Embora não tenhamos nos aprofundado, agora você deve estar confiante de que o WSL permitirá usar as ferramentas de linha de comando preferidas e os aplicativos de GUI (Interface Gráfica do Usuário), sejam eles executados no Windows ou no Linux.

Por fim, você aprendeu que há alguns ótimos recursos que abordam mais detalhadamente esses tópicos disponíveis para atender às suas necessidades e interesses. Nós relacionamos alguns deles abaixo.

## Referências adicionais
[Documentação do WSL](https://learn.microsoft.com/pt-br/windows/wsl)
[Ambiente empresarial: configure o WSL para sua empresa](https://learn.microsoft.com/pt-br/windows/wsl/enterprise)
[Documentação do Terminal do Windows](https://learn.microsoft.com/pt-br/windows/terminal/)

[Navegar para: WSL2 - Instalação sem usar Docker Desktop](../wsl-without-dd/introduction.md)
