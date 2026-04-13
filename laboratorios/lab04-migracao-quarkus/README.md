# 🚀 Laboratório 4 - Migração para Quarkus

## 📋 Informações do Laboratório

- **Duração:** 60 minutos
- **Nível:** Avançado
- **Objetivo:** Migrar a aplicação de Liberty para Quarkus, explorando arquitetura cloud-native e supersonic startup

## 🎯 Objetivos de Aprendizagem

Ao final deste laboratório, você será capaz de:

- ✅ Utilizar o IBM Bob para migração para Quarkus
- ✅ Converter aplicações Java EE para Quarkus
- ✅ Configurar aplicações Quarkus
- ✅ Aproveitar recursos cloud-native
- ✅ Implementar hot reload e dev mode
- ✅ Otimizar para containers e Kubernetes

## 📦 Pré-requisitos

Antes de iniciar, certifique-se de ter:

- ☑️ Laboratório 3 concluído
- ☑️ JDK 21 instalado
- ☑️ Quarkus CLI instalado
- ☑️ Maven 3.8+
- ☑️ IBM Bob configurado
- ☑️ Docker (opcional, para native build)

## 🌟 Por que Quarkus?

### Quarkus: Supersonic Subatomic Java

Quarkus é um framework Java cloud-native projetado para GraalVM e HotSpot, otimizado para containers e Kubernetes.

| Característica       | Liberty     | Quarkus           |
| -------------------- | ----------- | ----------------- |
| **Startup**          | ~8 segundos | ~0.05 segundos ⚡ |
| **Memória (JVM)**    | ~80MB       | ~30MB 💾          |
| **Memória (Native)** | N/A         | ~12MB 🚀          |
| **First Request**    | ~1s         | ~0.001s ⚡        |
| **Throughput**       | Alto        | Muito Alto 📈     |
| **Dev Experience**   | Bom         | Excelente ✨      |

### Benefícios do Quarkus

- ✅ **Supersonic Startup:** Inicia em milissegundos
- ✅ **Subatomic Memory:** Consumo mínimo de memória
- ✅ **Live Reload:** Mudanças instantâneas sem restart
- ✅ **Cloud-Native:** Otimizado para containers
- ✅ **GraalVM Native:** Compilação nativa opcional
- ✅ **Developer Joy:** Experiência de desenvolvimento superior
- ✅ **Standards-Based:** Jakarta EE, MicroProfile, Spring

## 🗺️ Jornada de Migração

```
┌─────────────────────┐
│  Liberty + Java 21  │
│  Aplicação Atual    │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  Análise com Bob    │
│  Mapeamento APIs    │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  Conversão Quarkus  │
│  Dependências       │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  Configuração       │
│  application.props  │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  Dev Mode & Test    │
│  Validação          │
└─────────────────────┘
```

## 🚀 Passo a Passo

### Passo 1: Preparar o Ambiente (5 min)

1. **Verificar Quarkus CLI:**

```bash
quarkus version
# Deve mostrar: 3.x.x
```

2. **Criar diretório para migração:**

```bash
mkdir BobLab04-Quarkus
cd BobLab04-Quarkus
```

3. **Copiar código do Lab 3:**

```bash
cp -r ../BobLab03-Liberty/* .
```

### Passo 2: Executar Migração com IBM Bob (25 min)

1. Abra o IBM Bob
2. Navegue até o diretório BobLab04-Quarkus
3. Copie e cole o prompt abaixo (também disponível em [prompt-bob.txt](./prompt-bob.txt))

**Prompt para o IBM Bob:**

