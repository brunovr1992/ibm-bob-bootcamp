# 🚀 Bootcamp - Modernizando Aplicações Java com IBM Bob

## 📋 Informações Gerais

- **Tema:** Modernizando Aplicações Java com o IBM Bob
- **Formato:** Bootcamp prático hands-on

## 🎯 Objetivo

Contextualizar os desenvolvedores sobre o IBM Bob e como utilizá-lo na modernização de aplicações Java através da execução de laboratórios práticos, abordando desde a criação de aplicações legadas até a migração para plataformas modernas como Liberty e Quarkus.

## 📚 Conteúdo do Bootcamp

### Abertura e Boas-vindas

- Apresentação dos instrutores
- Visão geral do bootcamp
- Objetivos de aprendizagem

### Apresentação: O que é o IBM Bob?

**Conteúdo:**

- Introdução ao IBM Bob e suas capacidades
- Desafios da modernização de aplicações Java
- Como o IBM Bob acelera o processo de modernização
- Análise de código, segurança e geração automática
- Demonstração prática ao vivo

### Laboratório 1 - Java 8 com WAS Base

**Objetivo:** Criar uma aplicação Java 8 rodando no WebSphere Application Server Base

**Atividades:**

- Uso do IBM Bob para gerar aplicação completa
- Implementação de sistema de log com timestamp
- Criação de frontend com IBM Carbon UI/UX
- Build Maven e geração de EAR
- Deploy no WAS Base

**Documentação:** [Lab 01 - Guia Completo](./laboratorios/lab01-java8-was-base/README.md)

### Laboratório 2 - Análise de Segurança

**Objetivo:** Validar segurança da aplicação usando IBM Bob

**Atividades:**

- Análise automatizada de vulnerabilidades
- Geração de relatório de segurança completo
- Classificação de problemas por gravidade
- Criação de plano de correção priorizado

**Documentação:** [Lab 02 - Guia Completo](./laboratorios/lab02-analise-seguranca/README.md)

### Laboratório 3 - Migração para Liberty

**Objetivo:** Migrar aplicação para WebSphere Liberty e Java 21

**Atividades:**

- Análise do migration plan
- Migração de Java 8 para Java 21
- Conversão de WAS Base para Liberty
- Configuração do servidor Liberty
- Deploy e validação da aplicação

**Documentação:** [Lab 03 - Guia Completo](./laboratorios/lab03-migracao-liberty/README.md)

### Laboratório 4 - Migração para Quarkus

**Objetivo:** Migrar aplicação e servidor para Quarkus

**Atividades:**

- Conversão de Liberty para Quarkus
- Adaptação do código para o modelo Quarkus
- Configuração do ambiente Quarkus
- Inicialização e validação do servidor

**Documentação:** [Lab 04 - Guia Completo](./laboratorios/lab04-migracao-quarkus/README.md)

### Desafio Prático - Aplicação Real

**Objetivo:** Aplicar conhecimentos adquiridos em uma aplicação real

**Atividades:**

- Análise de aplicação real
- Uso do IBM Bob para documentação automática
- Identificação de pontos de modernização
- Proposta de plano de migração
- Apresentação dos resultados em grupos

**Documentação:** [Desafio Prático - Guia](./desafio-pratico/README.md)

### Encerramento

- Recap dos principais aprendizados
- Próximos passos e recursos adicionais

## 🛠️ Pré-requisitos

### Software Necessário

**Obrigatórios:**

- ☑️ Java Development Kit (JDK) 8, 11, 17 e 21
- ☑️ Apache Maven 3.8+
- ☑️ Git
- ☑️ IBM WebSphere Application Server Base
- ☑️ IBM WebSphere Liberty (instalado em `C:\Softwares\Liberty\wlp`)
- ☑️ Quarkus CLI
- ☑️ IBM Bob (acesso configurado)
- ☑️ Visual Studio Code ou IDE de preferência

**Recomendados:**

- Docker Desktop
- Postman ou similar para testes de API
- Navegador moderno (Chrome, Firefox, Edge)

### Configuração do Ambiente

Consulte o [Checklist de Instalação](./pre-requisitos/checklist-instalacao.md) para instruções detalhadas de configuração.

### 📁 Estrutura do Projeto

```
bob-bootcamp-general/
├── README.md                          # Este arquivo
├── laboratorios/
│   ├── lab01-java8-was-base/
│   │   ├── README.md                  # Guia do laboratório
│   │   └── prompt-bob.txt             # Prompt para IBM Bob
│   ├── lab02-analise-seguranca/
│   │   ├── README.md
│   │   └── prompt-bob.txt
│   ├── lab03-migracao-liberty/
│   │   ├── README.md
│   │   ├── prompt-bob.txt
│   │   └── migration-plan-reference.md
│   └── lab04-migracao-quarkus/
│       ├── README.md
│       └── prompt-bob.txt
├── desafio-pratico/
│   ├── README.md                      # Instruções do desafio
│   └── template-analise.md            # Template de análise
├── pre-requisitos/
│   ├── checklist-instalacao.md        # Checklist de setup
│   └── ambiente-setup.md              # Guia de configuração
└── recursos/
    ├── diagramas/
    │   ├── fluxo-modernizacao.md      # Diagrama de fluxo
    │   └── arquitetura-migracao.md    # Diagrama de arquitetura
    └── referencias/
        └── links-uteis.md             # Links e recursos
```

### 🎓 Objetivos de Aprendizagem

Ao final do bootcamp, os participantes serão capazes de:

1. ✅ Compreender o IBM Bob e suas capacidades de IA
2. ✅ Utilizar o IBM Bob para gerar código Java automaticamente
3. ✅ Realizar análise de segurança em aplicações Java
4. ✅ Migrar aplicações de Java 8 para Java 21
5. ✅ Converter aplicações de WAS Base para Liberty
6. ✅ Migrar aplicações para Quarkus
7. ✅ Documentar aplicações automaticamente com IA
8. ✅ Propor planos de modernização para aplicações legadas

### 📊 Jornada de Modernização

```
┌─────────────────┐
│  Java 8 + WAS   │  ← Ponto de Partida (Lab 1)
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Análise de      │  ← Validação de Segurança (Lab 2)
│ Segurança       │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Java 21 +       │  ← Primeira Modernização (Lab 3)
│ Liberty         │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Java 21 +       │  ← Modernização Completa (Lab 4)
│ Quarkus         │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Aplicação Real  │  ← Desafio Prático
└─────────────────┘
```

## 📞 Suporte

Durante o bootcamp, você terá suporte de:

- **Instrutores:** Disponíveis para dúvidas técnicas
- **Documentação:** Guias detalhados para cada atividade

## 🔗 Recursos Adicionais

- [IBM Bob Documentation](https://www.ibm.com/docs/bob)
- [WebSphere Liberty Docs](https://www.ibm.com/docs/liberty)
- [Quarkus Guides](https://quarkus.io/guides/)
- [Java 21 Release Notes](https://openjdk.org/projects/jdk/21/)
- [IBM Carbon Design System](https://carbondesignsystem.com/)

## 📝 Feedback

Sua opinião é muito importante! Ao final do bootcamp, por favor preencha:

- Formulário de avaliação do evento
- Sugestões de melhoria
- Tópicos de interesse para futuros bootcamps

---

## 🚀 Vamos Começar!

Prepare seu ambiente seguindo o [Checklist de Instalação](./pre-requisitos/checklist-instalacao.md) e aproveite o bootcamp!

**Bom bootcamp e boa modernização! 🎉**

---

_Desenvolvido com ❤️ | Powered by IBM Bob_
