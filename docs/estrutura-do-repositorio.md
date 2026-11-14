# Estrutura do repositório de código (privado)

O código-fonte da Luneta fica em repositório privado. Este mapa descreve a organização para quem for avaliar ou continuar o trabalho.

| Pasta | Conteúdo |
|---|---|
| `apps/web` | Aplicação web (site estático), scripts de importação, build, auditoria e publicação, e documentação própria |
| `services/scraping` | Coletores por órgão, manifesto de fontes, esquemas, migrações e testes |
| `services/extraction` | Ponto de entrada da extração, decisões e experimentos |
| `pipeline_p1_documental` | Linha vigente da extração: prompts, esquemas por módulo, validadores e testes |
| `nova_arquitetura` | Contratos, invariantes, registro de decisões e índice de experimentos |
| `schemas` | Esquemas de dados compartilhados |
| `data/raw` | Documentos originais dos editais (entradas imutáveis) |
| `gabaritos` | Anotações humanas usadas como referência |
| `docs` | Arquitetura, decisões, auditorias, runbooks e diário de desenvolvimento |
| `ESTADO_ATUAL.md` | Única referência para a situação vigente e o próximo passo |

## Regras para quem continua

1. Ler primeiro `ESTADO_ATUAL.md` e o arquivo de decisões da frente em que for trabalhar.
2. Não preencher páginas à mão nem editar exports: o conteúdo vem do importador.
3. Toda experiência recebe nome e pasta de execução novos, com manifesto de configuração, hashes e métricas.
4. Não afirmar números que não foram medidos no pipeline ou no site, e registrar a data da medição.
5. Avisar o grupo antes de publicar em produção e usar o pacote de dados completo.

## Executar o site

Requer Node.js 22.18 ou superior.

```bash
cd apps/web
npm ci              # instala as dependências do lockfile
npm run dev         # desenvolvimento, porta 3000
npm test            # testes
npm run typecheck   # verificação de tipos
npm run build       # gera os arquivos estáticos em out/ e audita a saída
npm start           # serve out/ em http://127.0.0.1:4173
```

Para pedir acesso de leitura ao código, fale com a equipe.
