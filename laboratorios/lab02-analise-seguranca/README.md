# 🔒 Laboratório 2 - Análise de Segurança da Aplicação

## 📋 Informações do Laboratório

- **Duração:** 45 minutos
- **Nível:** Intermediário
- **Objetivo:** Realizar análise completa de segurança da aplicação usando IBM Bob e gerar relatório detalhado de vulnerabilidades

## 🎯 Objetivos de Aprendizagem

Ao final deste laboratório, você será capaz de:

- ✅ Utilizar o IBM Bob para análise de segurança automatizada
- ✅ Identificar vulnerabilidades comuns em aplicações Java
- ✅ Classificar problemas de segurança por gravidade
- ✅ Gerar relatórios abrangentes de segurança
- ✅ Propor correções para vulnerabilidades encontradas
- ✅ Priorizar ações de remediação

## 📦 Pré-requisitos

Antes de iniciar, certifique-se de ter:

- ☑️ Laboratório 1 concluído com sucesso
- ☑️ Aplicação BobLab rodando no WAS Base
- ☑️ IBM Bob configurado e acessível
- ☑️ Código-fonte da aplicação disponível

## 🔍 O que é Análise de Segurança?

A análise de segurança é um processo sistemático de identificação de vulnerabilidades, falhas e pontos fracos em aplicações de software. Com o IBM Bob, esse processo é automatizado e acelerado através de IA.

### Tipos de Vulnerabilidades Comuns

1. **Injeção (SQL, LDAP, etc.)**
2. **Autenticação e Sessão Quebradas**
3. **Exposição de Dados Sensíveis**
4. **XML External Entities (XXE)**
5. **Controle de Acesso Quebrado**
6. **Configuração de Segurança Incorreta**
7. **Cross-Site Scripting (XSS)**
8. **Desserialização Insegura**
9. **Componentes com Vulnerabilidades Conhecidas**
10. **Logging e Monitoramento Insuficientes**

## 🚀 Passo a Passo

### Passo 1: Preparar o Ambiente (5 min)

1. Certifique-se de que a aplicação do Lab 1 está rodando
2. Tenha o código-fonte acessível
3. Abra o IBM Bob

### Passo 2: Executar Análise de Segurança com IBM Bob (20 min)

1. Abra o IBM Bob
2. Navegue até o diretório do projeto BobLab
3. Copie e cole o prompt abaixo (também disponível em [prompt-bob.txt](./prompt-bob.txt))

**Prompt para o IBM Bob:**

```
VALIDAÇÃO DE SEGURANÇA DA APLICAÇÃO

Analise o código-fonte da aplicação BobLab em busca de vulnerabilidades de segurança.

Crie um relatório abrangente em português (pt-BR) incluindo:

1. Lista completa de todos os problemas de segurança encontrados

2. Classificação de gravidade para cada problema:
   - Crítico: Vulnerabilidades que podem ser exploradas remotamente sem autenticação
   - Alto: Vulnerabilidades que requerem acesso autenticado ou local
   - Médio: Vulnerabilidades que requerem condições específicas
   - Baixo: Problemas de segurança menores ou boas práticas não seguidas

3. Para cada vulnerabilidade, detalhe:
   - Descrição clara do problema
   - Impacto potencial no negócio e nos dados
   - Localização exata no código (arquivo, classe, método e linha)
   - Código vulnerável (trecho específico)
   - Correção recomendada com exemplo de código
   - Referências (OWASP, CWE, CVE quando aplicável)

4. Ordem de prioridade para as correções baseada em:
   - Gravidade da vulnerabilidade
   - Facilidade de exploração
   - Impacto no negócio
   - Esforço de correção

5. Resumo executivo contendo:
   - Total de vulnerabilidades por categoria de gravidade
   - Risco geral da aplicação (Crítico/Alto/Médio/Baixo)
   - Top 5 vulnerabilidades mais críticas
   - Recomendações gerais de segurança
   - Estimativa de esforço para correção

6. Plano de ação com:
   - Correções imediatas (0-7 dias)
   - Correções de curto prazo (1-4 semanas)
   - Melhorias de médio prazo (1-3 meses)

Formato: Documento estruturado em markdown com seções claras e exemplos de código.
```

