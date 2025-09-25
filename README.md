# 🌲 Planilha Florestal Analytics

[![Em Testes](https://img.shields.io/badge/Status-Em%20Testes-orange.svg)](https://github.com/higuchip/planilha-florestal-analytics)
[![GitHub Pages](https://img.shields.io/badge/GitHub-Pages-blue.svg)](https://higuchip.github.io/planilha-florestal-analytics/)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26.svg?logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E.svg?logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

**Ferramenta de análise fitossociológica para dados de inventário florestal**

Companheiro do [Planilha Florestal App](https://github.com/higuchip/inventario_app) - enquanto o PWA serve para coleta de dados no campo, esta ferramenta serve para analisar estes dados coletados.

## 📊 Demonstração

🔗 **[Acesse a aplicação](https://higuchip.github.io/planilha-florestal-analytics/)**


## ✨ Funcionalidades

### 📈 Análises Disponíveis
- **Parâmetros Fitossociológicos**: Densidade, Frequência, Dominância e IVI
- **Índices de Diversidade**: Shannon, Pielou, Simpson, Riqueza
- **Estrutura Florestal**: Histogramas de DAP e Altura com estatísticas
- **Curva de Acumulação**: Com estimadores de riqueza (Chao, Jackknife, Bootstrap)
- **Padrão Espacial**: Índice de Morisita para as principais espécies
- **Exportação**: Tabelas em formato CSV

### 🔧 Recursos Técnicos
- **Interface Responsiva**: Funciona em desktop, tablet e mobile
- **Configuração Flexível**: Tamanhos de parcela personalizáveis
- **Gráficos Interativos**: Powered by Chart.js
- **Importação CSV**: Compatível com dados do Planilha Florestal App
- **100% Client-side**: Não requer servidor, funciona offline após carregamento

## 🚀 Como Usar

### 1. **Configure a Área Amostral**
- Defina o tamanho das parcelas (m²)
- Presets disponíveis: 100, 400, 500, 600, 1000 m²

### 2. **Importe seus Dados**
- Faça upload do arquivo CSV exportado do Planilha Florestal App
- Ou use CSV compatível com a estrutura esperada

### 3. **Analise os Resultados**
- **Resumo**: Visão geral dos dados e estatísticas
- **Estrutura**: Histogramas de DAP e altura
- **Fitossociologia**: Tabela completa com todos os parâmetros
- **Curva de Acumulação**: Análise da suficiência amostral
- **Diversidade**: Índices e interpretações
- **Padrão Espacial**: Distribuição das espécies

### 4. **Exporte os Resultados**
- Tabelas fitossociológicas em CSV
- Gráficos em PNG
- Dados prontos para relatórios

## 🗂️ Estrutura de Dados CSV

O arquivo CSV deve conter as seguintes colunas:

| Coluna | Descrição | Exemplo |
|--------|-----------|---------|
| `Parcela` | Identificador da unidade amostral | P01 |
| `ID Árvore` | Identificador único da árvore | 001 |
| `Espécie` | Nome da espécie | *Araucaria angustifolia* |
| `CAP` | Circunferência à altura do peito (cm) | 95.5 |
| `Altura` | Altura da árvore em metros (opcional) | 15.2 |
| `Latitude` | Coordenada GPS (opcional) | -25.12345 |
| `Longitude` | Coordenada GPS (opcional) | -50.67890 |
| `Tronco Múltiplo` | Sim/Não | Não |
| `CAPs Individuais` | Lista de CAPs se tronco múltiplo | 30;25;40 |

## 🔄 Integração com Planilha Florestal App

Esta ferramenta foi desenvolvida para complementar o [Planilha Florestal App](https://github.com/higuchip/inventario_app):

1. **Campo**: Use o PWA para coleta de dados de inventário
2. **Escritório**: Exporte os dados em CSV
3. **Análise**: Importe aqui para análises fitossociológicas completas
4. **Relatório**: Exporte resultados para documentos finais

## 🛠️ Tecnologias Utilizadas

- **HTML5**: Estrutura e semântica
- **CSS3**: Estilização responsiva com CSS Grid/Flexbox
- **Vanilla JavaScript**: Lógica da aplicação
- **Chart.js**: Gráficos interativos
- **Papa Parse**: Processamento de arquivos CSV
- **HTML2Canvas**: Exportação de gráficos

## ⚠️ Status do Projeto

**🚧 EM FASE DE TESTES**

Este projeto está em desenvolvimento ativo. Características importantes:

- ✅ Funcionalidades principais implementadas
- ✅ Interface responsiva
- ✅ Análises estatísticas validadas
- ⚠️ Pode conter bugs ou comportamentos inesperados
- ⚠️ Recomenda-se validar resultados críticos
- ⚠️ Use por sua conta e risco

## 🎯 Público-Alvo

- **Engenheiros Florestais**
- **Técnicos em Florestas**
- **Estudantes de Engenharia Florestal**
- **Pesquisadores em Ecologia Florestal**
- **Consultores Ambientais**

## 📋 Roadmap

- [ ] Explorar novas análises e visualizações
- [ ] Criar visualização de mapas com coordenadas
- [ ] Veriricar erros e bugs
- [ ] Criar documentação técnica detalhada

## 🤝 Contribuições

Contribuições são bem-vindas! Como o projeto está em fase de testes:

1. **Issues**: Reporte bugs ou sugira melhorias
2. **Pull Requests**: Correções e novas funcionalidades
3. **Feedback**: Use e compartilhe sua experiência
4. **Documentação**: Ajude a melhorar este README

### Como Contribuir

1. Fork este repositório
2. Crie um branch para sua feature (`git checkout -b feature/nova-funcionalidade`)
3. Commit suas mudanças (`git commit -am 'Adiciona nova funcionalidade'`)
4. Push para o branch (`git push origin feature/nova-funcionalidade`)
5. Crie um Pull Request

## 📞 Contato

**Pedro Higuchi**
- 📧 Email: [higuchip@gmail.com](mailto:higuchip@gmail.com)
- 💼 GitHub: [@higuchip](https://github.com/higuchip)

## 📄 Licença
- A definir
---

<div align="center">

**🌲 Planilha Florestal Analytics**

*Desenvolvido para a comunidade florestal brasileira*


[🚀 Experimente Agora](https://higuchip.github.io/planilha-florestal-analytics/) | [🐛 Reporte Bugs](https://github.com/higuchip/planilha-florestal-analytics/issues) | [📖 Documentação](https://github.com/higuchip/planilha-florestal-analytics/wiki)

</div>