```
MIGRAÇÃO PARA QUARKUS

Migrar a aplicação e o servidor de aplicações para Quarkus.

Requisitos:

1. Migração Completa:
   - Converter aplicação Liberty para Quarkus
   - Adaptar código para o modelo Quarkus (CDI, JAX-RS)
   - Manter Java 21
   - Remover dependências específicas do Liberty
   - Adicionar extensões Quarkus necessárias

2. Alterações no Código:
   - Alterar mensagem do SystemOut para: "Aqui é o Bob e estou no Quarkus!!!!"
   - Adaptar frontend para Quarkus (servir arquivos estáticos)
   - Incluir mesmos detalhes da página de informações:
     * Nome do projeto
     * Versão
     * Tecnologias (Java 21, Quarkus)
     * Path do log
     * Arquitetura (Quarkus)
     * Métricas de performance
   - Manter funcionalidade de timer/scheduler

3. Configuração Quarkus:
   - Criar application.properties com:
     * Porta HTTP (8080)
     * Configurações de log
     * Dev mode settings
     * Métricas e health checks
   - Configurar hot reload
   - Habilitar extensões:
     * quarkus-resteasy-reactive
     * quarkus-scheduler
     * quarkus-smallrye-health
     * quarkus-micrometer
     * quarkus-logging-json

4. Estrutura do Projeto:
   - Seguir estrutura padrão Quarkus
   - src/main/resources/META-INF/resources para frontend
   - Configurações em application.properties
   - Testes em src/test/java

5. Build e Packaging:
   - Atualizar pom.xml para Quarkus
   - Configurar quarkus-maven-plugin
   - Suporte para JVM e Native builds
   - Profiles para dev, test e prod

6. Inicialização:
   - Iniciar servidor Quarkus em dev mode
   - Validar hot reload
   - Testar funcionalidades

7. Documentação:
   - Imprimir URL para acesso (http://localhost:8080)
   - Exibir path correto para o log no Quarkus
   - Documentar diferenças entre Liberty e Quarkus:
     * Startup time
     * Memory footprint
     * Developer experience
     * Cloud-native features
   - Listar benefícios do Quarkus:
     * Supersonic startup
     * Subatomic memory
     * Live reload
     * Native compilation
     * Container-first
   - Comandos úteis do Quarkus

8. Features Adicionais:
   - Health checks (/q/health)
   - Métricas (/q/metrics)
   - Dev UI (/q/dev)
   - OpenAPI/Swagger (/q/swagger-ui)

Gerar estrutura completa do projeto Quarkus:
- pom.xml com todas as dependências Quarkus
- application.properties completo
- Código Java adaptado para Quarkus
- Resources para frontend
- Testes básicos
- Dockerfile para containerização
- README.md com instruções completas
- Scripts de build e run

Certifique-se de que:
- O código está pronto para executar em dev mode
- Hot reload está funcionando
- Todas as funcionalidades são mantidas
- A aplicação é cloud-native ready
- A documentação é completa
```

### Passo 3: Revisar Código Migrado (10 min)

Após o IBM Bob gerar o código, revise a estrutura:

#### 📄 Estrutura Esperada do Projeto

```
BobLab04-Quarkus/
├── pom.xml (Quarkus)
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/ibm/bob/
│   │   │       ├── LoggerService.java
│   │   │       ├── InfoResource.java
│   │   │       └── HealthCheck.java
│   │   ├── resources/
│   │   │   ├── application.properties
│   │   │   └── META-INF/
│   │   │       └── resources/
│   │   │           ├── index.html
│   │   │           └── css/
│   │   └── docker/
│   │       ├── Dockerfile.jvm
│   │       └── Dockerfile.native
│   └── test/
│       └── java/
├── .dockerignore
└── README.md
```

#### 🔍 Mudanças Importantes

**1. pom.xml - Quarkus:**

```xml
<properties>
    <quarkus.platform.version>3.6.0</quarkus.platform.version>
    <maven.compiler.source>21</maven.compiler.source>
    <maven.compiler.target>21</maven.compiler.target>
</properties>

<dependencies>
    <dependency>
        <groupId>io.quarkus</groupId>
        <artifactId>quarkus-resteasy-reactive</artifactId>
    </dependency>
    <dependency>
        <groupId>io.quarkus</groupId>
        <artifactId>quarkus-scheduler</artifactId>
    </dependency>
</dependencies>
```

