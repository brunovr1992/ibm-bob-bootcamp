# 🏆 Desafio Prático - Análise de Aplicação Real

## 📋 Informações do Desafio

- **Duração:** Aproximadamente 90 minutos
- **Formato:** Trabalho em grupos (4-5 pessoas)
- **Nível:** Aplicação prática de todos os conceitos
- **Objetivo:** Analisar uma aplicação real e propor plano de modernização usando IBM Bob

## 🎯 Objetivos do Desafio

Ao final deste desafio, seu grupo será capaz de:

- ✅ Analisar aplicações Java legadas de forma estruturada
- ✅ Documentar arquitetura e dependências automaticamente
- ✅ Identificar pontos críticos de modernização
- ✅ Propor plano de migração viável
- ✅ Estimar esforço e riscos
- ✅ Apresentar resultados de forma profissional

## 📦 Materiais Fornecidos

Cada grupo receberá:

- 📁 Código-fonte de uma aplicação real
- 📄 Contexto de negócio da aplicação
- 🔑 Acesso ao IBM Bob
- 📊 Template de análise (veja abaixo)
- ⏱️ Tempo para completar o desafio

## 🗺️ Estrutura do Desafio

```
┌─────────────────────────────┐
│  Fase 1: Análise Inicial    │
│  (20 minutos)               │
└──────────┬──────────────────┘
           │
           ▼
┌─────────────────────────────┐
│  Fase 2: Documentação       │
│  com IBM Bob (25 minutos)   │
└──────────┬──────────────────┘
           │
           ▼
┌─────────────────────────────┐
│  Fase 3: Análise de         │
│  Modernização (25 minutos)  │
└──────────┬──────────────────┘
           │
           ▼
┌─────────────────────────────┐
│  Fase 4: Apresentação       │
│  (20 minutos - 5 min/grupo) │
└─────────────────────────────┘
```

## 📝 Fase 1: Análise Inicial

### Objetivos

- Entender o propósito da aplicação
- Identificar tecnologias utilizadas
- Mapear estrutura do projeto
- Levantar primeiras impressões

### Atividades

#### 1. Exploração do Código

**Perguntas a responder:**

- Qual é o propósito da aplicação?
- Quais são as principais funcionalidades?
- Qual a arquitetura atual? (Monolito, SOA, etc.)
- Quais tecnologias são utilizadas?
- Qual versão do Java?
- Qual servidor de aplicação?
- Quais frameworks principais?

**Checklist de Exploração:**

- [ ] Revisar README.md (se existir)
- [ ] Analisar pom.xml ou build.gradle
- [ ] Explorar estrutura de diretórios
- [ ] Identificar pontos de entrada (main, servlets, controllers)
- [ ] Verificar arquivos de configuração

#### 2. Mapeamento de Dependências

**Use o IBM Bob para:**

```
Analise o arquivo pom.xml (ou build.gradle) e liste:
1. Todas as dependências do projeto
2. Versões utilizadas
3. Dependências desatualizadas
4. Dependências com vulnerabilidades conhecidas
5. Dependências que podem ser removidas
```

**Documente:**

- Total de dependências
- Dependências críticas
- Dependências problemáticas
- Sugestões de atualização

## 📚 Fase 2: Documentação com IBM Bob

### Objetivos

- Gerar documentação automática
- Criar diagramas de arquitetura
- Documentar fluxos principais
- Identificar componentes críticos

### Atividades

#### 1. Documentação Geral

**Prompt para IBM Bob:**

```
Analise esta aplicação Java e gere documentação completa em português incluindo:

1. Visão Geral:
   - Propósito da aplicação
   - Principais funcionalidades
   - Arquitetura geral

2. Componentes Principais:
   - Lista de classes principais
   - Responsabilidade de cada componente
   - Relacionamentos entre componentes

3. Fluxos de Dados:
   - Como os dados fluem pela aplicação
   - Integrações externas
   - Persistência de dados

4. Tecnologias Utilizadas:
   - Stack completo
   - Versões
   - Propósito de cada tecnologia

5. Pontos de Atenção:
   - Código complexo
   - Possíveis problemas
   - Débito técnico

Formato: Documento markdown estruturado
```

