Você é um especialista em AWS, arquitetura distribuída, Platform Engineering e Software Engineering.

Preciso de um relatório técnico detalhado avaliando estratégias para gerenciamento dinâmico de versões de uma biblioteca Python utilizada por uma aplicação FastAPI executando em ECS Fargate.

## Cenário

* A aplicação roda em AWS ECS Fargate.
* A aplicação é construída com FastAPI.
* Existe uma biblioteca Python interna compartilhada entre múltiplos serviços.
* Essa biblioteca será hospedada em um Artifactory privado.
* A aplicação referencia essa biblioteca através do gerenciador de pacotes Python (pip/poetry).
* O objetivo é permitir atualização e gestão de versões da biblioteca SEM necessidade de realizar novo deploy da aplicação/container sempre que a biblioteca for atualizada.

## Objetivos da análise

Quero um relatório técnico profundo contendo:

1. Explicação do problema arquitetural

   * Acoplamento entre imagem Docker e dependências
   * Limitações do ECS Fargate para hot reload de bibliotecas
   * Impactos em imutabilidade de containers
   * Riscos de drift de ambiente

2. Opções arquiteturais possíveis
   Avalie detalhadamente opções como:

   * Dynamic package loading em runtime
   * Sidecar container para sincronização de libs
   * Volume compartilhado (EFS)
   * Plugin architecture
   * Feature flags + remote configuration
   * Remote execution / Lambda
   * Service mesh / control plane
   * Hot swapping de módulos Python
   * Internal SDK Gateway
   * Version resolver via startup
   * Download dinâmico da lib no startup do container
   * Lazy loading da biblioteca
   * Multi-version runtime support
   * Runtime dependency injection
   * Remote policy/config driven execution

3. Para cada opção, explique:

   * Como funcionaria
   * Arquitetura proposta
   * Fluxo operacional
   * Complexidade
   * Custos AWS envolvidos
   * Impactos de performance
   * Segurança
   * Observabilidade
   * Rollback
   * Escalabilidade
   * Confiabilidade
   * Compatibilidade com ECS Fargate
   * Riscos operacionais
   * Trade-offs
   * Nível de maturidade da solução

4. Quero também:

   * Diagramas textuais de arquitetura
   * Exemplos práticos
   * Estratégias de cache
   * Estratégias de versionamento
   * Estratégias de rollback
   * Estratégias blue/green
   * Estratégias canary
   * Estratégias de compatibilidade retroativa
   * Estratégias para evitar downtime
   * Estratégias para evitar inconsistência entre tasks

5. Avalie abordagens modernas de:

   * Platform Engineering
   * AI Platform Engineering
   * Internal Developer Platforms (IDP)
   * Golden Paths
   * Runtime Control Planes
   * Dynamic Configuration Systems
   * Progressive Delivery
   * GitOps
   * MCP-like runtime orchestration
   * Sidecar patterns
   * WASM/plugin-based architectures

6. Quero uma comparação final em tabela contendo:

   * Complexidade
   * Custo
   * Performance
   * Segurança
   * Facilidade operacional
   * Tempo de implementação
   * Risco
   * Escalabilidade
   * Manutenibilidade
   * Aderência ao ECS Fargate

7. Ao final:

   * Dê sua recomendação técnica como arquiteto principal
   * Explique qual abordagem você escolheria em ambiente enterprise
   * Explique qual abordagem você escolheria para ambientes críticos de alta escala
   * Explique qual abordagem você evitaria e por quê
   * Explique o equilíbrio entre imutabilidade vs flexibilidade
   * Sugira uma arquitetura alvo moderna e madura

## Requisitos adicionais

* Considere boas práticas AWS Well-Architected Framework.
* Considere ambientes enterprise altamente regulados.
* Considere múltiplas squads consumindo a mesma lib.
* Considere CI/CD moderno.
* Considere observabilidade com Datadog/OpenTelemetry.
* Considere segurança de supply chain.
* Considere versionamento semântico.
* Considere riscos de dependências transitivas.
* Considere impacto em cold start e startup time.
* Considere estratégias multi-tenant.
* Considere uso de ECR, CodeArtifact, Artifactory, ECS Service Connect, AppConfig e Parameter Store.
* Considere cenários near real-time de atualização.
* Considere riscos de atualização automática em produção.

## Formato esperado

O relatório deve:

* Ser extremamente técnico
* Ser estruturado como um documento de arquitetura enterprise
* Possuir comparações profundas
* Ter visão crítica e pragmática
* Não apenas listar opções, mas recomendar claramente uma direção
* Explicar cenários onde cada abordagem faz sentido
* Incluir exemplos reais de mercado quando aplicável
* Priorizar soluções maduras e operacionalmente sustentáveis
* Trazer visão de longo prazo de platform engineering
