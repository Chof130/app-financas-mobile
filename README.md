# 💰 Minhas Finanças - App de Controle Financeiro Pessoal

Um aplicativo completo de controle financeiro pessoal desenvolvido com React Native e Expo, que permite gerenciar receitas, despesas e acompanhar o saldo financeiro de forma simples e intuitiva.

## 📱 Funcionalidades

### 🏠 Dashboard
- **Visão geral do saldo**: Exibe o saldo total, receitas e despesas
- **Cartões de resumo**: Visualização clara dos valores financeiros
- **Lista de transações**: Histórico completo das movimentações
- **Cotações em tempo real**: Dólar e Euro atualizados via API

### ➕ Nova Transação
- **Registro de receitas e despesas**: Interface intuitiva para adicionar transações
- **Categorização**: Organização por categorias (Alimentação, Transporte, Lazer, etc.)
- **Validação de dados**: Campos obrigatórios e formatação adequada

### 📊 Relatórios
- **Análise por período**: Filtros por data para acompanhar evolução financeira
- **Gráficos visuais**: Representação gráfica dos dados financeiros
- **Resumos detalhados**: Estatísticas completas das finanças

### ℹ️ Sobre
- **Informações do app**: Versão, descrição e tecnologias utilizadas
- **Interface limpa**: Design moderno e responsivo

## 🛠️ Tecnologias Utilizadas

### Frontend
- **React Native 0.81.5**: Framework principal para desenvolvimento mobile
- **Expo ~54.0.33**: Plataforma para desenvolvimento e build de apps React Native
- **React Navigation**: Navegação entre telas com abas e pilhas
- **React Native Paper**: Componentes UI modernos e acessíveis

### Banco de Dados
- **Expo SQLite ~16.0.10**: Banco de dados local SQLite integrado ao Expo
- **AsyncStorage**: Armazenamento persistente para configurações do app

### APIs Externas
- **API de Cotações**: Integração com serviço de cotações para obter valores atualizados do dólar e euro

### Desenvolvimento
- **JavaScript (ES6+)**: Linguagem de programação
- **React Hooks**: Gerenciamento de estado e efeitos colaterais
- **Context API**: Gerenciamento global de estado da aplicação

## 🏗️ Arquitetura do Projeto

```
minhas-financas/
├── assets/                 # Imagens e ícones do app
├── components/             # Componentes reutilizáveis
│   ├── CardsResumo.js      # Cards de resumo financeiro
│   ├── CartaoCotacoes.js   # Cartão de cotações
│   ├── CartaoSaldo.js      # Cartão de saldo
│   └── ItemTransacao.js    # Item individual de transação
├── context/                # Context API para gerenciamento de estado
│   ├── TransacoesContext.js    # Estado das transações
│   └── PrimeiroAcessoContext.js # Controle de primeiro acesso
├── database/               # Camada de dados
│   └── db.js              # Funções do banco SQLite
├── hooks/                  # Custom hooks
│   └── useCotacoes.js     # Hook para cotações
├── routes/                 # Configuração de navegação
│   ├── TabRoutes.js       # Navegação por abas
│   └── DashboardStack.js  # Pilha de navegação do dashboard
├── screens/                # Telas do aplicativo
│   ├── BoasVindasScreen.js    # Tela de boas-vindas
│   ├── DashboardScreen.js     # Tela principal
│   ├── DetalheTransacaoScreen.js # Detalhes da transação
│   ├── NovaTransacaoScreen.js # Nova transação
│   ├── RelatorioScreen.js     # Relatórios
│   └── SobreScreen.js         # Sobre o app
├── App.js                  # Componente raiz
├── app.json               # Configuração do Expo
├── index.js               # Ponto de entrada
├── metro.config.js        # Configuração do Metro bundler
├── package.json           # Dependências e scripts
└── theme.js              # Tema e estilos globais
```

## 🚀 Como Executar

### Pré-requisitos
- Node.js instalado
- Expo CLI instalado globalmente: `npm install -g @expo/cli`
- Dispositivo físico ou emulador/simulador

### Instalação

1. **Clone o repositório:**
   ```bash
   git clone https://github.com/Chof130/app-financas-mobile.git
   cd minhas-financas-api-conversor
   ```

2. **Instale as dependências:**
   ```bash
   npm install
   ```

3. **Inicie o servidor de desenvolvimento:**
   ```bash
   npm start
   # ou
   npx expo start
   ```

4. **Execute no dispositivo:**
   - **Android**: Pressione `a` no terminal ou escaneie o QR code com o app Expo Go
   - **iOS**: Pressione `i` no terminal ou escaneie o QR code com a câmera
   - **Web**: Pressione `w` no terminal

## 📊 Funcionalidades do Banco de Dados

O aplicativo utiliza SQLite local para armazenamento persistente dos dados:

### Tabela de Transações
```sql
CREATE TABLE transacoes (
  id        TEXT PRIMARY KEY,
  descricao TEXT NOT NULL,
  valor     REAL NOT NULL,
  tipo      TEXT NOT NULL, -- 'receita' ou 'despesa'
  categoria TEXT NOT NULL,
  data      TEXT NOT NULL
);
```

### Operações Disponíveis
- ✅ **Inserir transação**: Adicionar nova receita/despesa
- ✅ **Buscar todas**: Listar histórico completo
- ✅ **Excluir transação**: Remover item específico
- ✅ **Filtrar por categoria**: Buscar por tipo de gasto
- ✅ **Somar por tipo**: Calcular totais de receita/despesa
- ✅ **Filtrar por período**: Buscar transações em intervalo de datas

## 🎨 Design System

### Cores
- **Fundo**: `#f8f9fa`
- **Texto principal**: `#2c3e50`
- **Texto secundário**: `#95a5a6`
- **Receitas**: Verde (`#27ae60`)
- **Despesas**: Vermelho (`#e74c3c`)
- **Accent**: Azul (`#3498db`)

### Tipografia
- **Fonte**: Sistema padrão
- **Tamanhos**: 13px a 26px conforme hierarquia
- **Espaçamentos**: Sistema consistente (4px a 24px)

## 🔧 Scripts Disponíveis

```bash
npm start          # Inicia o servidor de desenvolvimento
npm run android    # Executa no Android
npm run ios        # Executa no iOS
npm run web        # Executa na web
```

## 📈 Melhorias Futuras

- [ ] **Sincronização na nuvem**: Backup e sincronização entre dispositivos
- [ ] **Gráficos avançados**: Visualizações mais detalhadas dos dados
- [ ] **Orçamentos**: Definição e controle de limites por categoria
- [ ] **Metas financeiras**: Acompanhamento de objetivos de economia
- [ ] **Exportação de dados**: Relatórios em PDF/Excel
- [ ] **Notificações**: Lembretes de contas e metas
- [ ] **Autenticação**: Login e múltiplos usuários
- [ ] **Moedas múltiplas**: Suporte a diferentes moedas