#### 2. Diagramas de Arquitetura

**Prompt para IBM Bob:**

```
Crie diagramas em formato Mermaid para:

1. Diagrama de Componentes:
   - Principais módulos
   - Relacionamentos
   - Dependências

2. Diagrama de Fluxo:
   - Fluxo principal da aplicação
   - Pontos de decisão
   - Integrações

3. Diagrama de Dados:
   - Entidades principais
   - Relacionamentos
   - Persistência

Use sintaxe Mermaid para os diagramas.
```

#### 3. Análise de Complexidade

**Prompt para IBM Bob:**

```
Analise a complexidade do código e identifique:

1. Classes mais complexas (por linhas de código e complexidade ciclomática)
2. Métodos muito longos (>50 linhas)
3. Classes com muitas responsabilidades
4. Código duplicado
5. Padrões de design utilizados (ou falta deles)

Para cada problema, sugira refatoração.
```

## 🔍 Fase 3: Análise de Modernização

### Objetivos

- Identificar oportunidades de modernização
- Avaliar viabilidade técnica
- Propor estratégia de migração
- Estimar esforço e riscos

### Atividades

#### 1. Análise de Modernização

**Prompt para IBM Bob:**

```
Analise esta aplicação e proponha plano de modernização considerando:

1. Migração de Versão Java:
   - Versão atual vs versão alvo (Java 21)
   - Incompatibilidades a resolver
   - APIs descontinuadas
   - Novos recursos a aproveitar

2. Migração de Servidor:
   - Servidor atual vs opções modernas (Liberty, Quarkus)
   - Benefícios de cada opção
   - Esforço de migração
   - Riscos envolvidos

3. Modernização de Código:
   - Refatorações necessárias
   - Padrões modernos a aplicar
   - Testes a criar
   - Documentação a atualizar

4. Arquitetura:
   - Oportunidades de microserviços
   - Separação de responsabilidades
   - Cloud-native features

Priorize as ações por impacto vs esforço.
```

#### 2. Análise de Segurança

**Prompt para IBM Bob:**

```
Execute análise de segurança focada em:

1. Top 5 vulnerabilidades mais críticas
2. Exposição de dados sensíveis
3. Problemas de autenticação/autorização
4. Validação de entrada
5. Dependências vulneráveis

Para cada problema:
- Gravidade
- Impacto
- Correção recomendada
- Prioridade
```

#### 3. Plano de Ação

**Estruture o plano em fases:**

**Fase 1 - Preparação:**

- Correções críticas de segurança
- Setup de ambiente
- Criação de testes

**Fase 2 - Migração Inicial:**

- Migração de Java
- Atualização de dependências
- Refatorações básicas

**Fase 3 - Modernização:**

- Migração de servidor
- Modernização de código
- Implementação de features cloud-native

**Fase 4 - Validação:**

- Testes completos
- Performance testing
- Security testing

## 🎤 Fase 4: Apresentação

### Formato

- Aproximadamente 5 minutos por grupo
- Apresentação de slides ou documento
- Foco nos resultados e recomendações

### Estrutura da Apresentação

#### Slide 1: Visão Geral da Aplicação

- Nome e propósito
- Tecnologias atuais
- Principais funcionalidades

#### Slide 2: Análise Técnica

- Arquitetura atual
- Stack tecnológico
- Métricas (LOC, complexidade, dependências)

#### Slide 3: Principais Problemas Identificados

- Top 3 problemas técnicos
- Top 3 vulnerabilidades de segurança
- Débito técnico

#### Slide 4: Proposta de Modernização

- Estratégia recomendada
- Tecnologias alvo
- Benefícios esperados

#### Slide 5: Plano de Ação e Estimativas

- Fases do projeto
- Timeline
- Esforço estimado
- Riscos principais

### Critérios de Avaliação

| Critério                  | Peso | Descrição                          |
| ------------------------- | ---- | ---------------------------------- |
| **Análise Técnica**       | 25%  | Profundidade e precisão da análise |
| **Uso do IBM Bob**        | 20%  | Efetividade no uso da ferramenta   |
| **Plano de Modernização** | 25%  | Viabilidade e completude do plano  |
| **Apresentação**          | 15%  | Clareza e organização              |
| **Trabalho em Equipe**    | 15%  | Colaboração e divisão de tarefas   |

