# ✅ Checklist de Instalação e Pré-requisitos

## 📋 Visão Geral

Este documento contém todos os pré-requisitos e instruções de instalação necessários para participar do **Bootcamp - Modernizando Aplicações Java com IBM Bob**.

**⏰ Importante:** Complete todas as instalações **antes do início do bootcamp**

## 🎯 Requisitos de Sistema

### Sistema Operacional

- ✅ Windows 10/11 (64-bit)
- ✅ macOS 11+ (Big Sur ou superior)
- ✅ Linux (Ubuntu 20.04+, Fedora 35+, ou similar)

### Hardware Mínimo

- **Processador:** Intel Core i5 ou equivalente
- **RAM:** 8GB (16GB recomendado)
- **Disco:** 50GB de espaço livre
- **Internet:** Conexão estável para download de ferramentas

## 📦 Software Obrigatório

### 1. Java Development Kits (JDKs)

Você precisará de múltiplas versões do Java instaladas:

#### ☕ JDK 8

**Para:** Laboratório 1 - Aplicação legada

**Download:**

- Oracle JDK 8: https://www.oracle.com/java/technologies/javase/javase8-archive-downloads.html
- OpenJDK 8: https://adoptium.net/temurin/releases/?version=8

**Instalação Windows:**

```powershell
# Baixar e executar o instalador
# Configurar JAVA_HOME
setx JAVA_HOME "C:\Program Files\Java\jdk1.8.0_xxx"
setx PATH "%PATH%;%JAVA_HOME%\bin"
```

**Instalação macOS:**

```bash
# Usando Homebrew
brew install openjdk@8

# Adicionar ao PATH
echo 'export PATH="/usr/local/opt/openjdk@8/bin:$PATH"' >> ~/.zshrc
```

**Instalação Linux:**

```bash
# Ubuntu/Debian
sudo apt update
sudo apt install openjdk-8-jdk

# Fedora/RHEL
sudo dnf install java-1.8.0-openjdk-devel
```

**Validação:**

```bash
java -version
# Deve mostrar: java version "1.8.0_xxx"
```

- [ ] JDK 8 instalado
- [ ] JAVA_HOME configurado
- [ ] Comando `java -version` funcionando

#### ☕ JDK 11

**Para:** Compatibilidade e testes

**Download:**

- OpenJDK 11: https://adoptium.net/temurin/releases/?version=11

**Instalação similar ao JDK 8**

- [ ] JDK 11 instalado

#### ☕ JDK 17

**Para:** Testes intermediários

**Download:**

- OpenJDK 17: https://adoptium.net/temurin/releases/?version=17

**Instalação similar ao JDK 8**

- [ ] JDK 17 instalado

#### ☕ JDK 21 (LTS)

**Para:** Laboratórios 3 e 4 - Modernização

**Download:**

- OpenJDK 21: https://adoptium.net/temurin/releases/?version=21
- Oracle JDK 21: https://www.oracle.com/java/technologies/downloads/#java21

**Instalação Windows:**

```powershell
# Baixar e executar o instalador
# Configurar JAVA_HOME para JDK 21
setx JAVA_HOME "C:\Program Files\Java\jdk-21"
setx PATH "%PATH%;%JAVA_HOME%\bin"
```

**Instalação macOS:**

```bash
# Usando Homebrew
brew install openjdk@21

# Adicionar ao PATH
echo 'export PATH="/usr/local/opt/openjdk@21/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

**Instalação Linux:**

```bash
# Ubuntu/Debian
sudo apt update
sudo apt install openjdk-21-jdk

