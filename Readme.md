# WSL2 Ubuntu para Python e Node

Este processo é pensado em desenvolvedores que tem interesse de utilizar os recursos do Linux no Windows para explorar o melhor dos dois mundos. No final você poderá programar no Linux pelo VS Code do Windows de forma transparente, leve e super funcional.  
![VS Code Remote WSL](https://code.visualstudio.com/assets/docs/remote/wsl/architecture-wsl.png)  

Além de ficar com um terminal bonitão e com recursos de auto-completar, este processo também instala ambientes virtuais para Node, Yarn e Python, permitindo alterar versões facilmente, conforme a necessidade dos projetos, sem ter conflitos. Para isto é utilizado o [ASDF](https://asdf-vm.com/guide/getting-started.html#_4-install-a-plugin). Clique no link para conhecer mais mais plugins além do Node, Yarn e Python. Para conhecer comandos básicos vá para a sessão [ASDF](#asdf).  
No caso do Python também é instalado o [Poetry](https://python-poetry.org/docs/basic-usage/) para gerenciar bibliotecas PIP de forma similar ao que o Node faz.  

## Prerequisitos
![Windows 10](https://flat.badgen.net/badge/icon/windows10?icon=windows&label)  
Você deve estar executando o Windows 10 versão 2004 e superior (Build 19041 e superior) ou o Windows 11.

## Instalação do WSL2 Ubuntu
![WSL2 Ubuntu](https://flat.badgen.net/badge/WSL2/Ubuntu/orange)  

Abra o Powershell em modo administrador e insira o comando:  
```Powershell
wsl --install
```

Após finalizar, abra WSL pesquisando no menu iniciar.  
Conclua a instalação criando um usuário e senha. Após isso feche a janela do WSL.  

## Windows Terminal
- Baixe e instale essas 4 fontes no Windows para os recursos do Ubuntu aparecerem corretamente:  
    - [MesloLGS NF Regular.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf)  
    - [MesloLGS NF Bold.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold.ttf)  
    - [MesloLGS NF Italic.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf)  
    - [MesloLGS NF Bold Italic.ttf](https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf)  

- Instale e abra o Windows Terminal usando a Microsoft Store.  
    - Clique na "**seta pra baixo**", ao lado do "**+**"  
    - Vá em **Settings**  
    - No menu a esquerda selecione **Ubuntu > Appearance**  
    - Troque a **Font Face** para **MesloLGS NF**  
    - Salve  

## Configuração Básica do Ubuntu
Execute o comando a seguir no Windows Terminal.  
*Use a senha criada para o Ubuntu caso necessário.  
**Os comandos a seguir foram criados por mim e estão no meu gist. Para verificar cada linha do que é executado, acesse: https://gist.githubusercontent.com/alexandremendoncaalvaro

```Bash
/bin/bash -c "$(curl -fsSL https://gist.githubusercontent.com/alexandremendoncaalvaro/b468a2e7410403b2506608ff12325ece/raw/5bcaae34f93643bc0359141d927810f747f44b6e/config-ubuntu-py-pt1.sh)"
```
Feche o terminal e abra novamente.  
*Nessa etapa a aparencia do terminal é configurada através de um Wizzard com vários passos. Deixe conforme suas preferências.  
<img src="https://raw.githubusercontent.com/romkatv/powerlevel10k-media/master/configuration-wizard.gif" alt="Powerlevel10k" width="400"/>  


Execute o próximo comando:  
*Use a senha criada para o Ubuntu caso necessário.  
```Bash
/bin/bash -c "$(curl -fsSL https://gist.githubusercontent.com/alexandremendoncaalvaro/6eb05914ed4183718a72edcbfd41c053/raw/b81ae70f1a8e305e702a7f8b6b86c948ce5e240e/config-ubuntu-py-pt2.sh)"
```

## VSCode
Instale as extensão **Visual Studio Code Remote - WSL** no VS Code.  
Nas configurações do VS Code inclua a linha a seguir para alterar a fonte do terminal integrado:  
```Bash
"terminal.integrated.fontFamily": "MesloLGS NF",
```

Existem várias formas de acessar seus projetos no WLS, a minha favorita é abrir o WSL no Windows Terminal, navegar até a pasta do meu projeto e digitar:  
```Bash
code .
```

O VS Code do seu Windows vai abrir acessando seu projeto remotamente (via SSH) no WLS. Parece mágica e funciona incrivelmente bem!

## ASDF

Alguns exemplos de uso do ASDF  

Instalar a ultima versão do node:  
```Bash
asdf install nodejs latest
```

Selecionar a ultima versão do node como global para todos os projetos:  
```Bash
asdf global nodejs latest
```

Listar todas as versões de plugins instalados:  
```Bash
asdf list
```

## Poetry
### Guia Rápido
https://www.youtube.com/embed/BXlhJO3p3s4

### Porque usar o Poetry para Python?
https://www.youtube.com/embed/_XszPRFHQQ4
