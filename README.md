# FORJA

FORJA é um aplicativo web progressivo (PWA) para registrar, acompanhar e evoluir treinos de musculação com foco em hipertrofia. O projeto foi pensado para funcionar offline, ser instalado como app no celular e manter o controle do histórico, progresso e desempenho de forma simples e direta.

## Visão geral

O FORJA ajuda na organização da rotina de treino com:

- ficha de treino editável
- registro série a série
- cronômetro de descanso
- histórico de treinos
- evolução por exercício e por período
- biblioteca de exercícios
- backup local/exportação
- sincronização opcional via Supabase
- funcionamento offline e instalação como PWA

A aplicação usa HTML, CSS e JavaScript puro, sem dependências de build complexas, e pode ser publicada em qualquer hospedagem estática.

## Principais recursos

### Treino e acompanhamento
- registro de exercícios, cargas, repetições e séries
- fluxo de treinamento com foco no treino do dia
- comparação entre treino atual e anterior
- resumo de conclusão com volume, duração e recordes
- sugestões de progressão com base no histórico

### Evolução e análise
- painel de evolução com filtros por período
- métricas de volume semanal e consistência
- visualização de melhor marca e desempenho
- classificação por rank (C, B, A, S, SSS)
- histórico detalhado para acompanhamento de progresso

### PWA e offline
- funciona mesmo sem conexão
- pode ser instalado como app em Android e navegadores compatíveis
- atualizações via service worker
- suporte a uso local e persistência no navegador

### Backup, segurança e sincronização
- exportação/importação de dados em JSON
- backup opcional com criptografia
- sincronização via Supabase para uso em múltiplos dispositivos
- separação clara entre dados reais e dados de teste/simulação

## Requisitos

- navegador moderno com suporte a PWA
- Node.js 20+ para executar scripts de validação e testes
- Python 3 para análise de dados e testes automatizados

## Como iniciar

### 1) Clonar o projeto

```bash
git clone https://github.com/isaacmendonca31-sudo/Forja-App-v3.git
cd Forja-App-v3
```

### 2) Executar localmente

```bash
python3 -m http.server 8080
```

Ou, se preferir:

```bash
npm start
```

Depois abra no navegador:

```text
http://localhost:8080
```

> O service worker exige localhost ou HTTPS. Para instalar a PWA, use o prompt do navegador quando disponível.

## Scripts disponíveis

```bash
npm start
npm test
npm run check
npm run analyze
npm run icons
npm run test:py
```

### Descrição dos comandos

- `npm start`: inicia o servidor local para a aplicação
- `npm test`: executa os testes JavaScript
- `npm run check`: valida cache, testes JS e testes Python
- `npm run analyze`: executa análise de dados em Python
- `npm run icons`: gera ícones do projeto
- `npm run test:py`: executa testes Python

## Estrutura do projeto

```text
.
├── index.html
├── manifest.webmanifest
├── sw.js
├── package.json
├── _headers
├── css/
│   └── style.css
├── js/
│   ├── app.js
│   ├── backup.js
│   ├── chart.js
│   ├── config.js
│   ├── demo.js
│   ├── feedback.js
│   ├── gradient.js
│   ├── insights.js
│   ├── install.js
│   ├── legacy.js
│   ├── rank.js
│   ├── store.js
│   ├── suggest.js
│   ├── summary.js
│   ├── sync.js
│   ├── timer.js
│   ├── ui.js
│   ├── utils.js
│   ├── validate.js
│   ├── version.js
│   ├── data/
│   └── views/
├── scripts/
│   ├── analyze.py
│   ├── check-precache.mjs
│   └── make-icons.py
├── supabase/
│   └── schema.sql
├── tests/
├── docs/
│   ├── DEPLOY.md
│   ├── DESIGN-3.0.md
│   ├── FORJA-2.0.md
│   ├── PRIVACY.md
│   ├── RANK.md
│   ├── SECURITY.md
│   └── UX.md
├── icons/
├── README.md
└── .gitignore
```

## Documentação

A documentação do projeto está organizada em arquivos dedicados dentro de `docs/`:

- `docs/DEPLOY.md` — publicação e hospedagem
- `docs/SECURITY.md` — segurança e boas práticas
- `docs/PRIVACY.md` — privacidade e dados locais
- `docs/RANK.md` — sistema de rangos e classificação
- `docs/UX.md` — experiência e fluxo do usuário
- `docs/DESIGN-3.0.md` — diretrizes visuais e design

## Backup e sincronização

### Backup local
O app permite exportar e importar dados em JSON, incluindo a opção de backup protegido por senha quando necessário.

### Sincronização opcional
A sincronização via Supabase pode ser ativada para compartilhar dados entre aparelhos. O projeto inclui schema SQL e lógica de integração para esse fluxo.

Antes de usar em produção:

1. crie um projeto no Supabase
2. aplique `supabase/schema.sql`
3. configure as variáveis em `js/config.js`
4. teste com cuidado antes de confiar em sincronização em produção

## Privacidade e segurança

O projeto prioriza armazenamento local e controle do usuário sobre os dados. Algumas observações importantes:

- dados do treino são mantidos no navegador por padrão
- sincronização é opcional e exige configuração manual
- senhas e dados sensíveis não devem ser armazenados em ambientes compartilhados
- revise os documentos de segurança e privacidade antes de publicar em produção

## Publicação

Qualquer hospedagem estática serve para publicar o app, como:

- Netlify
- Cloudflare Pages
- Vercel
- GitHub Pages

Prefira serviços que permitam cabeçalhos HTTP e suporte a PWA, conforme descrito em `docs/DEPLOY.md`.

## Contribuição

Contribuições são bem-vindas. Se quiser melhorar o projeto:

1. faça um fork
2. crie uma branch para a mudança
3. implemente sua melhoria
4. rode os testes relevantes
5. abra um pull request descrevendo o que foi alterado

## Licença

Este projeto não informa explicitamente uma licença em `package.json` ou no repositório. Antes de reutilizar em produção ou distribuir publicamente, confirme a política de uso e os termos do projeto.

## Observações finais

FORJA foi pensado como uma ferramenta prática, leve e útil para acompanhamento de treinos de musculação. O objetivo principal é manter a rotina simples, clara e confiável, sem depender de infraestrutura pesada para funcionar bem.

---

Desenvolvido para apoiar o acompanhamento de treinos, volume, consistência e progresso ao longo do tempo.