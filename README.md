# WERT · interface de gestão

Interface de um projeto SaaS de gestão com áreas de usuários, produtos e inventário. Construída com **Next.js 14, React 18, TypeScript e Tailwind CSS**.

[API do projeto](https://github.com/Will-Ifes/wert-backend) · [Perfil do autor](https://github.com/Will-Ifes)

## Contexto e participação

Trabalho desenvolvido por Will Oliveira no projeto WERT, com colaboração registrada no projeto original. Esta edição de portfólio reúne uma cópia revisada do código com histórico novo; não reproduz o histórico de commits do desenvolvimento original.

O desafio da interface é organizar cadastros e operações de estoque em telas compreensíveis, conectadas às regras da API.

## Escopo presente

| Área | Conteúdo versionado |
| --- | --- |
| Autenticação | Login, cadastro e integração com a API |
| Produtos | Listagem e componentes de edição e confirmação de exclusão |
| Inventário | Consulta, entrada, saída e movimentações em abas |
| Usuários | Listagem e componentes de edição e visualização |
| Navegação | Header, sidebar e componentes de proteção de rotas |
| UI | Formulários, tabelas, diálogos, alertas e feedback |

## Arquitetura

| Caminho | Responsabilidade |
| --- | --- |
| [src/app](src/app) | Rotas e páginas do App Router |
| [src/actions/user.ts](src/actions/user.ts) | Integração de cadastro e autenticação |
| [src/components/application-bases](src/components/application-bases) | Estrutura de navegação e proteção de páginas |
| [src/components/ui](src/components/ui) | Primitivas de interface |
| [src/types](src/types) | Tipos de domínio usados pelo frontend |

A UI utiliza Radix e utilitários de composição de classes. Formulários usam React Hook Form e Zod. Os componentes de proteção da interface ajudam na navegação, mas a autorização dos dados precisa ser garantida pela API.

## Por dentro do código

- [Organização do inventário em abas](src/app/inventory/page.tsx).
- [Integração com os endpoints de usuários](src/actions/user.ts).
- [Contrato de login e geração de token](src/app/(auth)/login/validation/route.ts).
- [Componentes de produtos](src/app/products/components).

## Executar localmente

Requer Node.js, pnpm e a API configurada. Use as versões de dependências registradas no lockfile.

```bash
git clone https://github.com/Will-Ifes/wert-frontend.git
cd wert-frontend
pnpm install
pnpm dev
```

Antes de iniciar, configure `NEXT_PUBLIC_BACKEND_URL` em `.env.local` com a URL da sua API e `JWT_SECRET` no ambiente do servidor para os fluxos que assinam tokens. O segredo não deve usar prefixo `NEXT_PUBLIC_`. Confira também os endpoints de cada módulo: esta base preserva integrações históricas e requer revisão da configuração local.

A interface usa a porta padrão 3000. Para o backend atual em HTTPS, configure certificados confiáveis no seu ambiente.

## Qualidade e comandos

| Comando | Finalidade |
| --- | --- |
| `pnpm dev` | Desenvolvimento |
| `pnpm build` | Build do Next.js |
| `pnpm start` | Servidor da build |
| `pnpm lint` | ESLint |
| `pnpm format` | Formatação; modifica arquivos |

Não há suíte de testes automatizados versionada nesta edição. Os comandos foram conferidos no manifesto; esta documentação não declara build validada ou aplicação pronta para produção.

## Evolução

- Consolidar a configuração dos endpoints.
- Rever contratos e estados de erro dos formulários.
- Adicionar testes dos fluxos de autenticação e estoque.
- Verificar autorização no backend, acessibilidade e comportamento em telas menores.

## Procedência e uso

Esta cópia foi criada para apresentar o trabalho, removendo arquivos e dados locais do projeto original. A licença de uso do frontend não está definida em um arquivo de licença; consulte o autor para reutilização.

---

Mantido por **Will Oliveira** · [Perfil](https://github.com/Will-Ifes) · [LinkedIn](https://www.linkedin.com/in/wildemberg-de-jesus-oliveira/)