# Fedora/RHEL
sudo dnf install java-21-openjdk-devel
```

**Validação:**

```bash
java -version
# Deve mostrar: openjdk version "21.x.x"
```

- [ ] JDK 21 instalado
- [ ] JAVA_HOME configurado para JDK 21
- [ ] Comando `java -version` mostrando versão 21

**💡 Dica:** Use ferramentas como SDKMAN! (Linux/Mac) ou jEnv para gerenciar múltiplas versões:

```bash
# SDKMAN!
curl -s "https://get.sdkman.io" | bash
sdk install java 8.0.xxx-tem
sdk install java 21.0.xxx-tem
sdk use java 21.0.xxx-tem
```

### 2. Apache Maven

**Versão:** 3.8.0 ou superior

**Download:** https://maven.apache.org/download.cgi

**Instalação Windows:**

```powershell
# Baixar e extrair para C:\Program Files\Maven
# Configurar variáveis de ambiente
setx M2_HOME "C:\Program Files\Maven\apache-maven-3.9.x"
setx PATH "%PATH%;%M2_HOME%\bin"
```

**Instalação macOS:**

```bash
brew install maven
```

**Instalação Linux:**

```bash
# Ubuntu/Debian
sudo apt install maven

# Fedora/RHEL
sudo dnf install maven
```

**Validação:**

```bash
mvn -version
# Deve mostrar: Apache Maven 3.8.x ou superior
```

- [ ] Maven instalado
- [ ] M2_HOME configurado
- [ ] Comando `mvn -version` funcionando

### 3. Git

**Versão:** 2.30 ou superior

**Download:** https://git-scm.com/downloads

**Instalação Windows:**

- Baixar e executar o instalador
- Usar configurações padrão

**Instalação macOS:**

```bash
brew install git
```

**Instalação Linux:**

```bash
# Ubuntu/Debian
sudo apt install git

# Fedora/RHEL
sudo dnf install git
```

**Configuração inicial:**

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu.email@teste.com.br"
```

**Validação:**

```bash
git --version
# Deve mostrar: git version 2.30.x ou superior
```

- [ ] Git instalado
- [ ] Git configurado (nome e email)
- [ ] Comando `git --version` funcionando

### 4. IBM WebSphere Application Server Base

**Para:** Laboratório 1

**Nota:** Será fornecido acesso ao servidor durante o bootcamp ou instruções específicas de instalação.

**Validação:**

- [ ] WAS Base instalado ou acesso configurado
- [ ] Console administrativo acessível
- [ ] Servidor iniciando corretamente

### 5. IBM WebSphere Liberty

**Versão:** 23.0.0.x ou superior

**Download:** https://www.ibm.com/docs/en/was-liberty/base?topic=liberty-installing-from-archive

**Instalação:**

```bash
# Extrair para C:\Softwares\Liberty (Windows) ou /opt/liberty (Linux/Mac)
unzip wlp-*.zip -d C:\Softwares\Liberty

# Adicionar ao PATH
export PATH=$PATH:/opt/liberty/wlp/bin  # Linux/Mac
```

**Validação:**

```bash
cd C:\Softwares\Liberty\wlp\bin  # Windows
cd /opt/liberty/wlp/bin          # Linux/Mac

./server version
# Deve mostrar a versão do Liberty
```

- [ ] Liberty instalado em `C:\Softwares\Liberty\wlp`
- [ ] Comando `server version` funcionando
- [ ] Capaz de criar servidor de teste

### 6. Quarkus CLI

**Versão:** 3.6.0 ou superior

**Instalação Windows:**

```powershell
# Usando Chocolatey
choco install quarkus

# Ou baixar manualmente
# https://quarkus.io/get-started/
```

**Instalação macOS:**

```bash
brew install quarkusio/tap/quarkus
```

**Instalação Linux:**

```bash
# Usando SDKMAN!
sdk install quarkus

# Ou manualmente
curl -Ls https://sh.jbang.dev | bash -s - trust add https://repo1.maven.org/maven2/io/quarkus/quarkus-cli/
curl -Ls https://sh.jbang.dev | bash -s - app install --fresh --force quarkus@quarkusio
```

**Validação:**

```bash
quarkus version
# Deve mostrar: 3.6.x ou superior
```

- [ ] Quarkus CLI instalado
- [ ] Comando `quarkus version` funcionando
- [ ] Capaz de criar projeto de teste

### 7. IDE / Editor de Código

**Escolha uma das opções:**

#### Visual Studio Code (Recomendado)

