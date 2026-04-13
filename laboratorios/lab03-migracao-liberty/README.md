# ⚡ Laboratório 3 - Migração para Liberty e Java 21

## 📋 Informações do Laboratório

- **Duração:** 60 minutos
- **Nível:** Intermediário/Avançado
- **Objetivo:** Migrar a aplicação de WAS Base + Java 8 para WebSphere Liberty + Java 21 usando IBM Bob

## 🎯 Objetivos de Aprendizagem

Ao final deste laboratório, você será capaz de:

- ✅ Utilizar o IBM Bob para migração automatizada de aplicações
- ✅ Migrar de Java 8 para Java 21
- ✅ Converter aplicações de WAS Base para Liberty
- ✅ Configurar servidor Liberty
- ✅ Aproveitar recursos modernos do Java 21
- ✅ Validar aplicação migrada

## 📦 Pré-requisitos

Antes de iniciar, certifique-se de ter:

- ☑️ Laboratórios 1 e 2 concluídos
- ☑️ JDK 21 instalado e configurado
- ☑️ WebSphere Liberty instalado em `C:\Softwares\Liberty\wlp`
- ☑️ IBM Bob configurado e acessível
- ☑️ Migration plan de referência disponível
- ☑️ Código-fonte da aplicação BobLab

## 🚀 Por que Migrar?

### Benefícios do Liberty sobre WAS Base

| Aspecto             | WAS Base     | Liberty            |
| ------------------- | ------------ | ------------------ |
| **Startup**         | 2-5 minutos  | 5-10 segundos      |
| **Memória**         | 500MB+       | 50-100MB           |
| **Tamanho**         | ~1GB         | ~70MB              |
| **Configuração**    | XML complexo | server.xml simples |
| **Deploy**          | Console web  | Dropins ou CLI     |
| **Desenvolvimento** | Ciclo lento  | Hot reload         |

### Benefícios do Java 21 sobre Java 8

- ✅ **Performance:** JIT melhorado, GC mais eficiente
- ✅ **Segurança:** Patches e correções mais recentes
- ✅ **Recursos Modernos:** Records, Pattern Matching, Virtual Threads
- ✅ **APIs Atualizadas:** HTTP Client, Text Blocks, Switch Expressions
- ✅ **Suporte LTS:** Suporte de longo prazo até 2029

## 🗺️ Jornada de Migração

```
┌─────────────────────┐
│   Java 8 + WAS      │
│   Aplicação Atual   │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  Análise com Bob    │
│  Migration Plan     │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  Conversão Código   │
│  Java 8 → Java 21   │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  Adaptação Liberty  │
│  Configuração       │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  Build e Deploy     │
│  Validação          │
└─────────────────────┘
```

## 🚀 Passo a Passo

### Passo 1: Preparar o Ambiente (10 min)

1. **Verificar JDK 21:**

```bash
java -version
# Deve mostrar: openjdk version "21.x.x"
```

2. **Verificar Liberty:**

```bash
cd C:\Softwares\Liberty\wlp\bin
./server version
```

3. **Criar diretório para migração:**

```bash
mkdir BobLab03-Liberty
cd BobLab03-Liberty
```

4. **Copiar código-fonte do Lab 1:**

```bash
cp -r ../BobLab01/* .
```

### Passo 2: Analisar Migration Plan (5 min)

Antes de migrar, revise o migration plan de referência:

**Localização:** `C:\Softwares\BobWorkshop\BobHitsClaro\migration-plan`

**Principais pontos a observar:**

- APIs descontinuadas
- Mudanças de configuração
- Dependências a atualizar
- Recursos do Liberty a usar

### Passo 3: Executar Migração com IBM Bob (25 min)

1. Abra o IBM Bob
2. Navegue até o diretório BobLab03-Liberty
3. Copie e cole o prompt abaixo (também disponível em [prompt-bob.txt](./prompt-bob.txt))

**Prompt para o IBM Bob:**

```
MIGRAÇÃO PARA LIBERTY E JAVA 21

Migrar a aplicação atual para WebSphere Liberty e Java 21.

Requisitos:

1. Migração de Versão Java:
   - Converter código de Java 8 para Java 21
   - Utilizar features modernas do Java 21 quando apropriado:
     * Text Blocks para strings multilinha
     * Switch Expressions onde aplicável
     * Records para DTOs simples
     * Pattern Matching quando possível
   - Manter compatibilidade e funcionalidade

2. Migração de Servidor:
   - Converter de WAS Base para Liberty
   - Usar como referência: C:\Softwares\BobWorkshop\BobHitsClaro\migration-plan
   - Liberty instalado em: C:\Softwares\Liberty\wlp
   - Adaptar configurações XML para Liberty
   - Simplificar estrutura quando possível

3. Alterações no Código:
   - Alterar mensagem do SystemOut para: "Aqui é o Bob no Java 21!!!!"
   - Manter todas as outras funcionalidades
   - Atualizar frontend com informações da nova versão
   - Adicionar indicador de Java 21 e Liberty na página

4. Configuração do Servidor Liberty:
   - Criar servidor chamado: BobHitsJava21
   - Configurar para executar com JDK 21
   - Habilitar features necessárias:
     * servlet-5.0
     * jsp-3.0
     * cdi-3.0
     * jsonb-2.0
   - Configurar portas (HTTP: 9080, HTTPS: 9443)
   - Fazer deploy no servidor local

5. Build e Packaging:
   - Atualizar pom.xml para Java 21
   - Ajustar dependências para Liberty
   - Gerar WAR (não EAR) para Liberty
   - Configurar Maven para target Java 21

6. Documentação:
   - Exibir porta e URL da aplicação
   - Documentar mudanças realizadas
   - Listar benefícios da migração
   - Criar guia de deploy

Gerar todos os arquivos necessários:
- pom.xml atualizado
- server.xml para Liberty
- Código Java 21 modernizado
- Configurações Liberty
- Script de deploy
- Documentação de migração

Certifique-se de que o código está pronto para build e deploy imediato no Liberty.
```