**2. application.properties:**

```properties
# HTTP Configuration
quarkus.http.port=8080
quarkus.http.host=0.0.0.0

# Logging
quarkus.log.level=INFO
quarkus.log.console.format=%d{HH:mm:ss} %-5p [%c{2.}] (%t) %s%e%n

# Dev Mode
quarkus.live-reload.instrumentation=true

# Application
quarkus.application.name=BobLab04-Quarkus
```

**3. LoggerService.java - Quarkus Scheduler:**

```java
@ApplicationScoped
public class LoggerService {
    private static final Logger LOG = Logger.getLogger(LoggerService.class);
    private int counter = 0;

    @Scheduled(every = "5s")
    void logMessage() {
        counter++;
        String timestamp = LocalDateTime.now()
            .format(DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss"));
        LOG.info(String.format("[%s] Aqui é o Bob e estou no Quarkus!!!! - Execução #%d",
            timestamp, counter));
    }
}
```

### Passo 4: Build da Aplicação (5 min)

1. **Build JVM mode:**

```bash
cd /path/to/BobLab04-Quarkus
mvn clean package
```

2. **Verificar JAR gerado:**

```bash
ls -lh target/quarkus-app/
# Deve mostrar: quarkus-run.jar
```

**Saída Esperada:**

```
[INFO] BUILD SUCCESS
[INFO] Total time: XX.XXX s
```

### Passo 5: Executar em Dev Mode (10 min)

**Dev Mode é a melhor feature do Quarkus!**

1. **Iniciar dev mode:**

```bash
mvn quarkus:dev
```

2. **Aguardar inicialização:**

```
__  ____  __  _____   ___  __ ____  ______
 --/ __ \/ / / / _ | / _ \/ //_/ / / / __/
 -/ /_/ / /_/ / __ |/ , _/ ,< / /_/ /\ \
--\___\_\____/_/ |_/_/|_/_/|_|\____/___/

INFO  [io.quarkus] (Quarkus Main Thread) BobLab04-Quarkus 1.0.0 on JVM started in 1.234s.
INFO  [io.quarkus] (Quarkus Main Thread) Profile dev activated. Live Coding activated.
INFO  [io.quarkus] (Quarkus Main Thread) Installed features: [cdi, resteasy-reactive, scheduler]
```

3. **Acessar aplicação:**
   - URL: `http://localhost:8080`
   - Dev UI: `http://localhost:8080/q/dev`
   - Health: `http://localhost:8080/q/health`

4. **Testar Hot Reload:**
   - Faça uma alteração no código
   - Salve o arquivo
   - Recarregue o navegador
   - Mudança aplicada instantaneamente! ⚡

### Passo 6: Validar Funcionalidades (5 min)

1. **Verificar Frontend:**
   - Acesse: `http://localhost:8080`
   - Confirme título e informações
   - Valide indicadores de Quarkus

2. **Verificar Logs:**

```bash
# Os logs aparecem no console onde você executou mvn quarkus:dev
```

**Log Esperado:**

```
17:45:00 INFO  [com.ita.bob.LoggerService] (executor-thread-1) [2026-03-03 17:45:00] Aqui é o Bob e estou no Quarkus!!!! - Execução #1
17:45:05 INFO  [com.ita.bob.LoggerService] (executor-thread-1) [2026-03-03 17:45:05] Aqui é o Bob e estou no Quarkus!!!! - Execução #2
```

3. **Verificar Health Check:**

```bash
curl http://localhost:8080/q/health
```

**Resposta Esperada:**

```json
{
  "status": "UP",
  "checks": [
    {
      "name": "BobLab Health Check",
      "status": "UP"
    }
  ]
}
```

### Passo 7: Explorar Dev UI (5 min)

Acesse: `http://localhost:8080/q/dev`

**Features disponíveis:**

