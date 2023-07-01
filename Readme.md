# WSL2 Ubuntu para Python

Este processo é pensado em desenvolvedores que tem interesse de utilizar os recursos do Linux no Windows para explorar o melhor dos dois mundos. No final você poderá programar no WSL2 (Linux) remotamente pelo VS Code do Windows de forma transparente, leve e super funcional.  

<img src="https://code.visualstudio.com/assets/docs/remote/wsl-tutorial/remote-wsl-extension.png" alt="WSL Extension" width="600"/>  


Este processo também instala ambientes virtuais para Python, permitindo alterar versões facilmente, conforme a necessidade dos projetos, sem ter conflitos. Para isto é utilizado o [pyenv](https://github.com/pyenv/pyenv).  
Também é instalado o [poetry](https://python-poetry.org/docs/basic-usage/) para gerenciar bibliotecas PIP de forma similar ao que o Node faz.  

Para conhecer comandos básicos vá para as sessões [pyenv](#pyenv) e [poetry](#poetry) respectivamente.  

Opcionalmente você também pode ficar com um terminal bonitão e com recursos de auto-completar. Veja em [Windows Terminal + ZSH](#windows-terminal-zsh).

## Prerequisitos
![Windows 10](https://flat.badgen.net/badge/icon/windows10?icon=windows&label)  
Você deve estar executando o Windows 10 versão 2004 e superior (Build 19041 e superior) ou o Windows 11.

# Instalação do WSL2 Ubuntu
![WSL2 Ubuntu](https://flat.badgen.net/badge/WSL2/Ubuntu/orange)  

Abra o Powershell em modo administrador e insira o comando:  
```Powershell
wsl --install
```

Após finalizar, abra WSL pesquisando no menu iniciar.  
Conclua a instalação criando um usuário e senha. Após isso feche a janela do WSL.  

# Bash simplão ou Terminal Windows + Plugins?
Você pode seguir de duas formas agora em relação ao terminal.  

- [Bash Simplão](#bash-simpl-o): Instala o básico* pra funcionar no Bash.
- [Windows Terminal + ZSH](#windows-terminal-zsh): Instala o básico* pra funcionar no ZSH + o ZSH com plugins de autocomplete e aparência bonitona e informativa de terminal.  
Exemplo de aparência (tem vários temas):  
<img src="https://blog.rocketseat.com.br/content/images/2019/05/Screen-Shot-2019-05-02-at-10.08.19.png" alt="Powerlevel10k" width="600"/>  

> *básico: Integração vscode, pyenv e poetry

# Bash Simplão
Siga as etapas a seguir para instalar apenas o básico pra funcionar o pyenv e poetry no Bash.  

Execute o comando de terminal a seguir no WSL.  
```Bash
/bin/bash -c "$(curl -fsSL https://gist.githubusercontent.com/alexandremendoncaalvaro/2b9a6cc9a3a5b1ee2b0980502efc50ad/raw/729b5bd19c6eaff19aac20f773e1eefb5b5b841c/config-ubuntu-py-bash.sh)"
```
> *Use a senha criada para o Ubuntu caso necessário.  
**Os comandos a seguir foram criados por mim e estão no meu gist. Para verificar cada linha do que é executado, acesse: https://gist.githubusercontent.com/alexandremendoncaalvaro

Pronto!
Basta configurar o [VSCode](#vscode) e está pronto para usar os recursos do pyenv e poetry.

# Windows Terminal + ZSH
Exemplo de aparência (tem vários temas):  
<img src="https://blog.rocketseat.com.br/content/images/2019/05/Screen-Shot-2019-05-02-at-10.08.19.png" alt="Powerlevel10k" width="600"/>  
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
```Bash
/bin/bash -c "$(curl -fsSL https://gist.githubusercontent.com/alexandremendoncaalvaro/b468a2e7410403b2506608ff12325ece/raw/5bcaae34f93643bc0359141d927810f747f44b6e/config-ubuntu-py-pt1.sh)"
```
> *Use a senha criada para o Ubuntu caso necessário.  
**Os comandos a seguir foram criados por mim e estão no meu gist. Para verificar cada linha do que é executado, acesse: https://gist.githubusercontent.com/alexandremendoncaalvaro

Feche o terminal e abra novamente.  

Nessa etapa a aparencia do terminal é configurada através de um Wizzard com vários passos. Deixe conforme suas preferências.  
<img src="https://raw.githubusercontent.com/romkatv/powerlevel10k-media/master/configuration-wizard.gif" alt="Powerlevel10k" width="600"/>  


Execute o próximo comando:  
```Bash
/bin/bash -c "$(curl -fsSL https://gist.githubusercontent.com/alexandremendoncaalvaro/6eb05914ed4183718a72edcbfd41c053/raw/b81ae70f1a8e305e702a7f8b6b86c948ce5e240e/config-ubuntu-py-pt2.sh)"
```
> *Use a senha criada para o Ubuntu caso necessário.  

# VSCode
Instale as extensão **Visual Studio Code Remote - WSL** no VS Code.  

Se optou pela versão com temas, lembre de ir nas configurações do VS Code e incluir a linha a seguir para alterar a fonte do terminal integrado:  
```Bash
"terminal.integrated.fontFamily": "MesloLGS NF",
```

Existem várias formas de acessar seus projetos no WLS, a minha favorita é abrir o WSL no Windows Terminal, navegar até a pasta do meu projeto e digitar:  
```Bash
code .
```

O VS Code do seu Windows vai abrir acessando seu projeto remotamente (via SSH) no WLS. Parece mágica e funciona incrivelmente bem!

<img src="https://code.visualstudio.com/assets/docs/remote/wsl/architecture-wsl.png" alt="VS Code Remote WSL" width="600"/>  


# pyenv

Alguns exemplos de uso do pyenv  

Listar as versões do python que já temos instalada no sistema:  
```Bash
pyenv versions
```

Listar as versões do python disponíveis para instalação:  
```Bash
pyenv install -l
```

Instalar a versão do python escolhida:  
```Bash
pyenv install 3.10.14
```

Selecionar a versão do python que instalamos como global para todos os projetos:  
```Bash
pyenv global 3.10.14
```

### Mais informações e comandos
https://github.com/pyenv/pyenv#usage


# poetry
### Guia Rápido
https://www.youtube.com/embed/BXlhJO3p3s4

### Porque usar o Poetry para Python?
https://www.youtube.com/embed/_XszPRFHQQ4
