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
        $git origin main https://github.com/lucianopollbr/projetoflaskwsl.git
        $git push origin main 
        

###################################################################################

Ativação do Ambiente Virtual de Desenvolvimento Python:

passo a passo para criar um ambiente virtual Python no diretório `c:/xprojetos/projetoflaskwsl` usando WSL2 com Ubuntu pelo terminal no VS Code.

### Passo a Passo:

1. **Abrir o VS Code e o Terminal WSL2:**
   - Abra o VS Code.
   - Pressione `Ctrl + Shift + P` para abrir a paleta de comandos.
   - Digite `WSL: New Window` e selecione para abrir uma nova janela do VS Code conectada ao WSL2.

2. **Navegar até o Diretório do Projeto:**
   - No terminal do VS Code, navegue até o diretório do seu projeto com o comando:
     ```bash
     cd /mnt/c/xprojetos/projetoflaskwsl
     ```

3. **Criar o Ambiente Virtual:**
   - No terminal, crie o ambiente virtual com o comando:
     ```bash
     python3 -m venv venv
     ```
   - Isso criará uma pasta chamada `venv` dentro do diretório do seu projeto.

4. **Ativar o Ambiente Virtual:**
   - Ative o ambiente virtual com o comando:
     ```bash
     source venv/bin/activate
     ```
   - Você verá o nome do ambiente virtual (`venv`) aparecer no início da linha de comando, indicando que ele está ativo.

5. **Instalar Dependências:**
   - Agora, você pode instalar as dependências necessárias para o seu projeto. Por exemplo, para instalar Flask, use:
     ```bash
     pip install flask
     ```

6. **Configurar o VS Code para Usar o Ambiente Virtual:**
   - Pressione `Ctrl + Shift + P` novamente e digite `Python: Select Interpreter`.
   - Selecione o interpretador Python dentro do seu ambiente virtual (`venv`).

### Exemplo Completo:

Aqui está um resumo dos comandos que você usará:

```bash
cd /mnt/c/xprojetos/projetoflaskwsl
python3 -m venv venv
source venv/bin/activate
pip install flask
```

### Desativar o Ambiente Virtual:

Quando terminar de trabalhar, você pode desativar o ambiente virtual com o comando:

```bash
deactivate
```

###########################################################################

Acesso por SSH: 


1. **Gerar a Chave SSH (se ainda não tiver feito):**
   ```bash
   ssh-keygen -t rsa -b 4096 -C "seu_email@example.com"
   ```
   Siga as instruções e salve a chave em um local seguro (geralmente em `~/.ssh/id_rsa`).

2. **Copiar a Chave SSH para o Clipboard:**
   - Use o comando `clip.exe` para copiar a chave pública:
     ```bash
     cat ~/.ssh/id_rsa.pub | clip.exe
     ```
   - Isso copiará a chave pública para o clipboard do Windows.

3. **Adicionar a Chave SSH ao GitHub:**
   - Vá para [Configurações de SSH e GPG no GitHub](https://github.com/settings/keys) e clique em **New SSH key**.
   - Cole a chave pública copiada e salve.

4. **Configurar o Git para Usar SSH:**
   - No terminal, altere a URL remota para usar SSH:
     ```bash
     git remote set-url origin git@github.com:<seu_usuario>/<seu_repositorio>.git
     ```

5. **Fazer o Push:**
   - Agora, você pode fazer o push normalmente:
     ```bash
     git push origin main
     ```

### Resumo dos Comandos:

```bash
ssh-keygen -t rsa -b 4096 -C "seu_email@example.com"
cat ~/.ssh/id_rsa.pub | clip.exe
git remote set-url origin git@github.com:<seu_usuario>/<seu_repositorio>.git
git push origin main
```

###############################################################################
