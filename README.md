# projetoflaskwsl
API que apresentará o arquivo index.html na porta :3000

Preparação no Windows:
    - instalar aplicativos
        wsl2
        ubuntu
            requisitos: 
                hipervy ativado (Painel de controle > Programas > Ativar desativar recursos windows e ative a check box “Subsistema do Windows para linux” ) - Obs: também no BIOS
                Ubuntu pode ser adquirido em MS Store

Preparação no Ubuntu: (lembrar que é um sistema operacional completo que apenas vai acessar os arquivos nas unidades do windows) - Obs: /mnt/c/<diretorio> = sempre.
    - instalar 
        git (git config --global ...)
        python 
        docker
        ...
        Obs: $sudo apt update $$ sudo apt upgrade -y 

Criação do repositório:
    - no github.com criar o novo repositório com o "README.md" e a licença GLP3
    - no diretório raiz de trabalho "c:/xprojetos" executar o git clone
        $git clone https://github.com/lucianopollbr/projetoflaskwsl.git 
        $git checkout (deve ser a branch "main")
    - acrescentar os arquivos necessários ao desenvolvimento:
        $touch appsite.py
        $touch Dockerfile 
        $cp -r origem/site /mnt/c/xprojetos/projetoflaskwsl
    - fazer stage, commit e push
        $git add .
        $git commit -m "texto explicativo"
        $git push origin main 
        