**Download:** https://code.visualstudio.com/

**Extensões necessárias:**

```
- Extension Pack for Java (Microsoft)
- Spring Boot Extension Pack
- Quarkus Tools
- XML Tools
- YAML
- GitLens
- Docker (opcional)
```

**Instalação de extensões:**

```bash
code --install-extension vscjava.vscode-java-pack
code --install-extension vscjava.vscode-spring-boot-dashboard
code --install-extension redhat.vscode-quarkus
```

- [ ] VS Code instalado
- [ ] Extensões Java instaladas
- [ ] Extensões Quarkus instaladas

#### IntelliJ IDEA

**Download:** https://www.jetbrains.com/idea/download/

**Plugins necessários:**

- Quarkus Tools
- Liberty Tools

- [ ] IntelliJ IDEA instalado
- [ ] Plugins necessários instalados

#### Eclipse IDE

**Download:** https://www.eclipse.org/downloads/

**Plugins necessários:**

- Liberty Developer Tools
- Quarkus Tools

- [ ] Eclipse instalado
- [ ] Plugins necessários instalados

### 8. IBM Bob

**Acesso:** Será fornecido durante o bootcamp

**Pré-requisitos:**

- Conta IBM Cloud (será criada se necessário)
- Navegador moderno (Chrome, Firefox, Edge)

**Validação:**

- [ ] Acesso ao IBM Bob configurado
- [ ] Capaz de fazer login
- [ ] Interface funcionando corretamente

## 📦 Software Recomendado

### 1. Docker Desktop

**Para:** Containerização (Laboratório 4 - opcional)

**Download:** https://www.docker.com/products/docker-desktop

**Instalação:**

- Baixar e executar o instalador
- Seguir instruções específicas do SO

**Validação:**

```bash
docker --version
docker-compose --version
```

- [ ] Docker instalado (opcional)
- [ ] Docker rodando

### 2. Postman ou Insomnia

**Para:** Testes de API

**Download:**

- Postman: https://www.postman.com/downloads/
- Insomnia: https://insomnia.rest/download

- [ ] Ferramenta de API instalada

### 3. DBeaver ou Similar

**Para:** Visualização de banco de dados (se necessário)

**Download:** https://dbeaver.io/download/

- [ ] Cliente de BD instalado (opcional)

## 🔧 Configuração do Ambiente

### Variáveis de Ambiente

**Windows:**

```powershell
# Java
setx JAVA_HOME "C:\Program Files\Java\jdk-21"

# Maven
setx M2_HOME "C:\Program Files\Maven\apache-maven-3.9.x"

# Liberty
setx WLP_HOME "C:\Softwares\Liberty\wlp"

# PATH
setx PATH "%PATH%;%JAVA_HOME%\bin;%M2_HOME%\bin;%WLP_HOME%\bin"
```

**Linux/macOS:**

```bash
# Adicionar ao ~/.bashrc ou ~/.zshrc

# Java
export JAVA_HOME=/usr/lib/jvm/java-21-openjdk
export PATH=$JAVA_HOME/bin:$PATH

# Maven
export M2_HOME=/opt/maven
export PATH=$M2_HOME/bin:$PATH

# Liberty
export WLP_HOME=/opt/liberty/wlp
export PATH=$WLP_HOME/bin:$PATH

# Aplicar mudanças
source ~/.bashrc  # ou source ~/.zshrc
```

- [ ] JAVA_HOME configurado
- [ ] M2_HOME configurado
- [ ] WLP_HOME configurado
- [ ] PATH atualizado

### Configuração do Maven

**Criar/editar:** `~/.m2/settings.xml` (Linux/Mac) ou `C:\Users\[user]\.m2\settings.xml` (Windows)

```xml
<?xml version="1.0" encoding="UTF-8"?>
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"
          xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
          xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0
                              http://maven.apache.org/xsd/settings-1.0.0.xsd">

    <localRepository>${user.home}/.m2/repository</localRepository>

    <mirrors>
        <mirror>
            <id>central</id>
            <mirrorOf>central</mirrorOf>
            <url>https://repo.maven.apache.org/maven2</url>
        </mirror>
    </mirrors>

    <profiles>
        <profile>
            <id>java21</id>
            <properties>
                <maven.compiler.source>21</maven.compiler.source>
                <maven.compiler.target>21</maven.compiler.target>
            </properties>
        </profile>
    </profiles>
</settings>
```