### Passo 4: Revisar Código Migrado (10 min)

Após o IBM Bob gerar o código migrado, revise:

#### 📄 Estrutura Esperada do Projeto

```
BobLab03-Liberty/
├── pom.xml (atualizado para Java 21)
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/ibm/bob/
│   │   │       ├── LoggerService.java (Java 21)
│   │   │       └── InfoServlet.java (Java 21)
│   │   ├── webapp/
│   │   │   ├── WEB-INF/
│   │   │   │   └── web.xml
│   │   │   └── index.html (atualizado)
│   │   └── liberty/
│   │       └── config/
│   │           └── server.xml
│   └── test/
└── README.md
```

#### 🔍 Mudanças Importantes

**1. pom.xml - Java 21:**

```xml
<properties>
    <maven.compiler.source>21</maven.compiler.source>
    <maven.compiler.target>21</maven.compiler.target>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
</properties>

<packaging>war</packaging> <!-- Mudou de EAR para WAR -->
```

**2. LoggerService.java - Mensagem Atualizada:**

```java
private static final String MESSAGE = "Aqui é o Bob no Java 21!!!!";
```

**3. server.xml - Configuração Liberty:**

```xml
<server description="BobHitsJava21">
    <featureManager>
        <feature>servlet-5.0</feature>
        <feature>jsp-3.0</feature>
        <feature>cdi-3.0</feature>
    </featureManager>

    <httpEndpoint id="defaultHttpEndpoint"
                  host="*"
                  httpPort="9080"
                  httpsPort="9443" />

    <webApplication location="BobLab03-Liberty.war"
                    contextRoot="/boblab03" />
</server>
```

### Passo 5: Criar Servidor Liberty (5 min)

1. **Criar servidor:**

```bash
cd C:\Softwares\Liberty\wlp\bin
./server create BobHitsJava21
```

2. **Copiar configuração:**

```bash
cp /path/to/server.xml C:\Softwares\Liberty\wlp\usr\servers\BobHitsJava21\server.xml
```

3. **Verificar servidor criado:**

```bash
./server list
# Deve mostrar: BobHitsJava21
```

### Passo 6: Build da Aplicação (5 min)

1. **Executar build:**

```bash
cd /path/to/BobLab03-Liberty
mvn clean package
```

2. **Verificar WAR gerado:**

```bash
ls -lh target/*.war
# Deve mostrar: BobLab03-Liberty.war
```

**Saída Esperada:**

```
[INFO] BUILD SUCCESS
[INFO] Total time: XX.XXX s
[INFO] Finished at: YYYY-MM-DDTHH:MM:SS
```

### Passo 7: Deploy no Liberty (5 min)

**Opção A: Dropins (Mais Simples)**

```bash
cp target/BobLab03-Liberty.war C:\Softwares\Liberty\wlp\usr\servers\BobHitsJava21\dropins\
```

**Opção B: Apps Directory**

```bash
cp target/BobLab03-Liberty.war C:\Softwares\Liberty\wlp\usr\servers\BobHitsJava21\apps\
```

### Passo 8: Iniciar Servidor e Validar (5 min)

1. **Iniciar servidor:**

```bash
cd C:\Softwares\Liberty\wlp\bin
./server start BobHitsJava21
```

2. **Monitorar logs:**

```bash
./server run BobHitsJava21
# ou
tail -f C:\Softwares\Liberty\wlp\usr\servers\BobHitsJava21\logs\messages.log
```

3. **Verificar startup:**

```
[AUDIT   ] CWWKF0011I: The BobHitsJava21 server is ready to run a smarter planet.
```

4. **Acessar aplicação:**
   - URL: `http://localhost:9080/boblab03`
   - Verificar título e informações
   - Confirmar mensagem "Aqui é o Bob no Java 21!!!!"

5. **Verificar logs da aplicação:**

```bash
tail -f C:\Softwares\Liberty\wlp\usr\servers\BobHitsJava21\logs\console.log
```

**Log Esperado:**

