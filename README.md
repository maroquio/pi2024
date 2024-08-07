# Projeto Base Alterado

# Vídeo de Apoio

O link a seguir apresenta um vídeo de apoio que demonstra o seguimento dessas instruções na prática. Pode ser que algumas coisas mais específicas estejam somente neste documento.

[Vídeo de Apoio](https://www.youtube.com/watch?v=R8DTirL-mRc)

# Criando um Repositório no GitHub

Esse passo deve ser feito somente uma vez. Se seu projeto já tem repositório, pode ir ao passo seguinte. Depois de se cadastrar no GitHub, crie um novo repositório **público** com o nome do projeto, sem espações e em minúsculas. Cada grupo deve ter somente um repositório no GitHub.

# Adicionando Colaboradores

1. Abra o repositório criado para o projeto no GitHub;
2. Acesse o menu *Settings* na parte superior do repositório;
3. Acesse o menu *Collaborators*, na parte esquerda superior;
4. Na página que se abre, clique no botão verde *Add People*;
5. No modal que se abre, digite o e-mail ou nome de usuário GitHub do colaborador que deseja adicionar;
6. Se estiver correto, logo abaixo do campo será mostrada uma caixa com o colaborador, na qual você deve clicar;
7. No passo seguinte, basta clicar em *Add [Usuario Tal] to this repository*.

# Instalação do `Git for Windows`

Para usar os comandos Git no VSCode, a primeira coisa a ser feita é a instalação do Git for Windows (ou para o sistema operacional alvo). Para isso, acesse o seguinte endereço:

[Download do Git for Windows](https://git-scm.com/download/win)

[Download do Git for Linux](https://git-scm.com/download/linux)

[Download do Git for MacOS](https://git-scm.com/download/macos)

Durante os passos da instalação, escolha o próprio VSCode como editor padrão em vez do *vim*;

Em um próximo passo da instalação, escolha a opção para fazer *override* com *main*;

Depois siga os passos padrões até o final da instalação.

# Baixando e Alterando o Projeto Base

Esse passo deve ser feito apenas uma vez por projeto. 

Baixe o projeto base no grupo do Telegram, descompacte para uma pasta e abra a pasta descompatada no VSCode. Certifique-se de que o VSCode está aberto na raiz do projeto base. Em seguida, faça o seguinte:

1. Abra o arquivo `docker-compose.yml`;
2. Em "ports", no lugar de 8200, adicione a porta designada para o seu projeto;
3. No nome do contêiner, adicione no seguinte padrao: `projeto.cachoeiro.es`, onde "projeto" deve ser o nome do seu projeto em minúsculas e sem caracteres especiais ou espaços.

As portas de cada projeto são as seguintes:

1. Jeito Rural: 8201
2. Vitalis: 8202
3. ReclamES: 8203
4. CarboniO: 8204
5. VoluntariÊ: 8205
6. Fitness Life: 8206
7. Ruraliza: 8207
8. Workin: 8208
9. Tupã: 8209

# Configuração do VSCode para o Git

Esse processo deve ser executado na primeira vez em que for usar sua conta GitHub em um novo computador. Se você já fez isso no computador que está usando, pode pular esta etapa.

1. Abra o terminal do vscode;
2. Digite o comando `ssh-keygen -t ed25519 -C "usuariogit@email.com"`;
3. Pressione *Enter* para aceitar o local padrão para salvar a chave;
4. Não precisa de senha, então pressione *Enter* duas vezes;
5. Digite o comando `cat C:/PASTADOUSUARIO/.ssh/id_ed25519.pub` para exibir a chave pública;
6. Copie a chave pública e cole no GitHub de seu usuário em *Settings* > *SSH and GPG keys* > *New SSH key*;
7. Digite um título para a chave (ex.: Computador Pessoal) e cole a chave no campo *Key*;
8. Clique em *Add SSH key*.

# Para Inicializar a Pasta do Projeto Base e Configurar para Commits

Esse passo deve ser executado **somente na primeira vez** que você for subir o projeto para o GitHub ou sempre que clonar o projeto em um outro computador. No terminal do VSCode, aberto na pasta do projeto base, digite o seguinte:

```bash
    git init
    git branch -M main
    git remote add origin https://github.com/maroquio/pi2024.git
```

No lugar de `https://github.com/maroquio/pi2024.git`, coloque o endereço do repositório do seu projeto.

Agora, é necessário fazer o envio da primeira versão do projeto para o GitHub, executando os seguintes comandos:

```bash
    git add .
    git commit -m "mensagem informativa sobre que alteracoes esse commit possui"
    git push -u origin main
```

Se o VSCode pedir para logar na conta GitHub pelo navegador, faça isso. Depois que o projeto estiver no repositório do GitHub, ele pode ser clonado por qualquer colaborador para ser modificado.

# Para Clonar o Projeto em um Computador Diferente

Esse passo deve ser executado para clonar o projeto em um computador qualquer (de sua casa, por exemplo), para que cada colaborador do repositório possa trabalhar no projeto de forma integrada aos demais.

1. Abra o VSCode em uma pasta de trabalho vazia, onde pretende deixar o projeto;
2. Abra o terminal do VSCode e certifique-se de que ele está nesta pasta vazia;
3. Execute o seguinte comando:

```bash
    git clone https://github.com/maroquio/pi2024.git
```
No lugar de `https://github.com/maroquio/pi2024.git`, coloque o endereço do repositório do seu projeto.

Depois de clonar, feche o VSCode e abra-o novamente **na pasta clonada**, de forma que ela seja a raiz dos arquivos no VSCode. Depois disso, defina o usuário responsável por esse repositório clonado, executando os seguintes comandos:

```bash
    git config user.name "Seu Nome"
    git config user.email "seu.email@exemplo.com"
```

Caso queira definir um nome de usuário globalmente responsável por todos os repositórios do computador em que está trabalhando, use a opção `--global`:

```bash
    git config --global user.name "Seu Nome"
    git config --global user.email "seu.email@exemplo.com"
```

Por segurança, depois de alterar o usuário padrão, confirme isso no repositório digitando o seguinte:

```bash
git commit --amend --reset-author
```

Esse comando vai abrir um arquivo texto no editor padrão do Git local. Basta fechar esse arquivo para prosseguir. Depois disso, você já pode usar seu repositório clonado de forma colaborativa.

# Realizar Commit Após Alterações no Projeto

Esse passo deve ser feito após a inicialização de um projeto ou depois de clonar o projeto em outro computador e modificá-lo. Depois de realizar alterações quaisquer no projeto, execute os seguintes comandos para enviar as alterações para o GitHub:

```bash
    git add .
    git commit -m "mensagem informativa sobre que alteracoes esse commit possui"
    git push -u origin main
```

# Obtendo as Atualizações Feitas por Outros Colaboradores

**Sempre** que abrir o VSCode para começar a trabalhar no projeto, obtenha as atualizações dos outros colaboradores executando o seguinte commando:

```bash
    git pull
```

Somente depois disso é que você pode começar a realizar alterações no projeto. E lembre-se de não alterar arquivos que esteja sendo alterado por outro colaborador. Essa sincronização é importante para evitar conflitos e depender de *merges*.

# Criando um Webhook para Notificar o Servidor Web

Esse passo é **necessário** para que o projeto seja publicado adequadamente na web e não pode deixar de ser executado. Segue:

1. Abra o repositório do projeto integrador no GitHub;
2. Acesse o menu *Settings* na parte superior do repositório;
3. Na página que se abre, à esquerda, acesse o menu *Webhooks*;
4. Clique no botão *Add webhook* na parte superior direita;
5. No campo *Payload URL\** digite exatamente o seguinte, incluindo a barra no final:
    https://jenkins.cachoeiro.es/github-webhook/
6. Mantenha as outras opções como estão e clique no botão verde *Add webhook*, no final da página.