### Passo 3: Analisar o Relatório Gerado (10 min)

Após o IBM Bob gerar o relatório, analise cuidadosamente cada seção:

#### 📊 Estrutura Esperada do Relatório

```markdown
# Relatório de Análise de Segurança - BobLab

## 1. Resumo Executivo

- Risco Geral
- Total de Vulnerabilidades
- Distribuição por Gravidade

## 2. Vulnerabilidades Críticas

- Detalhes de cada vulnerabilidade crítica

## 3. Vulnerabilidades Altas

- Detalhes de cada vulnerabilidade alta

## 4. Vulnerabilidades Médias

- Detalhes de cada vulnerabilidade média

## 5. Vulnerabilidades Baixas

- Detalhes de cada vulnerabilidade baixa

## 6. Plano de Correção Priorizado

- Ordem de implementação

## 7. Recomendações Gerais

- Boas práticas de segurança
```

#### 🔍 Pontos Importantes para Verificar

**1. Completude do Relatório**

- Todas as vulnerabilidades foram identificadas?
- Cada vulnerabilidade tem classificação de gravidade?
- Há exemplos de código para correção?

**2. Clareza das Informações**

- As descrições são compreensíveis?
- A localização no código está precisa?
- O impacto está bem explicado?

**3. Viabilidade das Correções**

- As correções propostas são práticas?
- Há exemplos de código funcionais?
- O esforço estimado é realista?

### Passo 4: Documentar Vulnerabilidades Encontradas (5 min)

Crie uma planilha ou documento com as principais vulnerabilidades:

| ID   | Gravidade | Vulnerabilidade | Arquivo      | Linha | Status   |
| ---- | --------- | --------------- | ------------ | ----- | -------- |
| V001 | Crítico   | SQL Injection   | UserDAO.java | 45    | Pendente |
| V002 | Alto      | XSS             | index.jsp    | 23    | Pendente |
| V003 | Médio     | Senha hardcoded | Config.java  | 12    | Pendente |

### Passo 5: Priorizar Correções (5 min)

Com base no relatório, defina a ordem de correção:

**Prioridade 1 - Imediata (0-7 dias):**

- Vulnerabilidades críticas
- Exposição de dados sensíveis
- Falhas de autenticação

**Prioridade 2 - Curto Prazo (1-4 semanas):**

- Vulnerabilidades altas
- Problemas de configuração
- Validação de entrada

**Prioridade 3 - Médio Prazo (1-3 meses):**

- Vulnerabilidades médias e baixas
- Melhorias de código
- Atualização de dependências

## ✅ Checklist de Validação

Marque cada item conforme completa:

- [ ] Análise de segurança executada com IBM Bob
- [ ] Relatório completo gerado
- [ ] Todas as vulnerabilidades classificadas
- [ ] Impacto de cada vulnerabilidade documentado
- [ ] Correções propostas para cada problema
- [ ] Plano de priorização criado
- [ ] Resumo executivo revisado
- [ ] Documentação das vulnerabilidades organizada
- [ ] Próximos passos definidos

## 🎓 Conceitos Aprendidos

### 1. Análise de Segurança Automatizada

- Como usar IA para identificar vulnerabilidades
- Interpretação de relatórios de segurança
- Classificação de riscos

### 2. Vulnerabilidades Comuns em Java

- OWASP Top 10
- Padrões de código inseguro
- Boas práticas de segurança

### 3. Remediação de Vulnerabilidades

- Priorização baseada em risco
- Técnicas de correção
- Validação de correções

### 4. Segurança no Ciclo de Desenvolvimento

- Shift-left security
- DevSecOps
- Análise contínua

## 📊 Exemplo de Vulnerabilidade e Correção

### ❌ Código Vulnerável (SQL Injection)

```java
public User getUserByUsername(String username) {
    String query = "SELECT * FROM users WHERE username = '" + username + "'";
    // Vulnerável a SQL Injection
    return executeQuery(query);
}
```

**Problema:** Concatenação direta de entrada do usuário na query SQL.

**Impacto:** Atacante pode executar comandos SQL arbitrários, acessar dados sensíveis ou modificar o banco de dados.

### ✅ Código Corrigido (Prepared Statement)

