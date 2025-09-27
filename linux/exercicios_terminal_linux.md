# Exercícios de Terminal Linux

## 📋 Índice
1. [Abrindo o Terminal](#1-abrindo-o-terminal)
2. [Verificação de IP e Interfaces de Rede](#2-verificação-de-ip-e-interfaces-de-rede)
3. [Navegação e Manipulação de Arquivos](#3-navegação-e-manipulação-de-arquivos)
4. [Comandos Básicos de Sistema](#4-comandos-básicos-de-sistema)

---

## 1. Abrindo o Terminal

### 🎯 Objetivo
Aprender a abrir e usar o terminal no Ubuntu.

### 📝 Exercícios

#### Exercício 1.1: Abrindo o Terminal
1. **Método 1 - Atalho de Teclado:**
   - Pressione `Ctrl + Alt + T` para abrir o terminal rapidamente

2. **Método 2 - Menu de Aplicativos:**
   - Clique no botão "Mostrar aplicativos" (ícone de grade) no canto inferior esquerdo
   - Procure por "Terminal" ou digite "terminal" na busca
   - Clique no ícone do Terminal para abrir

3. **Método 3 - Menu de Atividades:**
   - Pressione a tecla `Super` (Windows) para abrir o menu de atividades
   - Digite "terminal" e pressione Enter

### ✅ Verificação
- O terminal deve abrir mostrando uma linha de comando similar a:
  ```
  usuario@nome-do-computador:~$ 
  ```

---

## 2. Verificação de IP e Interfaces de Rede

### 🎯 Objetivo
Aprender a verificar endereços IP e entender as interfaces de rede do sistema.

### 📝 Exercícios

#### Exercício 2.1: Comando ifconfig
```bash
ifconfig
```
**O que fazer:**
1. Execute o comando `ifconfig` no terminal
2. Observe as interfaces de rede listadas
3. Identifique os endereços IP de cada interface

#### Exercício 2.2: Comando ip addr
```bash
ip addr show
```
**O que fazer:**
1. Execute o comando `ip addr show` (ou apenas `ip addr`)
2. Compare os resultados com o comando anterior
3. Identifique as diferenças na apresentação das informações

### 📚 Explicação dos IPs e Interfaces

#### O que são Endereços IP?
- **IP (Internet Protocol):** É um endereço numérico único que identifica dispositivos em uma rede
- **Formato:** Quatro números separados por pontos (ex: 192.168.1.100)
- **Função:** Permite que dispositivos se comuniquem entre si na rede

#### Tipos de IP que você pode encontrar:

1. **IP Loopback (127.0.0.1):**
   - Interface: `lo` (loopback)
   - Função: Comunicação interna do próprio computador
   - Sempre presente em sistemas Linux

2. **IP Ethernet/Wi-Fi:**
   - Interface: `eth0`, `enp0s3`, `wlan0`, etc.
   - Função: Conexão com rede local ou internet
   - Pode ser obtido via DHCP ou configurado manualmente

3. **IP Docker/Containers:**
   - Interface: `docker0`
   - Função: Comunicação entre containers Docker

#### Interfaces de Rede:
- **lo:** Interface de loopback (sempre 127.0.0.1)
- **eth0/enp0s3:** Interface Ethernet (cabo)
- **wlan0:** Interface Wi-Fi (sem fio)
- **docker0:** Interface Docker (se Docker estiver instalado)

### ✅ Verificação
- Execute ambos os comandos e identifique:
  - Pelo menos 2 interfaces de rede
  - O IP loopback (127.0.0.1)
  - Seu IP na rede local (geralmente 192.168.x.x ou 10.x.x.x)

---

## 3. Navegação e Manipulação de Arquivos

### 🎯 Objetivo
Aprender comandos básicos para navegar no sistema de arquivos e manipular arquivos e diretórios.

### 📝 Exercícios

#### Exercício 3.1: Navegação Básica
```bash
# Verificar diretório atual
pwd

# Listar conteúdo do diretório atual
ls

# Listar com detalhes
ls -l

# Listar arquivos ocultos também
ls -la
```

#### Exercício 3.2: Criação de Pasta
```bash
# Criar uma pasta chamada 'exercicios'
mkdir exercicios

# Criar múltiplas pastas
mkdir pasta1 pasta2 pasta3

# Criar estrutura de pastas aninhadas
mkdir -p projeto/src projeto/docs projeto/tests
```

#### Exercício 3.3: Navegação entre Diretórios
```bash
# Entrar na pasta exercicios
cd exercicios

# Voltar ao diretório anterior
cd ..

# Voltar ao diretório home do usuário
cd ~
# ou simplesmente
cd

# Ir para um diretório específico
cd /home/usuario/Documentos
```

#### Exercício 3.4: Criação de Arquivos
```bash
# Criar um arquivo vazio
touch arquivo.txt

# Criar arquivo com conteúdo usando echo
echo "Este é meu primeiro arquivo" > arquivo1.txt

# Criar arquivo com múltiplas linhas
cat > arquivo2.txt << EOF
Linha 1: Primeira linha do arquivo
Linha 2: Segunda linha do arquivo
Linha 3: Terceira linha do arquivo
EOF
```

#### Exercício 3.5: Cópia de Arquivos
```bash
# Copiar arquivo para outro local
cp arquivo.txt arquivo_copia.txt

# Copiar arquivo para outra pasta
cp arquivo.txt exercicios/

# Copiar pasta inteira (recursivo)
cp -r exercicios exercicios_backup
```

#### Exercício 3.6: Movimentação e Renomeação
```bash
# Mover arquivo (também serve para renomear)
mv arquivo.txt novo_nome.txt

# Mover arquivo para outra pasta
mv arquivo1.txt exercicios/

# Renomear pasta
mv exercicios meus_exercicios
```

#### Exercício 3.7: Remoção
```bash
# Remover arquivo
rm arquivo.txt

# Remover pasta vazia
rmdir pasta_vazia

# Remover pasta com conteúdo (cuidado!)
rm -r pasta_com_conteudo

# Remover com confirmação
rm -i arquivo.txt
```

#### Exercício 3.8: Listagem e Visualização
```bash
# Listar arquivos com detalhes
ls -l

# Listar com tamanhos legíveis
ls -lh

# Listar arquivos por data de modificação
ls -lt

# Mostrar apenas diretórios
ls -d */

# Contar arquivos
ls | wc -l
```

### ✅ Verificação
Execute todos os exercícios em sequência e verifique:
1. ✅ Conseguiu criar a pasta 'exercicios'
2. ✅ Conseguiu criar arquivos dentro dela
3. ✅ Conseguiu fazer cópias dos arquivos
4. ✅ Conseguiu navegar entre diretórios
5. ✅ Conseguiu listar o conteúdo dos diretórios
6. ✅ Conseguiu voltar ao diretório home do usuário

---

## 4. Comandos Básicos de Sistema

### 🎯 Objetivo
Aprender comandos úteis para verificar informações do sistema.

### 📝 Exercícios

#### Exercício 4.1: Informações do Sistema
```bash
# Ver informações do sistema
uname -a

# Ver versão do sistema
cat /etc/os-release

# Ver espaço em disco
df -h

# Ver uso de memória
free -h
```

#### Exercício 4.2: Informações do Usuário
```bash
# Ver usuário atual
whoami

# Ver informações do usuário
id

# Ver histórico de comandos
history

# Ver variáveis de ambiente
env
```

#### Exercício 4.3: Busca de Arquivos
```bash
# Buscar arquivo por nome
find ~ -name "*.txt"

# Buscar arquivo por conteúdo
grep -r "texto" ~/

# Localizar comando
which ls
```

### ✅ Verificação Final
1. ✅ Conseguiu abrir o terminal
2. ✅ Executou comandos de rede (ifconfig/ip addr)
3. ✅ Entendeu os conceitos de IP e interfaces
4. ✅ Criou pastas e arquivos
5. ✅ Fez cópias e removeu arquivos
6. ✅ Navegou entre diretórios
7. ✅ Listou conteúdo de diretórios
8. ✅ Voltou ao diretório home

---

## 🎉 Parabéns!

Você completou os exercícios básicos de terminal Linux! 

### 📚 Próximos Passos Sugeridos:
- Aprender sobre permissões de arquivos (`chmod`, `chown`)
- Explorar redirecionamento e pipes (`>`, `>>`, `|`)
- Estudar editores de texto no terminal (`nano`, `vim`)
- Aprender sobre processos (`ps`, `top`, `kill`)
- Explorar compressão de arquivos (`tar`, `zip`, `gzip`)

### 💡 Dicas Importantes:
- Sempre use `Tab` para autocompletar comandos e nomes de arquivos
- Use `Ctrl + C` para interromper comandos em execução
- Use `Ctrl + L` ou `clear` para limpar a tela
- Use `man comando` para ver a documentação de qualquer comando
- Use `history` para ver comandos executados anteriormente

---

## 5. Instalação do Git e Clonagem de Repositório

### 🎯 Objetivo
Aprender a instalar o Git e clonar um repositório do GitHub.

### 📝 Exercícios

#### Exercício 5.1: Instalação do Git no Ubuntu
```bash
# Atualizar lista de pacotes
sudo apt update

# Instalar o Git
sudo apt install git

# Verificar se o Git foi instalado corretamente
git --version
```

#### Exercício 5.2: Configuração Inicial do Git
```bash
# Configurar nome de usuário (substitua pelo seu nome)
git config --global user.name "Seu Nome"

# Configurar email (substitua pelo seu email)
git config --global user.email "seu.email@exemplo.com"

# Verificar configurações
git config --list
```

#### Exercício 5.3: Clonagem do Repositório
```bash
# Navegar para o diretório onde quer clonar (exemplo: Documentos)
cd ~/Documentos

# Clonar o repositório informatica
git clone https://github.com/mfrlinux/informatica.git

# Entrar na pasta clonada
cd informatica

# Listar conteúdo do repositório
ls -la

# Ver informações do repositório
git remote -v
```

#### Exercício 5.4: Navegação no Repositório Clonado
```bash
# Ver estrutura de pastas
tree
# ou se não tiver tree instalado:
find . -type d

# Entrar na pasta informatica_basica
cd informatica_basica

# Listar conteúdo
ls -la

# Voltar ao diretório anterior
cd ..

# Ver histórico de commits
git log --oneline
```

### 📚 Explicação sobre Git e GitHub

#### O que é Git?
- **Git:** Sistema de controle de versão distribuído
- **Função:** Rastrear mudanças em arquivos ao longo do tempo
- **Benefícios:** Colaboração, backup, histórico de alterações

#### O que é GitHub?
- **GitHub:** Plataforma de hospedagem de código
- **Função:** Armazenar repositórios Git na nuvem
- **Benefícios:** Colaboração online, backup na nuvem, interface web

#### Comandos Git Básicos:
```bash
# Clonar repositório
git clone <url-do-repositorio>

# Ver status dos arquivos
git status

# Adicionar arquivos ao stage
git add .

# Fazer commit das mudanças
git commit -m "Mensagem descritiva"

# Enviar mudanças para o GitHub
git push

# Baixar mudanças do GitHub
git pull
```

### ✅ Verificação
1. ✅ Git foi instalado com sucesso (`git --version`)
2. ✅ Configurações foram definidas
3. ✅ Repositório foi clonado com sucesso
4. ✅ Conseguiu navegar na estrutura de pastas
5. ✅ Visualizou o conteúdo do repositório

### 🔧 Comandos Úteis Adicionais
```bash
# Ver diferenças entre arquivos
git diff

# Ver histórico detalhado
git log --graph --oneline --all

# Ver informações do repositório remoto
git remote show origin

# Verificar branch atual
git branch

# Listar todas as branches
git branch -a
```

### 💡 Dicas Importantes sobre Git:
- Sempre faça `git pull` antes de começar a trabalhar
- Use mensagens de commit descritivas
- Faça commits pequenos e frequentes
- Use `git status` para ver o que mudou
- Nunca commite arquivos sensíveis (senhas, chaves)

---

## 🎉 Parabéns!

Você completou os exercícios básicos de terminal Linux e aprendeu sobre Git! 

### 📚 Próximos Passos Sugeridos:
- Aprender sobre permissões de arquivos (`chmod`, `chown`)
- Explorar redirecionamento e pipes (`>`, `>>`, `|`)
- Estudar editores de texto no terminal (`nano`, `vim`)
- Aprender sobre processos (`ps`, `top`, `kill`)
- Explorar compressão de arquivos (`tar`, `zip`, `gzip`)
- Aprofundar conhecimentos em Git (branches, merge, rebase)

### 💡 Dicas Importantes:
- Sempre use `Tab` para autocompletar comandos e nomes de arquivos
- Use `Ctrl + C` para interromper comandos em execução
- Use `Ctrl + L` ou `clear` para limpar a tela
- Use `man comando` para ver a documentação de qualquer comando
- Use `history` para ver comandos executados anteriormente
- Configure o Git com suas informações pessoais antes de usar

**Boa prática no terminal! 🚀**

---

### 📖 Referências Úteis:
- [Repositório do curso: https://github.com/mfrlinux/informatica](https://github.com/mfrlinux/informatica)
- [Documentação oficial do Git](https://git-scm.com/doc)
- [GitHub Docs](https://docs.github.com/)
