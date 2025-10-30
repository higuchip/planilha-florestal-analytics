# 🤝 Guia de Contribuição

Obrigado por considerar contribuir com o **Planilha Florestal Analytics**! Este projeto é feito pela comunidade florestal, para a comunidade florestal. 🌲

Esta ferramenta complementa o [Planilha Florestal App](https://github.com/higuchip/inventario_app) (PWA para coleta de dados em campo) e oferece análises fitossociológicas completas de forma gratuita e open-source.

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

### Estrutura do Código

**Arquivo Principal:** `index.html` (aplicação single-page)

**Seções Principais do Código:**

```
📦 index.html
├── 🎨 CSS (variáveis, estilos, responsividade)
├── 📊 HTML (estrutura, tabs, formulários)
└── ⚙️ JavaScript
    ├── Variáveis Globais
    │   ├── data[] - dados processados
    │   ├── originalData[] - dados originais
    │   ├── speciesCorrections{} - correções aplicadas
    │   ├── processedData{} - resultados das análises
    │   └── plotSizeM2 - tamanho da parcela
    │
    ├── Configuração e Upload
    │   ├── enableUpload() - habilita upload após config
    │   ├── processFile() - processa CSV com Papa Parse
    │   └── prepareData() - valida e limpa dados
    │
    ├── Validação (Aba 1)
    │   ├── populateSpeciesTable() - lista espécies
    │   ├── applySpeciesCorrections() - aplica correções
    │   ├── mergeSelectedSpecies() - mescla espécies
    │   ├── detectOutliers() - IQR e Z-Score
    │   ├── editOutlierValues() - edita medições
    │   └── exportCorrectedCSV() - exporta dados validados
    │
    ├── Análises Fitossociológicas
    │   ├── calculatePhytosociology() - DA, DR, FA, FR, DoA, DoR, IVI
    │   ├── calculateDiversity() - Shannon, Pielou, Simpson
    │   ├── calculateAccumulationCurve() - 100 permutações
    │   ├── calculateRichnessEstimators() - Chao, Jackknife, Bootstrap
    │   └── calculateSpatialPattern() - Índice de Morisita
    │
    ├── Visualizações
    │   ├── createStructureHistograms() - DAP e Altura
    │   ├── createPhytoTable() - tabela fitossociológica
    │   ├── createAccumulationChart() - Chart.js
    │   ├── createDiversityChart() - gráfico de barras
    │   └── createSpatialChart() - Morisita
    │
    ├── Biomassa
    │   ├── modelos{} - 4 modelos alométricos
    │   │   ├── pantropicalModel (Chave 2014)
    │   │   ├── chambers2001 (Amazônia)
    │   │   ├── ziemmer2016 (Xaxins)
    │   │   └── trautenmuller2021 (FOM)
    │   ├── executeBiomassCalculation()
    │   └── exportBiomassData()
    │
    └── Exportação
        ├── exportTableToCSV() - tabela fitossociológica
        ├── exportChart() - gráficos em PNG
        └── exportCorrectedCSV() - dados validados
```

**Bibliotecas Externas:**
- `Chart.js` - Gráficos interativos
- `Papa Parse` - Processamento CSV
- `html2canvas` - Exportação de gráficos (planejado)

**Padrões de Código:**
- Vanilla JavaScript (sem frameworks)
- Processamento 100% client-side
- CSS Grid/Flexbox para layout
- Sistema de tabs para navegação

### Adicionando Novos Modelos de Biomassa

Se você deseja contribuir com um novo modelo alométrico:

```javascript
// 1. Adicione o modelo ao objeto 'modelos' no código
novoModelo: {
    description: "Descrição do modelo",
    parametrization: "Região/Formação florestal",
    requiredVariables: ["DAP", "H"], // ou apenas ["DAP"]
    requiredVariablesInfo: {
        DAP: "DAP em cm",
        H: "altura total da árvore em m"
    },
    reference: "Citação bibliográfica completa",
    formula: calculateNovoModeloBiomass, // função de cálculo
    report: (totalBiomass) => `Texto do relatório: ${totalBiomass.toFixed(2)} toneladas`,
    outputColumnName: "AGB"
}

// 2. Crie a função de cálculo
function calculateNovoModeloBiomass(row) {
    let DAP = parseFloat(String(row["DAP"]).replace(",", "."));
    let H = parseFloat(String(row["H"]).replace(",", "."));
    
    // Sua equação alométrica aqui
    // Retornar biomassa em TONELADAS (kg/1000)
    let result = /* sua fórmula */ / 1000;
    
    return parseFloat(result.toFixed(4));
}

// 3. Adicione opção no select HTML
<option value="novoModelo">Nome do Modelo - Região</option>
```

**Checklist para novos modelos:**
- [ ] Equação validada cientificamente
- [ ] Referência bibliográfica completa
- [ ] Unidades corretas (resultado em toneladas)
- [ ] Tratamento de valores inválidos
- [ ] Documentação da região/formação aplicável
- [ ] Testes com dados reais
- [ ] Exemplo no PR

### Áreas Prioritárias

Contribuições são especialmente bem-vindas em:

- [ ] **Validação de dados**: Melhorar detecção de erros em CSVs e correção botânica
- [ ] **Detecção de outliers**: Aprimorar algoritmos de detecção (IQR, Z-Score)
- [ ] **Modelos de biomassa**: Adicionar novos modelos alométricos regionais
- [ ] **Estimadores de riqueza**: Implementar novos estimadores (ACE, ICE)
- [ ] **Visualizações**: Criar gráficos adicionais e mapas interativos com coordenadas GPS
- [ ] **Análise temporal**: Comparação entre inventários de diferentes anos
- [ ] **Performance**: Otimizar processamento de grandes datasets (>10.000 árvores)
- [ ] **Acessibilidade**: Melhorar compatibilidade com leitores de tela
- [ ] **Testes**: Criar suite de testes automatizados
- [ ] **Documentação**: Expandir tutoriais e criar vídeos explicativos
- [ ] **Exportação**: Adicionar formatos GIS (Shapefile, GeoJSON)
- [ ] **Integração**: API Flora e Funga do Brasil para validação taxonômica

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

Use estes dados para testar (formato Planilha Florestal App):

```csv
Parcela;ID Árvore;Espécie;CAP;Tronco Múltiplo;CAPs Individuais;Altura;Latitude;Longitude;Data de Registro;Observação
1;1469;Ilex dumosa;85,8;Não;;7;-27,79615;-50,332249;25/09/2025, 08:35:33;Coletado
1;1504;Myrcia splendens;17,7;Não;;6;-27,791664;-50,346441;25/09/2025, 08:35:33;
1;1507;Myrsine umbellata;31,6;Não;;6;-27,791664;-50,346441;25/09/2025, 08:35:33;
1;1509;Myrsine umbellata;15,8;Não;;5;-27,79615;-50,332249;25/09/2025, 08:35:33;
1;1512;Myrcia palustris;26,7;Não;;7;-27,791664;-50,346441;25/09/2025, 08:35:33;
1;1518;Myrsine umbellata;18,4;Não;;6;-27,791664;-50,346441;25/09/2025, 08:35:33;
2;1520;Araucaria angustifolia;157,0;Não;;25,5;-27,79615;-50,332249;25/09/2025, 09:12:15;
2;1521;Ocotea pulchella;94,2;Não;;18,7;-27,791664;-50,346441;25/09/2025, 09:15:22;
```

**Observações importantes:**
- Separador: ponto-e-vírgula (;)
- Decimal: vírgula (,)
- Codificação: UTF-8 com BOM

### Cenários de Teste

**Configuração e Import:**
- [ ] Configuração de tamanho de parcela (100, 400, 500, 600, 1000 m²)
- [ ] Importação de CSV válido (formato Planilha Florestal App)
- [ ] CSV com erros (colunas faltando, valores inválidos)
- [ ] Diferentes separadores (ponto-e-vírgula vs vírgula)
- [ ] Diferentes decimais (vírgula vs ponto)

**Validação de Dados:**
- [ ] Correção de nomes de espécies
- [ ] Mesclagem de espécies duplicadas
- [ ] Detecção de outliers (IQR e Z-Score)
- [ ] Edição de valores de outliers (CAP, Altura)
- [ ] Remoção de outliers
- [ ] Exportação de CSV corrigido

**Análises Estruturais:**
- [ ] Histogramas de DAP com regra de Sturges
- [ ] Histogramas de Altura (quando disponível)
- [ ] Datasets pequenos (<10 árvores)
- [ ] Datasets grandes (>1000 árvores)
- [ ] Dados sem altura

**Fitossociologia:**
- [ ] Cálculo de IVI (Densidade, Frequência, Dominância)
- [ ] Exportação de tabela fitossociológica
- [ ] Espécies com frequência baixa
- [ ] Espécies com caracteres especiais nos nomes

**Diversidade e Acumulação:**
- [ ] Índices de Shannon, Pielou, Simpson
- [ ] Curva de acumulação com 100 permutações
- [ ] Estimadores de riqueza (Chao, Jackknife, Bootstrap)
- [ ] Interpretação de suficiência amostral

**Padrão Espacial:**
- [ ] Índice de Morisita para top 5 espécies
- [ ] Detecção de padrão agregado/uniforme/aleatório
- [ ] Cálculo de limites de agregação/uniformidade

**Biomassa:**
- [ ] Modelo Pantropical (Chave et al., 2014)
- [ ] Modelo Amazônico (Chambers et al., 2001)
- [ ] Modelo Xaxins (Ziemmer et al., 2016)
- [ ] Modelo FOM (Trautenmüller et al., 2021)
- [ ] Tratamento de árvores sem altura (exclusão vs imputação)
- [ ] Exportação de CSV com biomassa
- [ ] Estatísticas por espécie
- [ ] Identificação de espécies que representam 80% da biomassa

**Casos Especiais:**
- [ ] Troncos múltiplos
- [ ] Dados com valores faltantes (Altura, Coordenadas)
- [ ] Parcelas com número variável de árvores
- [ ] Uma única parcela
- [ ] Muitas parcelas (>50)

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