```java
public User getUserByUsername(String username) {
    String query = "SELECT * FROM users WHERE username = ?";
    PreparedStatement stmt = connection.prepareStatement(query);
    stmt.setString(1, username);
    // Protegido contra SQL Injection
    return executeQuery(stmt);
}
```

**Correção:** Uso de PreparedStatement com parâmetros parametrizados.

**Benefício:** Entrada do usuário é tratada como dado, não como código SQL.

## 🐛 Troubleshooting

### Problema: IBM Bob não encontra vulnerabilidades

**Possíveis causas:**

1. Código muito simples sem vulnerabilidades reais
2. Análise não abrangente o suficiente
3. Prompt não específico

**Soluções:**

- Refine o prompt para ser mais específico
- Peça análise de categorias específicas (OWASP Top 10)
- Solicite análise de dependências também

### Problema: Relatório muito genérico

**Solução:**

```
Refine o prompt pedindo:
- Exemplos de código específicos
- Localização exata (arquivo:linha)
- Trechos de código vulnerável
- Exemplos de correção funcionais
```

### Problema: Muitas vulnerabilidades de baixa prioridade

**Abordagem:**

1. Foque primeiro nas críticas e altas
2. Agrupe vulnerabilidades similares
3. Corrija padrões, não instâncias individuais

## 📈 Métricas de Segurança

Após a análise, documente as seguintes métricas:

### Antes da Correção

```
Total de Vulnerabilidades: XX
├── Críticas: X
├── Altas: X
├── Médias: X
└── Baixas: X

Risco Geral: [Crítico/Alto/Médio/Baixo]
Score de Segurança: X/100
```

### Meta Após Correção

```
Total de Vulnerabilidades: 0 (Críticas e Altas)
├── Críticas: 0
├── Altas: 0
├── Médias: ≤ 5
└── Baixas: ≤ 10

Risco Geral: Baixo
Score de Segurança: ≥ 85/100
```

## 🎯 Próximos Passos

Parabéns! Você completou o Laboratório 2. 🎉

Agora você está pronto para:

- **Laboratório 3:** Migração para Liberty e Java 21
- Aplicar correções de segurança durante a migração
- Modernizar a aplicação mantendo segurança

## 📚 Recursos Adicionais

### Segurança em Java

- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [OWASP Java Security Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Java_Security_Cheat_Sheet.html)
- [CWE - Common Weakness Enumeration](https://cwe.mitre.org/)

### Ferramentas de Análise

- [SonarQube](https://www.sonarqube.org/)
- [OWASP Dependency-Check](https://owasp.org/www-project-dependency-check/)
- [SpotBugs](https://spotbugs.github.io/)

### Boas Práticas

- [Secure Coding Guidelines for Java](https://www.oracle.com/java/technologies/javase/seccodeguide.html)
- [IBM Security Best Practices](https://www.ibm.com/security)

## 💡 Dicas Profissionais

1. **Análise Regular** - Execute análise de segurança em cada sprint
2. **Automatize** - Integre análise no pipeline CI/CD
3. **Eduque a Equipe** - Compartilhe vulnerabilidades encontradas
4. **Priorize Corretamente** - Nem tudo precisa ser corrigido imediatamente
5. **Documente Decisões** - Registre por que certas vulnerabilidades foram aceitas
6. **Teste as Correções** - Valide que a correção não quebra funcionalidades
7. **Mantenha Atualizado** - Acompanhe novas vulnerabilidades (CVEs)

## 🔐 Checklist de Segurança para Produção

Antes de colocar em produção, verifique:

- [ ] Todas as vulnerabilidades críticas corrigidas
- [ ] Todas as vulnerabilidades altas corrigidas
- [ ] Senhas e credenciais não estão hardcoded
- [ ] Dados sensíveis são criptografados
- [ ] Validação de entrada implementada
- [ ] Logs de segurança configurados
- [ ] HTTPS habilitado
- [ ] Headers de segurança configurados
- [ ] Dependências atualizadas
- [ ] Testes de segurança executados

---

**Tempo estimado de conclusão:** 45 minutos  
**Dificuldade:** ⭐⭐⭐☆☆ (Intermediário)  
**Pré-requisito para:** Laboratório 3

_Desenvolvido para o Bootcamp | Powered by IBM Bob_
