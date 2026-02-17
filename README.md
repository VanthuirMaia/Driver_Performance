# 🚖 Driver Performance Dashboard

> **Uma ferramenta visual e interativa para análise de desempenho de motoristas de aplicativo.**

Este projeto é um dashboard *single-file* (arquivo único) desenvolvido para visualizar, analisar e extrair insights a partir de dados de corridas (focado na plataforma 99, mas adaptável). Ele oferece uma visão clara dos ganhos, eficiência e padrões de trabalho, ajudando o motorista a otimizar sua rotina e aumentar seus lucros.

## ✨ Funcionalidades

O dashboard processa os dados brutos e gera diversas visualizações métricas:

*   **📊 Visão Geral (KPIs):**
    *   **Ganhos Totais**: Receita líquida no período.
    *   **Total de Corridas**: Contagem de viagens realizadas.
    *   **Horas Online**: Tempo total dedicado.
    *   **Ticket Médio**: Valor médio por corrida.
    *   **Ganhos por Hora**: Média de R$/hora.
*   **📅 Análise Temporal:**
    *   **Corridas por Dia da Semana**: Identifique os dias mais movimentados.
    *   **Melhores Dias**: Ranking dos dias com maior faturamento.
*   **🔥 Mapa de Calor (Heatmap):**
    *   Visualize os horários mais quentes (maior volume ou maior ticket) cruzando Dias da Semana x Horas do Dia.
*   **📈 Evolução Mensal:**
    *   Acompanhe o crescimento da receita, ticket médio e volume de corridas mês a mês.
*   **💰 Financeiro (Novo):**
    *   **Lucro Líquido Estimado**: Receita descontando custos operacionais.
    *   **Margem de Lucro**: Porcentagem de ganho real sobre o bruto.
    *   **Custos**: Estimativa de gastos com combustível e manutenção baseada na KM rodada.
*   **💡 Insights Inteligentes:**
    *   Recomendações automáticas sobre "Horários de Ouro", comparação de eficiência e alertas sobre tendências de queda.
*   **🔎 Filtros Interativos:**
    *   Filtre todos os gráficos e métricas por período (Data de Início e Fim).

## 🚀 Como Usar

Este projeto é **extremamente simples** de executar, pois não requer instalação de servidores, Node.js ou Python. Tudo roda diretamente no navegador.

1.  **Clone ou Baixe** este repositório.
2.  Navegue até a pasta do projeto.
3.  **Abra o arquivo `index.html`** com seu navegador preferido (Chrome, Edge, Firefox, etc.).

O dashboard carregará instantaneamente com os dados incluídos.

## 🛠️ Tecnologias Utilizadas

*   **HTML5 & CSS3**: Estrutura e estilização moderna (Dark Mode, Responsivo).
*   **JavaScript (ES6+)**: Lógica de processamento de dados e interatividade.
*   **[Chart.js](https://www.chartjs.org/)**: Biblioteca para geração dos gráficos (carregada via CDN).
*   **Google Fonts**: Tipografia moderna (DM Sans e JetBrains Mono).

## 📂 Estrutura de Dados

Os dados das corridas estão atualmente **embutidos** no próprio arquivo `index.html` dentro da variável constante `RAW_DATA`.

### Formato dos Dados (JSON)
Cada objeto de corrida possui a seguinte estrutura:

```json
{
  "id": 22101424785960,          // ID único da corrida
  "status": "finished",          // Status (finished, canceled, etc.)
  "call_time": "2026-02-12T16:45:24", // Data/Hora da chamada
  "complete_time": "2026-02-12T16:52:49", // Data/Hora da finalização
  "duration": 383,               // Duração em segundos
  "distance": 1.87,              // Distância em KM
  "payment": "Paid via Credit Card", // Método de pagamento
  "fee": 9.5,                    // Valor recebido (R$)
  "estimated_cost": 1.21,        // (Calculado Automaticamente)
  "net_income": 8.29             // (Calculado Automaticamente)
}
```

### Configuração de Custos
No início do código JavaScript (dentro de `index.html`), você pode ajustar os custos do seu veículo:

```javascript
const USER_METRICS = {
  costPerKm: 0.65,        // Custo total por KM (Combustível + Manutenção + Depreciação)
  avgConsumption: 10.75   // Consumo médio (KM/L) para estimativa de litros
};
```

### Atualizando os Dados
Para usar seus próprios dados:
1.  Gere um JSON com suas corridas seguindo o formato acima.
    *   *Dica: O arquivo `data/user_info.xlsx` pode ser usado como base para organizar seus dados antes de convertê-los.*
2.  Abra o arquivo `index.html` em um editor de texto (VS Code, Notepad++, etc.).
3.  Localize a variável `const RAW_DATA = [...]`.
4.  Substitua o conteúdo do array pelos seus novos dados.
5.  Salve e recarregue a página no navegador.

## 📄 Licença
Este projeto é de uso livre para fins pessoais e educativos.

---
*Desenvolvido para otimização de performance em mobilidade urbana.*
