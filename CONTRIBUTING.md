# 🤝 Guia de Contribuição

Obrigado por considerar contribuir com o **Planilha Florestal Analytics**! Este projeto é feito pela comunidade florestal, para a comunidade florestal. 🌲

## 📋 Índice

- [Código de Conduta](#-código-de-conduta)
- [Como Posso Contribuir?](#-como-posso-contribuir)
- [Reportando Bugs](#-reportando-bugs)
- [Sugerindo Melhorias](#-sugerindo-melhorias)
- [Contribuindo com Código](#-contribuindo-com-código)
- [Guia de Estilo](#-guia-de-estilo)
- [Processo de Pull Request](#-processo-de-pull-request)

---

## 📜 Código de Conduta

Este projeto adota um código de conduta baseado em respeito e colaboração:

- ✅ Seja respeitoso e inclusivo
- ✅ Aceite críticas construtivas
- ✅ Foque no que é melhor para a comunidade
- ✅ Mostre empatia com outros membros
- ❌ Não tolere assédio ou comportamento inadequado

---

## 🎯 Como Posso Contribuir?

Existem várias formas de contribuir, mesmo sem escrever código:

### 1. 🐛 Reportar Bugs
Encontrou um erro? Ajude-nos a melhorar reportando!

### 2. 💡 Sugerir Features
Tem uma ideia para melhorar a ferramenta? Compartilhe!

### 3. 📝 Melhorar Documentação
Documentação clara é essencial. Corrija erros, adicione exemplos, traduza.

### 4. 💻 Contribuir com Código
Implemente novas funcionalidades ou corrija bugs existentes.

### 5. 🧪 Testar
Use a ferramenta e reporte sua experiência.

### 6. 🌐 Traduzir
Ajude a tornar a ferramenta acessível em outros idiomas.

---

## 🐛 Reportando Bugs

Antes de reportar um bug:

1. **Verifique** se não é uma duplicata nas [issues existentes](https://github.com/higuchip/planilha-florestal-analytics/issues)
2. **Teste** na versão mais recente
3. **Colete** informações sobre o problema

### Template de Bug Report

```markdown
**Descrição do Bug**
Uma descrição clara e concisa do problema.

**Como Reproduzir**
Passos para reproduzir o comportamento:
1. Acesse '...'
2. Clique em '...'
3. Role até '...'
4. Veja o erro

**Comportamento Esperado**
O que deveria acontecer.

**Screenshots**
Se aplicável, adicione screenshots.

**Ambiente:**
 - OS: [ex: Windows 10, macOS 13, Ubuntu 22.04]
 - Navegador: [ex: Chrome 120, Firefox 121]
 - Versão: [ex: 1.0.0]

**Dados de Teste**
Se possível, anexe um CSV de exemplo que causa o problema.

**Contexto Adicional**
Qualquer outra informação relevante.
```

---

## 💡 Sugerindo Melhorias

### Template de Feature Request

```markdown
**O problema que esta feature resolveria**
Uma descrição clara do problema.

**Solução proposta**
Descrição de como você gostaria que funcionasse.

**Alternativas consideradas**
Outras abordagens que você considerou.

**Contexto adicional**
Screenshots, mockups, ou exemplos de outras ferramentas.

**Benefícios para a comunidade**
Como isso ajudaria outros usuários?
```

---

## 💻 Contribuindo com Código

### Setup do Ambiente Local

```bash
# 1. Fork o repositório no GitHub

# 2. Clone seu fork
git clone https://github.com/SEU-USUARIO/planilha-florestal-analytics.git
cd planilha-florestal-analytics

# 3. Adicione o repositório original como upstream
git remote add upstream https://github.com/higuchip/planilha-florestal-analytics.git

# 4. Crie um branch para sua feature
git checkout -b feature/minha-feature

# 5. Abra o index.html no navegador
# A aplicação roda completamente no client-side, sem necessidade de servidor
```

### Áreas Prioritárias

Contribuições são especialmente bem-vindas em:

- [ ] **Validação de dados**: Melhorar detecção de erros em CSVs
- [ ] **Novas visualizações**: Gráficos adicionais para análises
- [ ] **Performance**: Otimizar processamento de grandes datasets
- [ ] **Acessibilidade**: Melhorar compatibilidade com leitores de tela
- [ ] **Testes**: Criar suite de testes automatizados
- [ ] **Documentação**: Expandir tutoriais e exemplos

---

## 📐 Guia de Estilo

### JavaScript

```javascript
// ✅ BOM
function calcularIVI(especie) {
    const densidade = calcularDensidadeRelativa(especie);
    const frequencia = calcularFrequenciaRelativa(especie);
    const dominancia = calcularDominanciaRelativa(especie);
    
    return densidade + frequencia + dominancia;
}

// ❌ EVITAR
function calc_ivi(e){const d=calcDR(e);const f=calcFR(e);const dom=calcDoR(e);return d+f+dom;}
```

**Convenções:**
- Use `camelCase` para variáveis e funções
- Use nomes descritivos
- Comente código complexo
- Mantenha funções pequenas e focadas
- Evite variáveis globais

### CSS

```css
/* ✅ BOM */
.fitossociologia-tabela {
    width: 100%;
    border-collapse: collapse;
}

.fitossociologia-tabela__header {
    background-color: #2c5f2d;
    color: white;
}

/* ❌ EVITAR */
.ft{w:100%;bc:collapse}
```

**Convenções:**
- Use BEM ou classes descritivas
- Agrupe propriedades relacionadas
- Comente seções principais
- Mobile-first approach

### Commits

Use [Conventional Commits](https://www.conventionalcommits.org/):

```bash
# Tipos de commit
feat: Nova funcionalidade
fix: Correção de bug
docs: Documentação
style: Formatação, ponto-e-vírgula
refactor: Refatoração de código
test: Adição de testes
chore: Tarefas de manutenção

# Exemplos
git commit -m "feat: adicionar análise de regeneração natural"
git commit -m "fix: corrigir cálculo de IVI para espécies raras"
git commit -m "docs: atualizar README com novos modelos de biomassa"
```

---

## 🔄 Processo de Pull Request

### Checklist Antes de Submeter

- [ ] Código segue o guia de estilo
- [ ] Testado em Chrome, Firefox e Safari
- [ ] Testado em dispositivos móveis
- [ ] Comentários adicionados em código complexo
- [ ] Documentação atualizada (se necessário)
- [ ] Commit messages seguem padrão
- [ ] Branch está atualizado com `main`

### Passos para PR

1. **Atualize seu branch**
```bash
git fetch upstream
git rebase upstream/main
```

2. **Push para seu fork**
```bash
git push origin feature/minha-feature
```

3. **Crie o Pull Request**
- Vá até o repositório no GitHub
- Clique em "New Pull Request"
- Selecione seu branch
- Preencha a descrição detalhadamente

### Template de PR

```markdown
## Descrição
Resumo claro das mudanças.

## Tipo de Mudança
- [ ] Bug fix (mudança que corrige um problema)
- [ ] Nova feature (mudança que adiciona funcionalidade)
- [ ] Breaking change (mudança que quebra compatibilidade)
- [ ] Documentação

## Como Foi Testado?
Descreva os testes realizados.

## Screenshots (se aplicável)
Adicione screenshots de novas features.

## Checklist
- [ ] Código segue guia de estilo
- [ ] Comentários adicionados
- [ ] Documentação atualizada
- [ ] Testado em múltiplos navegadores
- [ ] Testado com dados reais
```

### Processo de Review

1. Mantenedores revisarão seu PR
2. Podem solicitar mudanças
3. Faça as alterações solicitadas
4. Push no mesmo branch (PR atualiza automaticamente)
5. Aguarde aprovação
6. Merge será feito por um mantenedor

---

## 🧪 Testando Mudanças

### Dados de Teste

Use estes dados para testar:

```csv
Parcela,ID Árvore,Espécie,CAP,Altura
P01,001,Araucaria angustifolia,157.0,25.5
P01,002,Ilex paraguariensis,62.8,12.3
P01,003,Ocotea pulchella,94.2,18.7
P02,004,Araucaria angustifolia,188.5,28.2
P02,005,Matayba elaeagnoides,45.6,9.5
P02,006,Cupania vernalis,51.2,11.8
```

### Cenários de Teste

- [ ] Importação de CSV válido
- [ ] CSV com erros (colunas faltando, valores inválidos)
- [ ] Diferentes tamanhos de parcela
- [ ] Datasets pequenos (<10 árvores)
- [ ] Datasets grandes (>1000 árvores)
- [ ] Espécies com caracteres especiais
- [ ] Troncos múltiplos
- [ ] Dados com valores faltantes

---

## 🌟 Reconhecimento de Contribuidores

Contribuidores serão:
- Listados no README
- Mencionados em release notes
- Creditados em publicações científicas que usem o software (quando aplicável)

---

## 📞 Dúvidas?

- 📧 Email: [higuchip@gmail.com](mailto:higuchip@gmail.com)
- 🐛 [Abra uma issue](https://github.com/higuchip/planilha-florestal-analytics/issues)
- 💬 Discussões: Use a aba "Discussions" do GitHub

---

<div align="center">

**Obrigado por contribuir! 🌲💚**

Cada contribuição, por menor que seja, ajuda a construir uma ferramenta melhor para toda a comunidade florestal.

</div>
