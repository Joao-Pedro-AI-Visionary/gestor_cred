# 🏦 Gestor Cred System

Sistema web avançado para extração automatizada de dados de propostas de crédito consignado utilizando OCR via API Anthropic Claude.

## 📋 Índice

- [Características](#-características)
- [Tecnologias](#-tecnologias)
- [Instalação](#-instalação)
- [Configuração](#-configuração)
- [Uso](#-uso)
- [Segurança](#-segurança)
- [Estrutura do Projeto](#-estrutura-do-projeto)
- [API e Integrações](#-api-e-integrações)
- [Contribuição](#-contribuição)
- [Licença](#-licença)

## 🚀 Características

### Funcionalidades Principais
- ✅ **Extração OCR Automatizada**: 56 campos específicos de propostas de crédito
- ✅ **Interface Moderna**: Design responsivo e intuitivo
- ✅ **Processamento Paralelo**: Até 3 arquivos simultâneos
- ✅ **Drag & Drop**: Upload facilitado de arquivos PDF
- ✅ **Edição Completa**: Modal de edição para todos os campos extraídos
- ✅ **Gerenciamento Local**: Armazenamento seguro no navegador
- ✅ **Validação Robusta**: Verificação de formato e integridade

### Campos Extraídos
O sistema extrai automaticamente 56 campos organizados em categorias:

**Dados Pessoais**
- Nome completo, CPF, RG, data de nascimento
- Estado civil, nacionalidade, naturalidade

**Endereço Residencial**
- Logradouro, número, complemento, bairro
- Cidade, estado, CEP, tempo de residência

**Dados da Proposta**
- Número da proposta, data, valor solicitado
- Prazo, finalidade, tipo de operação

**Valores e Taxas**
- Taxa de juros, CET, valor das parcelas
- IOF, seguro, tarifa de cadastro

**E muito mais...**

## 🛠 Tecnologias

- **Frontend**: HTML5, CSS3, JavaScript ES6+
- **API**: Anthropic Claude (claude-sonnet-4-20250514)
- **Armazenamento**: LocalStorage (navegador)
- **Upload**: FileReader API nativa
- **Processamento**: Fetch API para requisições

## 📦 Instalação

### Pré-requisitos
- Navegador moderno (Chrome, Firefox, Safari, Edge)
- Chave API da Anthropic Claude
- Conexão com internet

### Passos de Instalação

1. **Clone o repositório**
   ```bash
   git clone https://github.com/Joao-Pedro-AI-Visionary/gestor_cred.git
   cd gestor_cred
   ```

2. **Abra o sistema**
   - Abra o arquivo `gestor_cred_system.html` em seu navegador
   - Ou use um servidor local:
   ```bash
   # Python 3
   python -m http.server 8000
   
   # Node.js (se tiver http-server instalado)
   npx http-server
   ```

3. **Acesse o sistema**
   - Navegador direto: `file:///caminho/para/gestor_cred_system.html`
   - Servidor local: `http://localhost:8000`

## ⚙️ Configuração

### 1. Configuração da API Claude

1. Acesse a aba **"Parametrização do Sistema"**
2. Insira sua chave API da Anthropic Claude
3. Clique em **"Salvar Configuração"**

**Formato da chave**: `sk-ant-api03-...`

### 2. Obtenção da Chave API

1. Acesse [console.anthropic.com](https://console.anthropic.com)
2. Crie uma conta ou faça login
3. Navegue para "API Keys"
4. Gere uma nova chave API
5. Copie e cole no sistema

## 📖 Uso

### Processamento de Propostas

1. **Upload de Arquivos**
   - Acesse a aba "Extração de Propostas"
   - Arraste arquivos PDF ou clique para selecionar
   - Máximo de 5 arquivos por vez

2. **Processamento**
   - Clique em "Processar Arquivos"
   - Acompanhe o progresso em tempo real
   - Visualize estatísticas de processamento

3. **Gerenciamento de Dados**
   - Acesse a aba "Propostas Extraídas"
   - Visualize dados em tabela responsiva
   - Edite campos individuais
   - Exclua propostas desnecessárias

### Funcionalidades Avançadas

- **Edição em Lote**: Selecione múltiplas propostas
- **Busca e Filtros**: Encontre propostas específicas
- **Exportação**: Dados em formato JSON
- **Backup Local**: Dados salvos automaticamente

## 🔒 Segurança

### Proteção de Dados

⚠️ **IMPORTANTE**: Este sistema armazena dados localmente no navegador

- **Chaves API**: Armazenadas em localStorage (criptografadas)
- **Dados de Propostas**: Mantidos localmente
- **Comunicação**: HTTPS obrigatório para API
- **Validação**: Sanitização de inputs

### Recomendações de Segurança

1. **Use HTTPS**: Sempre acesse via conexão segura
2. **Chaves Privadas**: Nunca compartilhe sua chave API
3. **Dados Sensíveis**: Faça backup regular dos dados
4. **Navegador Seguro**: Use navegadores atualizados
5. **Rede Confiável**: Evite redes públicas para dados sensíveis

### Conformidade

- **LGPD**: Dados processados localmente
- **Segurança**: Criptografia em trânsito
- **Privacidade**: Sem armazenamento em servidores externos

## 📁 Estrutura do Projeto

```
gestor_cred/
├── gestor_cred_system.html    # Sistema principal
├── .gitignore                 # Proteção de arquivos sensíveis
├── README.md                  # Documentação
└── docs/                      # Documentação adicional (futuro)
```

### Arquitetura do Sistema

```
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│   Interface     │    │   Processamento  │    │   API Claude    │
│   (HTML/CSS/JS) │◄──►│   (JavaScript)   │◄──►│   (Anthropic)   │
└─────────────────┘    └──────────────────┘    └─────────────────┘
         │                       │                       │
         ▼                       ▼                       ▼
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│  LocalStorage   │    │   FileReader     │    │   Fetch API     │
│  (Configuração) │    │   (Upload PDF)   │    │   (Requisições) │
└─────────────────┘    └──────────────────┘    └─────────────────┘
```

## 🔌 API e Integrações

### Anthropic Claude API

**Endpoint**: `https://api.anthropic.com/v1/messages`
**Modelo**: `claude-sonnet-4-20250514`
**Método**: POST

**Headers Necessários**:
```javascript
{
  'Content-Type': 'application/json',
  'x-api-key': 'sua-chave-api',
  'anthropic-version': '2023-06-01'
}
```

**Payload de Exemplo**:
```javascript
{
  "model": "claude-sonnet-4-20250514",
  "max_tokens": 4000,
  "messages": [
    {
      "role": "user",
      "content": [
        {
          "type": "text",
          "text": "Extraia os dados desta proposta..."
        },
        {
          "type": "image",
          "source": {
            "type": "base64",
            "media_type": "application/pdf",
            "data": "base64-encoded-pdf"
          }
        }
      ]
    }
  ]
}
```

### Rate Limits

- **Requisições**: Conforme plano Anthropic
- **Processamento**: 3 arquivos paralelos
- **Timeout**: 30 segundos por arquivo

## 🤝 Contribuição

### Como Contribuir

1. **Fork** o repositório
2. **Clone** sua fork
3. **Crie** uma branch para sua feature
4. **Implemente** suas mudanças
5. **Teste** thoroughly
6. **Commit** com mensagens claras
7. **Push** para sua branch
8. **Abra** um Pull Request

### Padrões de Código

- **JavaScript**: ES6+ com comentários em PT-BR
- **HTML**: Semântico e acessível
- **CSS**: Mobile-first, responsivo
- **Commits**: Conventional Commits

### Áreas para Contribuição

- 🔧 **Backend**: Implementação de servidor seguro
- 🎨 **UI/UX**: Melhorias na interface
- 🔒 **Segurança**: Implementações de segurança
- 📊 **Analytics**: Métricas e relatórios
- 🧪 **Testes**: Testes automatizados

## 📄 Licença

Este projeto está licenciado sob a **MIT License**.

```
MIT License

Copyright (c) 2024 Joao-Pedro-AI-Visionary

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 📞 Suporte

Para suporte, dúvidas ou sugestões:

- **GitHub Issues**: [Abrir Issue](https://github.com/Joao-Pedro-AI-Visionary/gestor_cred/issues)
- **Documentação**: Consulte este README
- **Email**: [Contato via GitHub](https://github.com/Joao-Pedro-AI-Visionary)

---

**Desenvolvido com ❤️ por [Joao-Pedro-AI-Visionary](https://github.com/Joao-Pedro-AI-Visionary)**

*Sistema Gestor Cred - Automatizando a extração de dados de propostas de crédito consignado*