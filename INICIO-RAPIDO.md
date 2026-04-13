# 🚀 Guia de Início Rápido - Bootcamp

## 📋 Para Participantes

### Antes do Bootcamp (Checklist Essencial)

#### 1. Instalações Obrigatórias ⚠️

```bash
# Verificar instalações
java -version        # Deve mostrar Java 8, 11, 17 e 21
mvn -version         # Maven 3.8+
git --version        # Git 2.30+
quarkus version      # Quarkus 3.6+
```

**Se algo falhar:** Consulte [Checklist de Instalação](./pre-requisitos/checklist-instalacao.md)

#### 2. Configurar Ambiente

- [ ] JAVA_HOME configurado para JDK 21
- [ ] Maven settings.xml configurado
- [ ] Liberty instalado em `C:\Softwares\Liberty\wlp`
- [ ] IDE configurada (VS Code, IntelliJ ou Eclipse)
- [ ] IBM Bob acessível

#### 3. Validar Setup

Execute o script de validação:

```bash
# Windows
.\validate.ps1

# Linux/Mac
./validate.sh
```

### No Dia do Bootcamp

#### Preparação

- Conectar à rede (se presencial)
- Abrir VS Code ou IDE
- Testar acesso ao IBM Bob

#### Durante os Labs

1. **Siga o guia passo a passo** de cada laboratório
2. **Use os prompts fornecidos** para o IBM Bob
3. **Marque os checklists** conforme avança
4. **Peça ajuda** se travar por mais de 5 minutos

#### Desafio Prático

- Trabalhe em equipe
- Use o template de análise
- Foque nos resultados, não na perfeição

---

## 👨‍🏫 Para Instrutores

### Preparação (1 semana antes)

#### Materiais

- [ ] Revisar todos os laboratórios
- [ ] Testar prompts do IBM Bob
- [ ] Preparar aplicação para desafio
- [ ] Imprimir materiais de apoio

#### Ambiente

- [ ] Validar acesso IBM Bob para todos
- [ ] Preparar ambiente de demonstração
- [ ] Testar projetor e áudio

#### Contingência

- [ ] Plano B para problemas de rede
- [ ] Instaladores offline disponíveis
- [ ] Exemplos de código backup

---

## 📂 Navegação Rápida

### Documentos Principais

- [README Principal](./README.md) - Visão geral completa
- [Estrutura Completa](./ESTRUTURA-COMPLETA.md) - Resumo executivo

### Laboratórios

1. [Lab 1: Java 8 + WAS Base](./laboratorios/lab01-java8-was-base/README.md) - 45 min
2. [Lab 2: Análise de Segurança](./laboratorios/lab02-analise-seguranca/README.md) - 45 min
3. [Lab 3: Migração Liberty](./laboratorios/lab03-migracao-liberty/README.md) - 60 min
4. [Lab 4: Migração Quarkus](./laboratorios/lab04-migracao-quarkus/README.md) - 60 min

### Recursos

- [Checklist de Instalação](./pre-requisitos/checklist-instalacao.md)
- [Desafio Prático](./desafio-pratico/README.md)
- [Template de Análise](./desafio-pratico/template-analise.md)
- [Diagramas](./recursos/diagramas/)
- [Links Úteis](./recursos/referencias/links-uteis.md)

---

## ⚡ Comandos Rápidos

### Java

```bash
# Trocar versão do Java (com SDKMAN!)
sdk use java 21.0.xxx-tem
sdk use java 8.0.xxx-tem

# Verificar versão
java -version
javac -version
```

### Maven

```bash
# Build completo
mvn clean install

# Build rápido (sem testes)
mvn clean install -DskipTests

# Limpar cache
rm -rf ~/.m2/repository
```

### Liberty

```bash
# Criar servidor
server create BobHitsJava21

# Iniciar servidor
server start BobHitsJava21

# Parar servidor
server stop BobHitsJava21

# Ver logs
tail -f wlp/usr/servers/BobHitsJava21/logs/messages.log
```

### Quarkus

```bash
# Dev mode
mvn quarkus:dev

# Build
mvn clean package

# Executar
java -jar target/quarkus-app/quarkus-run.jar

# Native build
mvn package -Pnative
```

### Git

```bash
# Clonar repositório
git clone <url>

# Status
git status

# Commit
git add .
git commit -m "mensagem"

# Push
git push origin main
```

---

## 🆘 Problemas Comuns

### "Java não encontrado"

```bash
# Verificar JAVA_HOME
echo $JAVA_HOME  # Linux/Mac
echo %JAVA_HOME% # Windows

# Configurar (exemplo)
export JAVA_HOME=/usr/lib/jvm/java-21-openjdk
```

### "Maven não baixa dependências"

```bash
# Forçar atualização
mvn clean install -U

# Limpar cache
rm -rf ~/.m2/repository
```

### "Porta já em uso"

```bash
# Verificar porta
netstat -an | grep 9080  # Linux/Mac
netstat -an | findstr 9080  # Windows

# Matar processo
kill -9 <PID>  # Linux/Mac
taskkill /PID <PID> /F  # Windows
```

---

## 🎯 Dicas de Sucesso

### Para Aprender Melhor

1. **Leia o guia antes** de executar
2. **Entenda o código** gerado pelo Bob
3. **Faça anotações** durante os labs
4. **Tire dúvidas** imediatamente
5. **Pratique depois** do bootcamp

### Para o Desafio

1. **Divida tarefas** no grupo
2. **Use o template** fornecido
3. **Foque no essencial** (não na perfeição)
4. **Gerencie o tempo** (90 minutos)
5. **Prepare apresentação** clara

### Para Networking

1. **Conheça os colegas** nos breaks
2. **Compartilhe experiências**
3. **Troque contatos**
4. **Forme grupos de estudo**
5. **Mantenha contato** pós-bootcamp

---

## 📚 Após o Bootcamp

### Próximos Passos

1. Revisar materiais do bootcamp
2. Praticar laboratórios novamente
3. Aplicar em projetos reais
4. Compartilhar conhecimento
5. Continuar aprendendo

### Recursos Contínuos

- Materiais do bootcamp (sempre disponíveis)
- [Links úteis](./recursos/referencias/links-uteis.md)
- Comunidades online
- Documentação oficial

---

## ✅ Checklist Final

### Antes do Bootcamp

- [ ] Todas as ferramentas instaladas
- [ ] Ambiente validado
- [ ] IBM Bob acessível
- [ ] Materiais revisados
- [ ] Laptop carregado

### Durante o Bootcamp

- [ ] Lab 1 completo
- [ ] Lab 2 completo
- [ ] Lab 3 completo
- [ ] Lab 4 completo
- [ ] Desafio apresentado

---

## 🎉 Mensagem Final

**Bem-vindo ao Bootcamp - Modernizando Aplicações Java com IBM Bob!**

Este é o início de uma jornada incrível de aprendizado e transformação. Você vai:

- ✨ Dominar o IBM Bob
- 🚀 Modernizar aplicações Java
- 🔒 Melhorar segurança de código
- ☁️ Criar aplicações cloud-native
- 🤝 Fazer networking valioso

**Aproveite cada momento, faça perguntas, pratique muito e divirta-se!**

---

_Guia de Início Rápido | Bootcamp IBM Bob_