```
[2026-03-03 17:30:00] Aqui é o Bob no Java 21!!!! - Execução #1
[2026-03-03 17:30:05] Aqui é o Bob no Java 21!!!! - Execução #2
[2026-03-03 17:30:10] Aqui é o Bob no Java 21!!!! - Execução #3
```

## ✅ Checklist de Validação

Marque cada item conforme completa:

- [ ] JDK 21 instalado e configurado
- [ ] Liberty instalado e verificado
- [ ] Migration plan revisado
- [ ] Código migrado pelo IBM Bob
- [ ] pom.xml atualizado para Java 21
- [ ] Mensagem alterada para "Aqui é o Bob no Java 21!!!!"
- [ ] server.xml criado para Liberty
- [ ] Servidor BobHitsJava21 criado
- [ ] Build Maven executado com sucesso
- [ ] WAR gerado
- [ ] Deploy realizado no Liberty
- [ ] Servidor iniciado sem erros
- [ ] Aplicação acessível via navegador
- [ ] Frontend atualizado visível
- [ ] Logs aparecendo corretamente
- [ ] Performance melhorada observada

## 🎓 Conceitos Aprendidos

### 1. Migração de Versões Java

- Compatibilidade entre versões
- Novos recursos do Java 21
- Modernização de código

### 2. WebSphere Liberty

- Arquitetura modular
- Configuração simplificada
- Deploy rápido e eficiente

### 3. Processo de Migração

- Análise de impacto
- Planejamento de migração
- Execução e validação

### 4. Automação com IA

- Uso do IBM Bob para migração
- Geração de código modernizado
- Aceleração do processo

## 📊 Comparação de Performance

### Antes (WAS Base + Java 8)

```
Startup Time: ~3 minutos
Memory Usage: ~600MB
Deploy Time: ~2 minutos
Hot Reload: Não suportado
```

### Depois (Liberty + Java 21)

```
Startup Time: ~8 segundos ⚡ (22x mais rápido)
Memory Usage: ~80MB 💾 (7.5x menos memória)
Deploy Time: ~5 segundos ⚡ (24x mais rápido)
Hot Reload: Suportado ✅
```

## 🐛 Troubleshooting

### Problema: Erro de compilação Java 21

**Erro:**

```
[ERROR] Source option 8 is no longer supported. Use 11 or later.
```

**Solução:**

```xml
<!-- Atualizar pom.xml -->
<maven.compiler.source>21</maven.compiler.source>
<maven.compiler.target>21</maven.compiler.target>
```

### Problema: Feature não encontrada no Liberty

**Erro:**

```
CWWKF0001E: A feature definition could not be found for servlet-5.0
```

**Solução:**

```bash
# Instalar features necessárias
./installUtility install servlet-5.0 jsp-3.0 cdi-3.0
```

### Problema: Aplicação não inicia no Liberty

**Verificações:**

1. Confirme que o WAR está no diretório correto
2. Verifique o server.xml
3. Revise os logs em messages.log

**Comando útil:**

```bash
./server dump BobHitsJava21
# Gera dump completo para análise
```

### Problema: Porta já em uso

**Solução:**

```xml
<!-- Alterar portas no server.xml -->
<httpEndpoint id="defaultHttpEndpoint"
              httpPort="9081"
              httpsPort="9444" />
```

## 💡 Recursos Modernos do Java 21

### Text Blocks

```java
// Antes (Java 8)
String html = "<html>\n" +
              "  <body>\n" +
              "    <h1>Bob</h1>\n" +
              "  </body>\n" +
              "</html>";

// Depois (Java 21)
String html = """
    <html>
      <body>
        <h1>Bob</h1>
      </body>
    </html>
    """;
```

### Records

```java
// Antes (Java 8)
public class User {
    private final String name;
    private final int age;

    public User(String name, int age) {
        this.name = name;
        this.age = age;
    }
    // getters, equals, hashCode, toString...
}

// Depois (Java 21)
public record User(String name, int age) {}
```

### Pattern Matching

```java
// Antes (Java 8)
if (obj instanceof String) {
    String s = (String) obj;
    System.out.println(s.length());
}

// Depois (Java 21)
if (obj instanceof String s) {
    System.out.println(s.length());
}
```

## 🎯 Próximos Passos

Parabéns! Você completou o Laboratório 3. 🎉

Agora você está pronto para:

- **Laboratório 4:** Migração para Quarkus
- Explorar arquitetura cloud-native
- Aproveitar recursos do Quarkus

## 📚 Recursos Adicionais

- [WebSphere Liberty Documentation](https://www.ibm.com/docs/liberty)
- [Java 21 Release Notes](https://openjdk.org/projects/jdk/21/)
- [Liberty Migration Toolkit](https://www.ibm.com/docs/was-liberty/base?topic=tools-migration-toolkit-application-binaries)
- [Java 21 New Features](https://www.oracle.com/java/technologies/javase/21-relnote-issues.html)

---

**Tempo estimado de conclusão:** 60 minutos  
**Dificuldade:** ⭐⭐⭐⭐☆ (Intermediário/Avançado)  
**Pré-requisito para:** Laboratório 4

_Desenvolvido para o Bootcamp | Powered by IBM Bob_