## 📊 Template de Análise

Use este template para documentar sua análise:

### 1. Informações Básicas

```markdown
# Análise de Modernização - [Nome da Aplicação]

## Grupo

- Integrante 1
- Integrante 2
- Integrante 3
- Integrante 4
- Integrante 5

## Data

[Data do bootcamp]

## Aplicação Analisada

- Nome:
- Propósito:
- Domínio de Negócio:
```

### 2. Análise Técnica Atual

```markdown
## Stack Tecnológico Atual

### Linguagem e Versão

- Java: [versão]
- Build Tool: [Maven/Gradle]

### Servidor de Aplicação

- Tipo: [WAS/Tomcat/etc]
- Versão:

### Frameworks Principais

- [Framework 1]: [versão]
- [Framework 2]: [versão]
- [Framework 3]: [versão]

### Banco de Dados

- Tipo:
- Versão:
- ORM:

### Dependências Principais

Total: [número]

- [Dependência 1]: [versão]
- [Dependência 2]: [versão]
- [Dependência 3]: [versão]

## Métricas de Código

- Linhas de Código: [número]
- Número de Classes: [número]
- Número de Métodos: [número]
- Complexidade Média: [número]
- Cobertura de Testes: [%]
```

### 3. Problemas Identificados

```markdown
## Problemas Técnicos

### Problema 1: [Título]

- **Gravidade:** [Crítico/Alto/Médio/Baixo]
- **Descrição:** [descrição detalhada]
- **Impacto:** [impacto no negócio/sistema]
- **Localização:** [arquivo/classe/método]
- **Correção Sugerida:** [como corrigir]

### Problema 2: [Título]

[repetir estrutura]

### Problema 3: [Título]

[repetir estrutura]

## Vulnerabilidades de Segurança

### Vulnerabilidade 1: [Título]

- **Gravidade:** [Crítico/Alto/Médio/Baixo]
- **Tipo:** [SQL Injection/XSS/etc]
- **Descrição:** [descrição]
- **Impacto:** [impacto]
- **Correção:** [como corrigir]

[repetir para outras vulnerabilidades]

## Débito Técnico

- **Código Duplicado:** [descrição e localização]
- **Falta de Testes:** [áreas sem cobertura]
- **Documentação:** [o que falta]
- **Padrões não Seguidos:** [quais]
```

### 4. Proposta de Modernização

```markdown
## Estratégia de Modernização

### Opção Recomendada

[Liberty/Quarkus/Outro]

### Justificativa

[Por que esta opção?]

### Benefícios Esperados

#### Performance

- Startup: [atual] → [esperado]
- Memory: [atual] → [esperado]
- Throughput: [atual] → [esperado]

#### Desenvolvimento

- [Benefício 1]
- [Benefício 2]
- [Benefício 3]

#### Operação

- [Benefício 1]
- [Benefício 2]
- [Benefício 3]

## Roadmap de Migração

### Fase 1: Preparação (Semanas 1-2)

- [ ] Correções críticas de segurança
- [ ] Setup de ambiente
- [ ] Criação de testes base
- [ ] Documentação inicial

**Esforço:** [X] dias/pessoa
**Risco:** [Baixo/Médio/Alto]

### Fase 2: Migração Inicial (Semanas 3-6)

- [ ] Migração para Java 21
- [ ] Atualização de dependências
- [ ] Refatorações básicas
- [ ] Testes de regressão

**Esforço:** [X] dias/pessoa
**Risco:** [Baixo/Médio/Alto]

### Fase 3: Modernização (Semanas 7-14)

- [ ] Migração de servidor
- [ ] Modernização de código
- [ ] Cloud-native features
- [ ] Performance tuning

**Esforço:** [X] dias/pessoa
**Risco:** [Baixo/Médio/Alto]

### Fase 4: Validação (Semanas 15-16)

- [ ] Testes completos
- [ ] Performance testing
- [ ] Security testing
- [ ] Documentação final

**Esforço:** [X] dias/pessoa
**Risco:** [Baixo/Médio/Alto]

## Estimativas

### Esforço Total

- **Desenvolvimento:** [X] dias/pessoa
- **Testes:** [X] dias/pessoa
- **Documentação:** [X] dias/pessoa
- **Total:** [X] dias/pessoa

### Timeline

- **Início:** [data]
- **Fim:** [data]
- **Duração:** [X] semanas

### Equipe Necessária

- [x] Desenvolvedores Senior
- [x] Desenvolvedores Pleno
- [x] QA Engineers
- [x] DevOps Engineer

## Riscos e Mitigações

### Risco 1: [Título]

- **Probabilidade:** [Alta/Média/Baixa]
- **Impacto:** [Alto/Médio/Baixo]
- **Mitigação:** [como mitigar]

[repetir para outros riscos]
```