- [ ] settings.xml configurado

## ✅ Validação Final

Execute este script para validar todas as instalações:

**Windows (PowerShell):**

```powershell
# Salvar como validate.ps1
Write-Host "=== Validação de Ambiente - Bootcamp ===" -ForegroundColor Green

Write-Host "`nValidando Java..." -ForegroundColor Yellow
java -version
javac -version

Write-Host "`nValidando Maven..." -ForegroundColor Yellow
mvn -version

Write-Host "`nValidando Git..." -ForegroundColor Yellow
git --version

Write-Host "`nValidando Quarkus..." -ForegroundColor Yellow
quarkus version

Write-Host "`nValidando Liberty..." -ForegroundColor Yellow
& "$env:WLP_HOME\bin\server.bat" version

Write-Host "`nValidando Docker (opcional)..." -ForegroundColor Yellow
docker --version

Write-Host "`n=== Validação Concluída ===" -ForegroundColor Green
```

**Linux/macOS (Bash):**

```bash
#!/bin/bash
# Salvar como validate.sh e executar: chmod +x validate.sh && ./validate.sh

echo "=== Validação de Ambiente - Bootcamp ==="

echo -e "\nValidando Java..."
java -version
javac -version

echo -e "\nValidando Maven..."
mvn -version

echo -e "\nValidando Git..."
git --version

echo -e "\nValidando Quarkus..."
quarkus version

echo -e "\nValidando Liberty..."
$WLP_HOME/bin/server version

echo -e "\nValidando Docker (opcional)..."
docker --version

echo -e "\n=== Validação Concluída ==="
```

### Checklist Final

- [ ] Todos os JDKs instalados (8, 11, 17, 21)
- [ ] Maven funcionando
- [ ] Git configurado
- [ ] Liberty instalado
- [ ] Quarkus CLI funcionando
- [ ] IDE configurada
- [ ] IBM Bob acessível
- [ ] Variáveis de ambiente configuradas
- [ ] Script de validação executado com sucesso

## 🆘 Suporte

### Problemas Comuns

#### Java não encontrado

```bash
# Verificar JAVA_HOME
echo $JAVA_HOME  # Linux/Mac
echo %JAVA_HOME% # Windows

# Verificar PATH
echo $PATH  # Linux/Mac
echo %PATH% # Windows
```

#### Maven não baixa dependências

```bash
# Limpar cache
mvn clean
rm -rf ~/.m2/repository

# Forçar atualização
mvn clean install -U
```

#### Liberty não inicia

```bash
# Verificar logs
cat $WLP_HOME/usr/servers/[server-name]/logs/messages.log

# Verificar portas
netstat -an | grep 9080
```

## 📅 Timeline de Preparação

### 2 Semanas Antes do Bootcamp

- [ ] Baixar todos os instaladores
- [ ] Instalar JDKs
- [ ] Instalar Maven e Git

### 1 Semana Antes

- [ ] Instalar Liberty e Quarkus
- [ ] Configurar IDE
- [ ] Executar validação

### 3 Dias Antes

- [ ] Testar IBM Bob
- [ ] Validação final
- [ ] Resolver pendências

### Dia do Bootcamp

- [ ] Chegar 15 minutos antes
- [ ] Validar conexão de internet
- [ ] Ter backup de instaladores

## 🎓 Recursos Adicionais

- [Documentação Java](https://docs.oracle.com/en/java/)
- [Maven Getting Started](https://maven.apache.org/guides/getting-started/)
- [Liberty Documentation](https://www.ibm.com/docs/en/was-liberty)
- [Quarkus Guides](https://quarkus.io/guides/)

---

**Versão:** 1.0

_Preparado para o Bootcamp - IBM Bob_