- 📊 Configuration Editor
- 🔍 ArC (CDI Container)
- 📈 Metrics
- 🏥 Health Checks
- 📝 Logging
- 🔄 Continuous Testing

## ✅ Checklist de Validação

Marque cada item conforme completa:

- [ ] Quarkus CLI instalado
- [ ] Código migrado pelo IBM Bob
- [ ] pom.xml atualizado para Quarkus
- [ ] application.properties configurado
- [ ] Mensagem alterada para "Aqui é o Bob e estou no Quarkus!!!!"
- [ ] Build Maven executado com sucesso
- [ ] Dev mode iniciado
- [ ] Aplicação acessível via navegador
- [ ] Frontend atualizado visível
- [ ] Logs aparecendo corretamente
- [ ] Hot reload funcionando
- [ ] Health check respondendo
- [ ] Dev UI acessível
- [ ] Performance superior observada

## 🎓 Conceitos Aprendidos

### 1. Quarkus Framework

- Arquitetura cloud-native
- Supersonic startup
- Developer experience

### 2. Dev Mode e Hot Reload

- Live coding
- Continuous testing
- Instant feedback

### 3. Cloud-Native Features

- Health checks
- Metrics
- Containerização

### 4. Migração de Frameworks

- Liberty → Quarkus
- Java EE → Jakarta EE
- Adaptação de código

## 📊 Comparação Final de Performance

### Java 8 + WAS Base (Lab 1)

```
Startup: ~180 segundos
Memory: ~600MB
First Request: ~2s
Package: EAR (~50MB)
```

### Java 21 + Liberty (Lab 3)

```
Startup: ~8 segundos ⚡
Memory: ~80MB 💾
First Request: ~1s
Package: WAR (~20MB)
```

### Java 21 + Quarkus (Lab 4)

```
Startup: ~1.2 segundos ⚡⚡⚡ (150x mais rápido que WAS!)
Memory: ~30MB 💾💾 (20x menos que WAS!)
First Request: ~0.01s ⚡⚡⚡
Package: JAR (~15MB)
```

### Native Build (Opcional)

```
Startup: ~0.05 segundos 🚀 (3600x mais rápido!)
Memory: ~12MB 🚀🚀 (50x menos!)
First Request: ~0.001s 🚀🚀🚀
Package: Native (~50MB)
```

## 🐛 Troubleshooting

### Problema: Porta 8080 já em uso

**Solução:**

```properties
# application.properties
quarkus.http.port=8081
```

### Problema: Hot reload não funciona

**Verificações:**

1. Certifique-se de estar em dev mode
2. Verifique se salvou o arquivo
3. Aguarde alguns segundos

**Comando:**

```bash
mvn quarkus:dev -Dquarkus.live-reload.instrumentation=true
```

### Problema: Dependência não encontrada

**Solução:**

```bash
# Limpar e rebuildar
mvn clean install -U
```

### Problema: Native build falha

**Requisitos:**

- GraalVM instalado
- Native image configurado

**Comando:**

```bash
mvn package -Pnative
```

## 🚀 Build Native (Opcional - Avançado)

Para máxima performance, compile para native:

```bash
# Instalar GraalVM (se ainda não tiver)
sdk install java 21-graalvm

# Build native
mvn package -Pnative

# Executar
./target/BobLab04-Quarkus-1.0.0-runner
```

**Resultado:**

```
__  ____  __  _____   ___  __ ____  ______
 --/ __ \/ / / / _ | / _ \/ //_/ / / / __/
 -/ /_/ / /_/ / __ |/ , _/ ,< / /_/ /\ \
--\___\_\____/_/ |_/_/|_/_/|_|\____/___/

INFO  [io.quarkus] (main) BobLab04-Quarkus 1.0.0 native started in 0.052s. 🚀
```

## 🐳 Containerização

### Dockerfile.jvm (Gerado pelo Bob)

