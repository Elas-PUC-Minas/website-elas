# Site do Projeto de Extensão Elas++

Este repositório contém o website do projeto de extensão "Elas++" — uma aplicação front-end construída com Next.js + TypeScript que organiza e apresenta informações sobre eventos, oficinas, publicações e integrantes do projeto.

Organização do sistema
- Páginas principais implementadas em `app/`: página inicial, `Eventos`, `Oficinas`, `Publicacoes` e `Sobre`.
- Componentes reutilizáveis em `app/components/` e `components/ui/` (botões, diálogos, Navbar, Footer, etc.).
- Rotas de API simples em `app/api/members` que servem dados de membros a partir de `data/members.json`.
- Conteúdo estático e dados de exemplo em `data/` (eventos, oficinas, publicações, membros).
- Estilização por meio de Tailwind/PostCSS (ver `postcss.config.mjs` e `tailwindcss` nas dependências).

Tecnologias usadas
- Framework: Next.js (versão declarada em `package.json`).
- Linguagem: TypeScript.
- UI: React + bibliotecas de componentes (`shadcn`, `radix-ui`, `lucide-react`, `@phosphor-icons/react`).
- Estilos: Tailwind CSS + PostCSS.
- Ferramentas de desenvolvimento: ESLint para linting.

Estrutura do projeto 
- `app/` — arquitetura de rotas e páginas do Next.js (contém `page.tsx`, subpastas por seção, e `api/`).
- `components/` — componentes reutilizáveis e primitives UI em `components/ui/`.
- `data/` — arquivos JSON com dados de exemplo: `eventos.json`, `oficinas.json`, `publicacoes.json`, `members.json`.
- `lib/` — helpers e camadas de acesso a dados (`members-data.ts`, `utils.ts`).
- `public/` — ativos públicos (imagens, ícones, etc.).
- `next.config.ts`, `tsconfig.json`, `postcss.config.mjs` — configs do projeto.

### Como rodar o projeto localmente

### Pré-requisitos
- Node.js 18+ recomendado (uma versão moderna do Node com suporte ao Next.js e ESM).
- npm (vem com Node) ou outro gerenciador de pacotes compatível.

### Passos rápidos
1. Clone o repositório e entre na pasta do projeto:

```bash
git clone https://github.com/Elas-PUC-Minas/website-elas.git
cd website-elas
```

2. Instale as dependências:

```bash
npm install
```

3. Rode em modo desenvolvimento (servidor com hot-reload):

```bash
npm run dev
```

4. Abra o navegador em `http://localhost:3000`.

Comandos úteis
- `npm run dev` — executa o Next.js em modo desenvolvimento.
- `npm run build` — gera a build de produção.
- `npm start` — inicia o servidor de produção após `npm run build`.
- `npm run lint` — executa o ESLint configurado.

Observações sobre variáveis de ambiente
- No estado atual do projeto não há variáveis de ambiente obrigatórias detectadas no código. As rotas de API usam os arquivos JSON em `data/` como fonte de dados de exemplo.

Dicas para desenvolvimento e contribuição
- Fluxo sugerido:
	1. Crie uma branch a partir de `main`: `git checkout -b feat/minha-mudanca`.
	2. Faça commits pequenos e descritivos.
	3. Abra um Pull Request explicando as mudanças.

- Para adicionar dados de teste, edite os arquivos em `data/` e atualize os componentes em `app/` que consomem esses dados.

Estrutura de código e pontos de entrada importantes
- Página principal e layout global: `app/layout.tsx` e `app/page.tsx`.
- Rotas/Seções: `app/Eventos`, `app/Oficinas`, `app/Publicacoes`, `app/Sobre`.
- API de membros: `app/api/members/route.ts` e `app/api/members/[username]/route.ts`.
- Componentes compartilhados: `app/components/Navbar.tsx`, `app/components/Footer.tsx`, `components/ui/button.tsx`.

Checklist rápido para testar localmente
- [ ] `npm install` completa sem erros.
- [ ] `npm run dev` inicia e a aplicação abre em `http://localhost:3000`.
- [ ] Navegar pelas páginas `Eventos`, `Oficinas`, `Publicacoes` e `Sobre` funciona.
- [ ] Endpoints de API para `members` retornam os JSON esperados.

Próximos passos recomendados
- Adicionar testes unitários e/ou integração (ex.: Jest + React Testing Library).
- Inserir validação de tipos mais estrita e regras de lint mais rígidas conforme o projeto crescer.
- Documentar padrões de componentes e guideline de design (se houver um design system a ser seguido).
- Configurar CI/CD para rodar lint/build e deploy automático.

Contato
- Se precisar de ajuda para rodar, testar ou modificar o projeto, abra uma issue ou envie uma mensagem no repositório.

Licença
- Consulte o arquivo `LICENSE` na raiz do repositório para informações sobre a licença do projeto.