### 5. Conclusão

```markdown
## Recomendações Finais

1. [Recomendação 1]
2. [Recomendação 2]
3. [Recomendação 3]

## Próximos Passos Imediatos

1. [Ação 1]
2. [Ação 2]
3. [Ação 3]

## ROI Esperado

- **Investimento:** [valor/esforço]
- **Retorno:** [benefícios quantificados]
- **Payback:** [tempo para retorno]
```

## 💡 Dicas para o Desafio

### Para Análise Efetiva

1. **Comece pelo README** - Entenda o contexto
2. **Use o IBM Bob intensivamente** - Ele acelera muito
3. **Foque no crítico** - Não tente analisar tudo
4. **Documente enquanto analisa** - Não deixe para depois
5. **Pense em viabilidade** - Propostas devem ser práticas

### Para Trabalho em Grupo

1. **Divida as tarefas** - Cada um foca em uma área
2. **Comunique-se** - Compartilhe descobertas
3. **Consolide resultados** - Junte as análises
4. **Revise em conjunto** - Valide as conclusões
5. **Prepare apresentação juntos** - Todos devem conhecer o conteúdo

### Para Apresentação

1. **Seja objetivo** - 5 minutos passam rápido
2. **Use visuais** - Diagramas e gráficos ajudam
3. **Foque em resultados** - Não no processo
4. **Seja realista** - Estimativas devem fazer sentido
5. **Prepare para perguntas** - Conheça bem sua análise

## 🎯 Entregáveis

Ao final do desafio, cada grupo deve entregar:

1. **Documento de Análise Completo**
   - Usando o template fornecido
   - Formato: Markdown ou PDF

2. **Apresentação**
   - 5 slides
   - Formato: PowerPoint ou PDF

3. **Artefatos Gerados pelo IBM Bob**
   - Documentação
   - Diagramas
   - Relatórios de análise

## 🏆 Premiação

- 🥇 **1º Lugar:** Certificado de Destaque + Brinde IBM
- 🥈 **2º Lugar:** Certificado de Destaque
- 🥉 **3º Lugar:** Menção Honrosa

**Todos os participantes recebem:**

- Certificado de conclusão do bootcamp
- Acesso a materiais complementares
- Networking com equipe IBM

## 📚 Recursos de Apoio

Durante o desafio, você tem acesso a:

- ✅ IBM Bob (ilimitado)
- ✅ Documentação dos laboratórios
- ✅ Internet para pesquisa
- ✅ Instrutores para dúvidas pontuais
- ✅ Materiais de referência

## ⏱️ Gestão do Tempo

O desafio é dividido em 4 fases principais:

1. **Fase 1:** Análise Inicial
2. **Fase 2:** Documentação com IBM Bob
3. **Fase 3:** Análise de Modernização
4. **Fase 4:** Apresentação dos Resultados

## 🎓 Aprendizados Esperados

Ao completar este desafio, você terá:

- ✅ Experiência prática com análise de aplicações reais
- ✅ Domínio do IBM Bob para análise e documentação
- ✅ Capacidade de propor modernizações viáveis
- ✅ Habilidade de trabalhar em equipe sob pressão
- ✅ Experiência em apresentar resultados técnicos

---

**Boa sorte e bom desafio! 🚀**

_Lembre-se: O objetivo não é ter a solução perfeita, mas demonstrar raciocínio técnico, uso efetivo do IBM Bob e capacidade de propor soluções viáveis._

_Desenvolvido para o Bootcamp | Powered by IBM Bob_
