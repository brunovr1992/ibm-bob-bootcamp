# 🔬 Laboratório 1 - Criação de Aplicação Java 8 com WAS Base

## 📋 Informações do Laboratório

- **Duração:** 45 minutos
- **Nível:** Iniciante
- **Objetivo:** Criar uma aplicação Java 8 completa rodando no WebSphere Application Server Base usando IBM Bob

## 🎯 Objetivos de Aprendizagem

Ao final deste laboratório, você será capaz de:

- ✅ Utilizar o IBM Bob para gerar código Java automaticamente
- ✅ Criar aplicações Java EE para WAS Base
- ✅ Implementar sistema de log com timestamp
- ✅ Desenvolver frontend com IBM Carbon UI/UX
- ✅ Realizar build Maven e gerar arquivo EAR
- ✅ Fazer deploy no WebSphere Application Server

## 📦 Pré-requisitos

Antes de iniciar, certifique-se de ter:

- ☑️ JDK 8 instalado e configurado
- ☑️ Maven 3.8+ instalado
- ☑️ WebSphere Application Server Base instalado
- ☑️ IBM Bob configurado e acessível
- ☑️ IDE (VS Code, Eclipse ou IntelliJ)

## 🚀 Passo a Passo

### Passo 1: Preparar o Ambiente (5 min)

1. Abra seu terminal ou prompt de comando
2. Crie um diretório para o projeto:

```bash
mkdir BobLab01
cd BobLab01
```

3. Verifique as versões instaladas:

```bash
java -version
mvn -version
```

### Passo 2: Usar o IBM Bob para Gerar a Aplicação (15 min)

1. Abra o IBM Bob
2. Copie e cole o prompt abaixo (também disponível em [prompt-bob.txt](./prompt-bob.txt))
3. Aguarde a geração do código

**Prompt para o IBM Bob:**

```
Criar uma aplicação em Java 8 que rode no WAS Base com as seguintes características:

1. Funcionalidade de Log:
   - Imprimir mensagem "Bob no Java 8 e WAS Base" a cada 5 segundos no SystemOut
   - Incluir timestamp em cada mensagem
   - Adicionar contador de execuções

2. Frontend com IBM Carbon UI/UX:
   - Título: "BoB no WAS Base"
   - Seção com detalhes do projeto
   - Exibir path para o log
   - Mostrar arquitetura em execução

3. Build e Deploy:
   - Executar comando: mvn clean install
   - Gerar arquivo EAR para instalação no WAS
   - Imprimir o context root para deploy no WAS

4. Estrutura do Projeto:
   - Seguir padrões Java EE
   - Configuração adequada para WAS Base
   - Documentação inline no código

Por favor, gere todos os arquivos necessários incluindo:
- pom.xml com todas as dependências
- Classes Java com anotações apropriadas
- Arquivos de configuração (web.xml, application.xml)
- Páginas HTML/JSP com IBM Carbon Design
- Instruções de build e deploy
```

### Passo 3: Revisar o Código Gerado (10 min)

Após o IBM Bob gerar o código, revise os seguintes arquivos:

#### 📄 Estrutura Esperada do Projeto

```
BobLab01/
├── pom.xml
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/ibm/bob/
│   │   │       ├── LoggerService.java
│   │   │       └── InfoServlet.java
│   │   ├── webapp/
│   │   │   ├── WEB-INF/
│   │   │   │   ├── web.xml
│   │   │   │   └── ibm-web-ext.xml
│   │   │   ├── index.html
│   │   │   └── css/
│   │   │       └── carbon-styles.css
│   │   └── resources/
│   │       └── META-INF/
│   │           └── application.xml
│   └── test/
│       └── java/
└── README.md
```

#### 🔍 Pontos Importantes para Verificar

**1. LoggerService.java**

- Verifica se há um timer que executa a cada 5 segundos
- Confirma a mensagem "Bob no Java 8 e WAS Base"
- Valida timestamp e contador

**2. Frontend (index.html)**

- Verifica uso do IBM Carbon Design System
- Confirma título "BoB no WAS Base"
- Valida exibição de informações do projeto

**3. pom.xml**

- Verifica dependências do Java EE 7
- Confirma configuração para gerar EAR
- Valida plugins Maven necessários

### Passo 4: Build da Aplicação (5 min)

1. No terminal, execute o build Maven:

```bash
mvn clean install
```

2. Aguarde a conclusão do build
3. Verifique se o arquivo EAR foi gerado em `target/BobLab01.ear`

**Saída Esperada:**

```
[INFO] BUILD SUCCESS
[INFO] Total time: XX.XXX s
[INFO] Finished at: YYYY-MM-DDTHH:MM:SS
```

### Passo 5: Deploy no WAS Base (10 min)

#### Opção A: Deploy via Console Administrativo

1. Acesse o console do WAS: `http://localhost:9060/ibm/console`
2. Faça login com suas credenciais
3. Navegue até: **Applications → New Application → New Enterprise Application**
4. Selecione o arquivo `BobLab01.ear`
5. Siga o wizard de instalação:
   - Aceite as configurações padrão
   - Defina o context root como `/boblab01`
   - Clique em **Finish**
6. Salve as configurações
7. Inicie a aplicação

#### Opção B: Deploy via wsadmin (Linha de Comando)