```dockerfile
FROM registry.access.redhat.com/ubi8/openjdk-21:1.18

COPY target/quarkus-app/lib/ /deployments/lib/
COPY target/quarkus-app/*.jar /deployments/
COPY target/quarkus-app/app/ /deployments/app/
COPY target/quarkus-app/quarkus/ /deployments/quarkus/

EXPOSE 8080
USER 185

ENTRYPOINT ["java", "-jar", "/deployments/quarkus-run.jar"]
```

### Build e Run com Docker

```bash
# Build da imagem
docker build -f src/main/docker/Dockerfile.jvm -t boblab-quarkus:jvm .

# Executar container
docker run -i --rm -p 8080:8080 boblab-quarkus:jvm

# Verificar
curl http://localhost:8080
```

## 💡 Comandos Úteis do Quarkus

```bash
# Dev mode
mvn quarkus:dev

# Dev mode com debug
mvn quarkus:dev -Ddebug=5005

# Build
mvn clean package

# Build native
mvn package -Pnative

# Executar testes
mvn test

# Continuous testing (em dev mode)
# Pressione 'r' no console

# Adicionar extensão
mvn quarkus:add-extension -Dextensions="extensao-name"

# Listar extensões
mvn quarkus:list-extensions

# Criar projeto novo
quarkus create app com.ibm:boblab --extensions=resteasy-reactive,scheduler
```

## 📈 Métricas e Monitoramento

### Acessar Métricas

```bash
curl http://localhost:8080/q/metrics
```

### Métricas Disponíveis

- JVM metrics (memory, threads, GC)
- HTTP metrics (requests, response times)
- Application metrics (custom)

### Prometheus Integration

```properties
# application.properties
quarkus.micrometer.export.prometheus.enabled=true
```

## 🎯 Próximos Passos

Parabéns! Você completou o Laboratório 4 e toda a jornada de modernização! 🎉

**Você migrou de:**

- Java 8 → Java 21
- WAS Base → Liberty → Quarkus
- Aplicação legada → Cloud-native

**Agora você está pronto para:**

- **Desafio Prático:** Aplicar conhecimentos em aplicação real do Itaú
- Implementar em produção
- Explorar Kubernetes e cloud

## 📚 Recursos Adicionais

### Documentação Quarkus

- [Quarkus Guides](https://quarkus.io/guides/)
- [Quarkus Extensions](https://quarkus.io/extensions/)
- [Quarkus Blog](https://quarkus.io/blog/)

### Comunidade

- [Quarkus GitHub](https://github.com/quarkusio/quarkus)
- [Quarkus Zulip Chat](https://quarkusio.zulipchat.com/)
- [Stack Overflow](https://stackoverflow.com/questions/tagged/quarkus)

### Cursos e Tutoriais

- [Red Hat Quarkus Training](https://developers.redhat.com/products/quarkus/getting-started)
- [Quarkus Workshops](https://quarkus.io/quarkus-workshops/)

## 💡 Dicas Profissionais

1. **Use Dev Mode sempre** - Produtividade máxima
2. **Explore Dev UI** - Ferramentas poderosas
3. **Continuous Testing** - Testes automáticos
4. **Native quando necessário** - Para máxima performance
5. **Containerize tudo** - Cloud-ready desde o início
6. **Monitore com métricas** - Observabilidade é essencial
7. **Health checks sempre** - Kubernetes precisa deles
8. **Documente APIs** - OpenAPI/Swagger incluído

## 🏆 Conquistas Desbloqueadas

- ✅ Migração completa Java 8 → Java 21
- ✅ Modernização WAS → Liberty → Quarkus
- ✅ Análise de segurança automatizada
- ✅ Cloud-native transformation
- ✅ Performance 150x melhor
- ✅ Memória 50x menor
- ✅ Developer experience superior

---

**Tempo estimado de conclusão:** 60 minutos
**Dificuldade:** ⭐⭐⭐⭐⭐ (Avançado)
**Próximo:** Desafio Prático

_Desenvolvido para o Bootcamp Itaú | Powered by IBM Bob_

```

```