```bash
cd $WAS_HOME/bin
./wsadmin.sh -lang jython

# No prompt do wsadmin:
AdminApp.install('/path/to/BobLab01.ear', '[-contextroot /boblab01]')
AdminConfig.save()
AdminControl.invoke(AdminControl.queryNames('type=ApplicationManager,*'), 'startApplication', 'BobLab01')
```

### Passo 6: Validar a Aplicação (5 min)

1. **Verificar o Frontend:**
   - Acesse: `http://localhost:9080/boblab01`
   - Confirme que a página carrega corretamente
   - Verifique o título "BoB no WAS Base"
   - Valide as informações exibidas

2. **Verificar os Logs:**
   - Abra o arquivo de log do WAS: `$WAS_HOME/profiles/[profile]/logs/[server]/SystemOut.log`
   - Procure pelas mensagens "Bob no Java 8 e WAS Base"
   - Confirme que aparecem a cada 5 segundos
   - Valide timestamp e contador

**Exemplo de Log Esperado:**

```
[03/03/26 17:15:00:123 BRT] 00000001 SystemOut     O [2026-03-03 17:15:00] Bob no Java 8 e WAS Base - Execução #1
[03/03/26 17:15:05:456 BRT] 00000001 SystemOut     O [2026-03-03 17:15:05] Bob no Java 8 e WAS Base - Execução #2
[03/03/26 17:15:10:789 BRT] 00000001 SystemOut     O [2026-03-03 17:15:10] Bob no Java 8 e WAS Base - Execução #3
```

## ✅ Checklist de Validação

Marque cada item conforme completa:

- [ ] Código gerado pelo IBM Bob
- [ ] Build Maven executado com sucesso
- [ ] Arquivo EAR gerado
- [ ] Deploy realizado no WAS Base
- [ ] Aplicação iniciada sem erros
- [ ] Frontend acessível via navegador
- [ ] Título "BoB no WAS Base" visível
- [ ] Informações do projeto exibidas
- [ ] Logs aparecendo no SystemOut
- [ ] Mensagens a cada 5 segundos
- [ ] Timestamp correto nos logs
- [ ] Contador incrementando

## 🎓 Conceitos Aprendidos

### 1. IBM Bob para Geração de Código

- Como formular prompts efetivos
- Geração automática de estrutura de projeto
- Criação de código Java EE completo

### 2. Java EE e WAS Base

- Estrutura de aplicações enterprise
- Servlets e serviços
- Timers e agendamento de tarefas

### 3. IBM Carbon Design System

- Componentes de UI modernos
- Padrões de design IBM
- Responsividade e acessibilidade

### 4. Build e Deploy

- Maven para build de projetos Java
- Geração de arquivos EAR
- Deploy em servidores de aplicação

## 🐛 Troubleshooting

### Problema: Build Maven falha

**Solução:**

```bash
# Limpar cache do Maven
mvn clean
rm -rf ~/.m2/repository

# Tentar novamente
mvn clean install -U
```

### Problema: Deploy falha no WAS

**Possíveis causas:**

1. Porta já em uso
2. Aplicação com mesmo nome já instalada
3. Permissões insuficientes

**Soluções:**

```bash
# Verificar aplicações instaladas
./wsadmin.sh -c "print AdminApp.list()"

# Desinstalar aplicação existente
./wsadmin.sh -c "AdminApp.uninstall('BobLab01')"
./wsadmin.sh -c "AdminConfig.save()"
```

### Problema: Logs não aparecem

**Verificações:**

1. Confirme que a aplicação está rodando
2. Verifique o caminho correto do log
3. Aguarde pelo menos 5 segundos

**Comando para monitorar logs em tempo real:**

```bash
tail -f $WAS_HOME/profiles/[profile]/logs/[server]/SystemOut.log
```

### Problema: Frontend não carrega

**Verificações:**

1. Confirme o context root correto
2. Verifique se o servidor está rodando
3. Teste a URL completa: `http://localhost:9080/boblab01/`

## 📊 Informações Técnicas

### Context Root

```
/boblab01
```

### URL de Acesso

```
http://localhost:9080/boblab01
```

### Porta do WAS Base

```
HTTP: 9080
HTTPS: 9443
Admin Console: 9060
```

### Localização dos Logs

```
$WAS_HOME/profiles/[profile]/logs/[server]/SystemOut.log
```

## 🎯 Próximos Passos

Parabéns! Você completou o Laboratório 1. 🎉

Agora você está pronto para:

- **Laboratório 2:** Análise de Segurança da aplicação
- Aprender sobre vulnerabilidades comuns
- Gerar relatórios de segurança com IBM Bob

## 📚 Recursos Adicionais

- [IBM WebSphere Application Server Documentation](https://www.ibm.com/docs/was)
- [Java EE 7 Tutorial](https://docs.oracle.com/javaee/7/tutorial/)
- [IBM Carbon Design System](https://carbondesignsystem.com/)
- [Maven Documentation](https://maven.apache.org/guides/)

## 💡 Dicas Profissionais

1. **Sempre revise o código gerado pelo Bob** - Entenda o que foi criado
2. **Documente suas alterações** - Facilita manutenção futura
3. **Use logs estruturados** - Facilita debugging e monitoramento
4. **Teste localmente antes de deploy** - Evita problemas em produção
5. **Mantenha dependências atualizadas** - Segurança e performance

---

**Tempo estimado de conclusão:** 45 minutos  
**Dificuldade:** ⭐⭐☆☆☆ (Iniciante)  
**Pré-requisito para:** Laboratório 2

_Desenvolvido para o Bootcamp | Powered by IBM Bob_
