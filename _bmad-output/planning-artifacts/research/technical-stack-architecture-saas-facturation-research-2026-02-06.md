---
stepsCompleted: [1, 2, 3, 4, 5]
inputDocuments: []
workflowType: 'research'
lastStep: 1
research_type: 'technical'
research_topic: 'Stack et architecture optimale pour SaaS de facturation/devis TPE'
research_goals: 'Identifier le stack front-end et back-end le plus adapte (pas overkill, pas sous-dimensionne), evaluer les architectures (monolithe, microservices, API Gateway), definir les bonnes pratiques (tests unitaires, documentation Swagger, lisibilite du code), et recommander une strategie de deploiement cloud'
user_name: 'Amine'
date: '2026-02-06'
web_research_enabled: true
source_verification: true
---

# Research Report: Technical

**Date:** 2026-02-06
**Author:** Amine
**Research Type:** Technical

---

## Research Overview

[Research overview and methodology will be appended here]

---

## Technical Research Scope Confirmation

**Research Topic:** Stack et architecture optimale pour SaaS de facturation/devis TPE
**Research Goals:** Identifier le stack front-end et back-end le plus adapte (pas overkill, pas sous-dimensionne), evaluer les architectures (monolithe, microservices, API Gateway), definir les bonnes pratiques (tests unitaires, documentation Swagger, lisibilite du code), et recommander une strategie de deploiement cloud

**Technical Research Scope:**

- Architecture Analysis - design patterns, frameworks, system architecture
- Implementation Approaches - development methodologies, coding patterns
- Technology Stack - languages, frameworks, tools, platforms
- Integration Patterns - APIs, protocols, interoperability
- Performance Considerations - scalability, optimization, patterns

**Research Methodology:**

- Current web data with rigorous source verification
- Multi-source validation for critical technical claims
- Confidence level framework for uncertain information
- Comprehensive technical coverage with architecture-specific insights

**Scope Confirmed:** 2026-02-06

## Technology Stack Analysis

### Langages de Programmation

#### TypeScript — Le choix unanime pour le full-stack SaaS

TypeScript s'impose comme le langage de reference pour les SaaS modernes en 2025-2026. Son avantage decisif dans votre contexte : **un seul langage pour le front-end ET le back-end**, ce qui simplifie enormement la vie d'un developpeur solo.

- **Typage statique** : Detection des erreurs a la compilation, code auto-documente, refactoring securise
- **Ecosysteme unifie** : Partage de types/interfaces entre front et back (DTOs, modeles)
- **Lisibilite** : Le typage rend le code comprehensible pour un futur collaborateur sans documentation excessive
- **Maturite** : Adoption massive dans l'industrie SaaS, communaute gigantesque, support IDE excellent

**Pourquoi pas PHP ?** PHP (Symfony/Laravel) reste solide pour le back-end, mais impose deux ecosystemes distincts (PHP + JS/TS) ce qui double la charge cognitive pour un dev solo. Le full-stack TypeScript elimine ce probleme.

_Niveau de confiance : Tres eleve — consensus multi-sources_
_Sources : [Dev.to - Backend Frameworks Comparison](https://dev.to/devops-make-it-run/comparing-backend-frameworks-for-high-load-applications-nestjs-laravel-symfony-and-zend-4779), [Yield Studio - Symfony vs Laravel vs Node.js](https://www.yieldstudio.fr/blog/symfony-vs-laravel-vs-node-js-quel-bon-framework-en-2025)_

### Frameworks de Developpement

#### Front-end : Next.js (React)

Next.js 16 (2025-2026) est le framework front-end dominant pour les SaaS, et particulierement adapte a votre projet :

- **React Server Components** : Reduction du JavaScript envoye au navigateur, performances ameliorees
- **App Router** : Architecture moderne avec layouts imbriques, loading states, error boundaries
- **API Routes & Middleware** : Gestion de l'authentification, redirections, headers
- **ISR (Incremental Static Regeneration)** : Performance optimale pour les pages semi-statiques
- **Cold starts 18% plus rapides** que Nuxt pour les deployments serverless
- **TurboPack** : Builds 28% plus rapides que Vite (Nuxt) en phase de test

**Pourquoi Next.js plutot que Nuxt ?** Pour un SaaS avec dashboard authentifie, gestion d'etat granulaire et interfaces data-driven, Next.js est le choix recommande. Nuxt excelle en vitesse de developpement et DX Vue, mais l'ecosysteme React est plus mature pour les applications complexes multi-tenant.

**Architecture de projet recommandee :**
- Structure feature-based (par domaine metier : auth, devis, factures, dashboard)
- Separation UI components / business logic / services
- Atomic Design compatible avec App Router

_Niveau de confiance : Tres eleve — Amine a deja de l'experience React/Next.js_
_Sources : [Strapi - Nuxt vs Next.js Guide](https://strapi.io/blog/nuxt-vs-nextjs-framework-comparison-guide), [InvexTech - Next.js vs Nuxt for SaaS](https://invextech.com/insights/nextjs-vs-nuxtjs), [G2Techsoft - Next.js Leads Frontend 2025](https://www.g2techsoft.com/blog/why-nextjs-leads-frontend-game-2025-comparison-reactjs-nuxtjs/), [CodeByDeep - Next.js Folder Structure 2026](https://www.codebydeep.com/blog/next-js-folder-structure-best-practices-for-scalable-applications-2026-guide)_

#### Back-end : NestJS

NestJS est le framework back-end TypeScript le plus adapte pour votre SaaS de facturation :

- **Architecture modulaire** : Organisation par modules (auth, users, devis, factures, paiements) — exactement ce qu'il faut pour un SaaS de facturation
- **Support natif microservices** : Pas utile au lancement, mais la porte est ouverte pour plus tard
- **Swagger/OpenAPI integre** : Documentation API automatique via decorateurs — repond directement a votre besoin de documentation
- **Testing natif avec Jest** : Tests unitaires et e2e preconfigures out-of-the-box
- **WebSockets integres** : Utile pour les notifications en temps reel (relances, paiements recus)
- **Scalabilite eprouvee** : Architecture non-bloquante (Node.js), gestion de charge sans saturation

**NestJS vs Symfony :** NestJS offre une architecture similaire a Symfony (injection de dependances, decorateurs, modules) mais avec l'avantage du full-stack TypeScript. Symfony reste excellent mais impose le dualisme PHP/JS.

**NestJS vs Laravel :** Laravel excelle pour les MVPs rapides, mais NestJS offre une meilleure scalabilite pour les architectures distribuees et une meilleure maintenabilite long terme.

_Niveau de confiance : Eleve — multiple sources concordantes_
_Sources : [Edana - Laravel vs NestJS](https://edana.ch/en/2026/01/06/laravel-or-nestjs-choosing-the-right-backend-based-on-your-needs-for-speed-scalability-and-long-term-growth/), [BetterStack - NestJS vs Laravel](https://betterstack.com/community/guides/scaling-nodejs/nestjs-vs-laravel/), [Dev.to - NestJS Laravel Symfony Comparison](https://dev.to/devops-make-it-run/comparing-nestjs-laravel-symfony-and-zend-framework-performance-scalability-and-use-cases-in-4f8a)_

### Base de Donnees et Technologies de Stockage

#### PostgreSQL — Le choix incontournable

PostgreSQL est devenu **le standard de facto** pour les SaaS en 2026. Le debat MySQL vs PostgreSQL est fonctionnellement termine dans le monde SaaS :

- **Transactions ACID** : Critique pour la facturation (coherence des donnees financieres)
- **JSONB natif** : Flexibilite pour les configurations utilisateur, metadata, logs d'activite sans sacrifier les performances
- **Multi-tenant** : Support excellent via schema separation ou tenant_id partage
- **Numerotation sequentielle** : Sequences PostgreSQL parfaites pour la numerotation inalterable des factures (conformite legale)
- **Archivage longue duree** : Robuste pour la conservation 10 ans requise
- **Extensions** : pgvector (IA future), PostGIS, full-text search integre

**Complement recommande :**
- **Redis** : Cache en memoire pour les sessions, les taux de TVA, les donnees frequemment accedees
- **S3/MinIO** : Stockage objet pour les PDFs generes, logos, pieces jointes

_Niveau de confiance : Tres eleve — consensus unanime des sources_
_Sources : [TechGeeta - PostgreSQL for SaaS 2026](https://techgeeta.com/blog/postgresql-for-saas-startups-2026), [Dev.to - PostgreSQL vs MySQL vs MongoDB 2026](https://dev.to/pockit_tools/postgresql-vs-mysql-vs-mongodb-in-2026-the-honest-comparison-nobody-asked-for-5fkc), [Bytebase - Postgres vs MySQL 2026](https://www.bytebase.com/blog/postgres-vs-mysql/)_

#### ORM : Prisma vs TypeORM

Deux options serieuses pour NestJS + PostgreSQL :

| Critere | Prisma | TypeORM |
|---------|--------|---------|
| DX (Developer Experience) | Excellent — schema-first, auto-completion | Bon — decorateurs familiers |
| Integration NestJS | Bonne (module dedie) | Excellente (natif) |
| Performance | Bonne | Bonne, controle plus fin |
| Migrations | Prisma Migrate (automatique) | Migrations manuelles ou auto |
| Lisibilite | Tres haute (DSL declaratif) | Haute (class-based) |
| Flexibilite queries | Moyenne (API haut niveau) | Haute (query builder puissant) |
| Risque | Vendor lock-in (DSL proprietaire) | Maintenance parfois lente |

**Recommandation pour votre contexte :** **Prisma** pour un dev solo qui veut aller vite avec une DX excellente et un code tres lisible. Si vous anticipez des requetes SQL tres complexes (reporting avance), TypeORM offre plus de controle.

**Alternative emergente :** **Drizzle ORM** — le plus performant en 2025 (jusqu'a 14x moins de latence sur les jointures complexes), mais ecosysteme moins mature.

_Niveau de confiance : Eleve — sources multiples avec nuances_
_Sources : [Dev.to - Best ORM for NestJS 2025](https://dev.to/sasithwarnakafonseka/best-orm-for-nestjs-in-2025-drizzle-orm-vs-typeorm-vs-prisma-229c), [Bytebase - Prisma vs TypeORM 2025](https://www.bytebase.com/blog/prisma-vs-typeorm/), [Medium - Prisma or TypeORM in 2026](https://medium.com/@Nexumo_/prisma-or-typeorm-in-2026-the-nestjs-data-layer-call-ae47b5cfdd73)_

### Outils de Developpement et Bonnes Pratiques

#### Testing (reponse directe a votre besoin)

**NestJS + Jest** (preconfigure) :
- **Tests unitaires** : Chaque service, controller, guard teste isolement avec mocks
- **Tests d'integration** : Supertest pour les assertions HTTP, base de donnees de test dediee
- **Tests e2e** : Scenarios complets (creer un devis → convertir en facture → marquer paye)
- **Bonnes pratiques** : async/await, jest.spyOn pour les mocks, eviter le mocking excessif, tester le comportement reel

_Source : [NestJS Docs - Testing](https://docs.nestjs.com/fundamentals/testing), [FreeCodeCamp - NestJS Testing Guide](https://www.freecodecamp.org/news/nestjs-unit-testing-e2e-testing-guide/), [Toxigon - Testing NestJS 2025](https://toxigon.com/best-practices-for-testing-nestjs-applications)_

#### Documentation API (reponse directe a votre besoin)

**NestJS + @nestjs/swagger** :
- Documentation Swagger/OpenAPI **generee automatiquement** depuis les decorateurs
- CLI Plugin qui analyse le code TypeScript et ajoute les decorateurs a la compilation — moins de boilerplate
- Organisation par tags (@ApiTags) pour grouper les endpoints (Devis, Factures, Clients, Auth)
- Exemples de valeurs dans les DTOs → documentation interactive testable
- Versioning API reflete dans la documentation

_Source : [NestJS Docs - OpenAPI](https://docs.nestjs.com/openapi/introduction), [DevCentreHouse - NestJS Swagger Auto-Generate](https://www.devcentrehouse.eu/blogs/nestjs-swagger-auto-generate-api-docs/), [Dev.to - 5 Tips Better Swagger NestJS](https://dev.to/antoncodes/5-tips-for-better-swagger-docs-in-nestjs-ng9)_

### Infrastructure Cloud et Deploiement

#### Strategie recommandee : Separation Front / Back

| Composant | Plateforme | Cout estimatif | Justification |
|-----------|-----------|----------------|---------------|
| **Front-end (Next.js)** | Vercel | Gratuit → $20/mois | Optimise pour Next.js, CDN global, preview deployments |
| **Back-end (NestJS)** | Railway | $5 → $20/mois | Simple, PostgreSQL manage, bon rapport qualite/prix |
| **Base de donnees** | Railway PostgreSQL ou Neon | $5 → $15/mois | Manage, backups auto, scale-to-zero (Neon) |
| **Stockage fichiers** | S3 (AWS) ou Cloudflare R2 | ~$1-5/mois | PDFs, logos, pieces jointes |
| **Redis (cache)** | Upstash | Gratuit → $10/mois | Serverless, pay-per-use |

**Cout total estimatif au lancement : $10-30/mois**

**Alternatives :**
- **Render** : $19/mois minimum, bonne alternative a Railway
- **AWS complet** : Plus puissant mais plus complexe, $30+/mois, recommande quand vous scalez
- **OVH** : Moins cher pour du VPS, mais plus de gestion manuelle

**Attention Vercel** : A fort trafic, les couts de bande passante peuvent exploser (cas documente d'une startup a $2,000/mois). Pour un SaaS de facturation TPE, ce risque est faible au depart.

_Niveau de confiance : Eleve — donnees de pricing verifiees multi-sources_
_Sources : [Northflank - Cloud Deployment Platforms 2026](https://northflank.com/blog/best-cloud-app-deployment-platforms), [Railway vs Vercel Comparison](https://ritza.co/articles/gen-articles/cloud-hosting-providers/railway-vs-vercel/), [MakerKit - Best Next.js Hosting 2026](https://makerkit.dev/blog/tutorials/best-hosting-nextjs), [DigitalOcean - Vercel Alternatives 2026](https://www.digitalocean.com/resources/articles/vercel-alternatives)_

### Architecture : Monolithe Modulaire

#### Pourquoi PAS de microservices

Le consensus 2025-2026 est clair : **les microservices ne beneficient qu'aux equipes de 10+ developpeurs**. En dessous de ce seuil, le monolithe performe mieux. En tant que dev solo, les microservices seraient un piege :

- Complexite operationnelle massive (orchestration, monitoring, debugging distribue)
- Overhead de communication inter-services
- Tests d'integration exponentiellement plus complexes
- Cout d'infrastructure multiplie

#### Le Monolithe Modulaire — Le juste milieu parfait

La strategie recommandee : **monolithe modulaire** (ou "modular monolith") avec NestJS :

```
src/
├── modules/
│   ├── auth/          (authentification, JWT, roles)
│   ├── users/         (profils entreprise, SIRET, logo)
│   ├── clients/       (carnet clients, auto-completion)
│   ├── catalog/       (produits/prestations, prix)
│   ├── quotes/        (devis, cycle de vie, PDF)
│   ├── invoices/      (factures, numerotation, conformite)
│   ├── payments/      (statuts, relances, liens paiement)
│   ├── dashboard/     (metriques, filtres, exports)
│   └── common/        (shared DTOs, guards, interceptors)
├── infrastructure/
│   ├── database/      (Prisma schema, migrations, seeds)
│   ├── storage/       (S3/R2, generation PDF)
│   ├── mail/          (emails transactionnels, relances)
│   └── config/        (variables d'environnement)
└── main.ts
```

**Avantages :**
- Chaque module a ses propres controllers, services, DTOs, tests
- Boundaries claires entre domaines metier (devis ≠ factures ≠ paiements)
- Refactorable en microservices plus tard si necessaire (NestJS le supporte nativement)
- Un seul process, un seul deploiement, debugging simple
- Tests unitaires par module + tests e2e globaux

**Pas besoin d'API Gateway** au stade actuel : un monolithe n'a pas de services a orchestrer. Le middleware NestJS suffit pour l'authentification, le rate limiting et le logging.

_Niveau de confiance : Tres eleve — consensus fort dans la communaute_
_Sources : [Dev.to - Monoliths vs Microservices Startups](https://dev.to/naveens16/monoliths-vs-microservices-why-startups-should-think-twice-before-going-distributed-17p2), [Scalosoft - Monolithic vs Microservices 2025](https://www.scalosoft.com/blog/monolithic-vs-microservices-architecture-pros-and-cons-for-2025/), [Medium - Scalable SaaS Architecture](https://medium.com/@beta_49625/building-scalable-saas-architecture-microservices-vs-monolith-trade-offs-explained-40186f0fed05)_

### Tendances d'Adoption et Evolution

#### Le stack "Full TypeScript SaaS" en 2025-2026

La tendance dominante pour les SaaS modernes :
- **TypeScript partout** : Front + Back + Tests + Scripts
- **Monorepo** (optionnel) : Turborepo ou Nx pour partager les types entre front et back
- **Schema-first** : Prisma pour la BDD, Zod pour la validation, OpenAPI pour l'API
- **Infrastructure as Code** : Docker + docker-compose pour le dev local
- **CI/CD** : GitHub Actions pour les tests auto et le deploiement

#### Evolution prevue

1. **Court terme** : Monolithe modulaire NestJS + Next.js sur Railway/Vercel
2. **Moyen terme** : Extraction de services si besoin (PDF generation, email)
3. **Long terme** : Migration vers AWS/infra dediee si le trafic le justifie

_Sources : [Ace Infoway - Top Backend Frameworks 2026](https://www.aceinfoway.com/blog/best-backend-frameworks), [Kanhasoft - Scalable SaaS with Next.js](https://kanhasoft.com/blog/how-to-build-scalable-saas-products-with-next-js/)_

## Integration Patterns Analysis

### API Design Patterns — REST API avec NestJS

Pour un SaaS de facturation TPE, l'API REST classique est le choix optimal. GraphQL et gRPC seraient de l'overkill pour ce contexte.

**Architecture REST recommandee :**

- **Controllers par ressource** : Un controller dedie par entite metier (DevisController, FacturesController, ClientsController, etc.)
- **Pagination obligatoire** : Sur toutes les collections (devis, factures, clients) — baisse de 45% des temps de reponse avec une page size de 50 vs requetes non-limitees
- **Codes HTTP precis** : 201 (creation), 409 (conflit), 422 (validation), 404 (introuvable) — structure d'erreur unifiee
- **Versioning API** : Prefixe `/api/v1/` pour permettre l'evolution sans casser les clients existants
- **Swagger auto** : Chaque endpoint documente via decorateurs NestJS (@ApiTags, @ApiResponse, @ApiProperty)

**Conventions de nommage :**
```
GET    /api/v1/quotes          → Liste des devis (pagine)
POST   /api/v1/quotes          → Creer un devis
GET    /api/v1/quotes/:id      → Detail d'un devis
PATCH  /api/v1/quotes/:id      → Modifier un devis
POST   /api/v1/quotes/:id/convert  → Convertir en facture
GET    /api/v1/invoices         → Liste des factures
POST   /api/v1/invoices/:id/remind → Envoyer une relance
```

**Logging structure :** Winston ou Pino pour les logs JSON structures avec correlation IDs, rotation et niveaux d'erreur.

_Niveau de confiance : Tres eleve — patterns REST matures et bien documentes_
_Sources : [Medium - Mastering NestJS REST API](https://medium.com/@janishar.ali/mastering-nestjs-building-an-effective-rest-api-backend-8a5add59c2f5), [Startup House - NestJS RESTful APIs Guide](https://startup-house.com/blog/nestjs-restful-apis-guide), [MoldStud - RESTful API Best Practices NestJS](https://moldstud.com/articles/p-top-faqs-on-best-practices-for-restful-apis-in-nestjs-development)_

### Generation de PDF (Devis & Factures)

La generation de PDF est une integration critique pour votre SaaS. Deux approches principales :

| Critere | Puppeteer (HTML→PDF) | PDFKit (programmatique) |
|---------|---------------------|------------------------|
| Approche | Template HTML/CSS → rendu Chrome headless | Construction programmatique du PDF |
| Facilite | Facile si vous maitrisez HTML/CSS | Courbe d'apprentissage plus raide |
| Qualite visuelle | Excellente (rendu navigateur reel) | Bonne mais plus de travail |
| Performance | Plus lent (demarre Chrome a chaque fois) | Tres rapide |
| Personnalisation | Templates HTML reutilisables | Controle pixel-perfect |
| Ressources serveur | Gourmand (Chrome headless) | Leger |

**Recommandation : Puppeteer** pour votre contexte :
- Vous connaissez deja HTML/CSS (React dev)
- Templates de devis/factures faciles a designer et maintenir
- Le logo, les mentions legales, la mise en page se gerent en CSS
- Performance acceptable pour un SaaS TPE (pas des milliers de PDFs/seconde)
- **Astuce performance** : Garder une instance Puppeteer persistante (pool de navigateurs) plutot que de relancer Chrome a chaque PDF

**Alternative legere :** `@react-pdf/renderer` — generer les PDFs avec des composants React, coherent avec votre stack front-end.

_Niveau de confiance : Eleve — choix dependant du volume, Puppeteer adapte pour TPE_
_Sources : [LogRocket - Best HTML to PDF Libraries Node.js](https://blog.logrocket.com/best-html-pdf-libraries-node-js/), [LeadWithSkills - PDF Generation Puppeteer vs PDFKit](https://www.leadwithskills.com/blogs/pdf-generation-nodejs-puppeteer-pdfkit), [Dev.to - 5 Node.js PDF Libraries](https://dev.to/xeshan6981/the-5-nodejs-pdf-libraries-every-developer-must-know-4b39)_

### Integration Paiement — Stripe

Stripe est le choix naturel pour un SaaS de facturation en France :

**Fonctionnalites cles pour votre projet :**
- **Stripe Payment Links** : Lien de paiement direct dans l'email de facture ("Payer maintenant" — idee #27 du brainstorming)
- **Stripe Checkout** : Page de paiement hebergee, conforme PCI-DSS sans effort
- **Stripe Billing** : Gestion des abonnements pour votre propre modele SaaS (pricing par paliers)
- **Webhooks** : Notification en temps reel quand un paiement est recu → mise a jour automatique du statut facture
- **Multi-devises** : Pret pour l'international si necessaire

**Integration NestJS :**
- Package `nestjs-stripe` pour l'injection de dependances
- Module dedie `/modules/payments/` avec service, controller, webhooks handler
- Webhook endpoint securise pour les evenements Stripe (payment_intent.succeeded, etc.)

**Alternatives :**
- **GoCardless** : Prelevement SEPA (pertinent pour la France)
- **Mollie** : Alternative europeenne, excellente pour les marchands francais

_Niveau de confiance : Eleve — Stripe domine le marche SaaS, excellente documentation_
_Sources : [Dev.to - Stripe Payment Processing NestJS](https://dev.to/slaknoah/seamless-payment-processing-with-stripe-and-nestjs-3cbg), [Medium - Payment Module NestJS](https://medium.com/@yassinejedidi10/how-to-implement-a-payment-module-in-nestjs-ad402aa7f83d), [SlakNoah - Stripe and NestJS](https://www.slaknoah.com/blog/seamless-payment-processing-with-stripe-and-nest-js)_

### Email Transactionnel (Relances & Notifications)

Pour les emails de relance de facture, envoi de devis, et notifications :

| Critere | Resend | Brevo (ex-Sendinblue) | SendGrid |
|---------|--------|----------------------|----------|
| DX (Developer Experience) | Excellent — API moderne, docs claires | Bon — lib simple NestJS | Bon — mature |
| Prix (startup) | ~$20/mois | Gratuit 300 emails/jour | ~$20/mois |
| Specialite | Transactionnel pur | All-in-one (marketing + transac) | Transactionnel + marketing |
| Deliverabilite | Tres bonne | 99% | Tres bonne |
| Avantage France | - | Entreprise francaise, conformite RGPD native | - |

**Recommandation : Resend** pour la DX et la simplicite, ou **Brevo** si vous voulez un outil francais RGPD-natif avec marketing email inclus (utile pour les relances et newsletters futurs).

**Cas d'usage dans votre SaaS :**
- Envoi de devis PDF par email
- Relance automatique de facture impayee (idee #66 du brainstorming)
- Notification de paiement recu
- Email de bienvenue et onboarding

_Niveau de confiance : Eleve — comparaison multi-sources coherente_
_Sources : [Brevo - SendGrid Alternatives 2026](https://www.brevo.com/blog/sendgrid-alternatives/), [NextBuild - Resend vs SendGrid vs SES](https://nextbuild.co/blog/resend-vs-sendgrid-vs-ses-email), [EmailToolTester - Best Transactional Email 2026](https://www.emailtooltester.com/en/blog/best-transactional-email-service/)_

### Authentification & Securite — JWT + RBAC

**Architecture d'authentification recommandee :**

- **JWT (JSON Web Tokens)** : Standard pour les SaaS, stateless, scalable
- **Refresh Tokens** : Stockes en base (PostgreSQL), rotation automatique
- **Passport.js** : Integration native NestJS via `@nestjs/passport`
- **Guards NestJS** : AuthGuard (JWT), RolesGuard (RBAC), TenantGuard (multi-tenant)

**RBAC (Role-Based Access Control) :**
- **Roles prevus** : Owner (proprietaire), Admin, Gestionnaire, Comptable (idee #75 du brainstorming)
- **Principe du moindre privilege** : Chaque role a uniquement les permissions necessaires
- **JWT payload minimal** : user_id, tenant_id, roles — pas de donnees sensibles
- **Logging des tentatives non autorisees** : Audit trail pour la conformite (idee #38)

**Multi-tenant :**
- Strategie `tenant_id` dans chaque table (shared schema) — simple et efficace
- `TenantGuard` NestJS qui injecte le tenant_id dans chaque requete
- Isolation stricte : un utilisateur ne voit JAMAIS les donnees d'un autre tenant (idee #74)

**OAuth2 (optionnel, phase 2) :**
- Login Google / Microsoft pour simplifier l'onboarding
- Architecture extensible : ajouter un provider OAuth = implementer une interface + enregistrer dans la factory

_Niveau de confiance : Tres eleve — patterns de securite bien etablis_
_Sources : [NestJS Docs - Authentication](https://docs.nestjs.com/security/authentication), [Medium - Production-Ready JWT RBAC NestJS](https://medium.com/@sabin.shrestha.er/stop-rebuilding-auth-a-production-ready-jwt-rbac-template-for-nestjs-18d99f9b8944), [Permit.io - RBAC Authorization NestJS](https://www.permit.io/blog/how-to-protect-a-url-inside-a-nestjs-app-using-rbac-authorization), [Medium - Multi-Provider OAuth2 NestJS](https://medium.com/@camillefauchier/multi-provider-oauth2-authentication-in-nestjs-beyond-basic-jwt-7945ece51bb3)_

### Jobs en Arriere-Plan — BullMQ + Redis

**BullMQ** (via `@nestjs/bullmq`) est le systeme de queues recommande pour NestJS :

**Cas d'usage dans votre SaaS :**
- **Relances automatiques** : Cron job qui verifie les factures impayees et envoie des emails de relance
- **Generation PDF** : Mise en file d'attente pour ne pas bloquer l'API
- **Expiration des devis** : Job programme qui passe les devis expires en "Sans suite" (idee #14)
- **Passage en "retardee"** : Verification quotidienne des delais de paiement depasses (idee #11)
- **Notifications** : Envoi asynchrone pour ne pas ralentir l'UX

**Avantages BullMQ :**
- Retries automatiques avec backoff exponentiel
- Jobs programmes et recurrents (cron)
- Dead-letter queues pour les jobs echoues
- Rate limiting pour eviter de surcharger les APIs externes (Stripe, email)
- **Execution unique garantie** : En multi-instance, un seul worker execute chaque job (pas de doublons)

**Infrastructure :** Utilise Redis (deja prevu dans le stack via Upstash) — zero infrastructure supplementaire.

_Niveau de confiance : Tres eleve — BullMQ est le standard NestJS pour les queues_
_Sources : [NestJS Docs - Queues](https://docs.nestjs.com/techniques/queues), [Medium - BullMQ with NestJS](https://mahabub-r.medium.com/using-bullmq-with-nestjs-for-background-job-processing-320ab938048a), [Dev.to - Cron Jobs NestJS with Bull](https://dev.to/juan_castillo/handling-cron-jobs-in-nestjs-with-multiple-instances-using-bull-3pj2), [Dev.to - BullMQ Queues DLQs Bull Board](https://dev.to/ronak_navadia/level-up-your-nestjs-app-with-bullmq-queues-dlqs-bull-board-5hnn)_

### Formats de Donnees et Standards

**JSON** : Format unique pour toutes les communications API (requetes, reponses, webhooks)
- DTOs valides avec `class-validator` + `class-transformer` (NestJS natif)
- Validation Zod comme alternative plus moderne et type-safe

**OpenAPI 3.0** : Standard de documentation API, genere automatiquement par `@nestjs/swagger`

**PDF/A** : Format d'archivage longue duree pour les factures (conformite legale francaise — conservation 10 ans)

### Schema d'Integration Global

```
┌─────────────┐     ┌──────────────┐     ┌─────────────┐
│  Next.js     │────▶│  NestJS API  │────▶│ PostgreSQL  │
│  (Vercel)    │◀────│  (Railway)   │◀────│ (Railway)   │
└─────────────┘     └──────┬───────┘     └─────────────┘
                           │
              ┌────────────┼────────────┐
              ▼            ▼            ▼
       ┌──────────┐ ┌──────────┐ ┌──────────┐
       │  Stripe   │ │  Resend/  │ │  S3/R2   │
       │ (Paiement)│ │  Brevo    │ │ (PDFs)   │
       └──────────┘ │ (Emails)  │ └──────────┘
                    └──────────┘
              ┌────────────┐
              │  Redis      │ ← BullMQ (queues, cron, jobs)
              │  (Upstash)  │
              └────────────┘
```

_Ce schema montre que chaque service externe est isole dans son propre module NestJS, facilitant le remplacement ou l'evolution de chaque brique independamment._

## Architectural Patterns and Design

### Architecture Systeme — Le Monolithe Modulaire en Detail

#### Pourquoi le monolithe modulaire (et pas Clean/Hexagonal au demarrage)

Un point crucial revele par la recherche : les architectures Clean/Hexagonal et DDD completes **ne sont pas recommandees pour les applications petites/moyennes** avec une logique metier limitee au demarrage. Elles ajoutent :
- Du boilerplate et des abstractions prematurees
- De la complexite structurelle qui ralentit un dev solo
- Des couches d'indirection qui n'apportent rien quand la logique est simple

**L'approche pragmatique recommandee en 2025 :**

> "Commencer par un monolithe modulaire pragmatique, sans Clean Architecture ni DDD complets, pour reduire la complexite et favoriser l'iteration rapide."

Cela dit, les **principes** de ces architectures restent precieux :
- **Separation des responsabilites** : Chaque module NestJS encapsule un domaine metier
- **Injection de dependances** : NestJS le fournit nativement
- **Inversion de controle** : Facile a appliquer via les interfaces TypeScript
- **Boundaries claires** : Un module ne devrait pas acceder directement aux internals d'un autre

**Evolution prevue :** Si la logique metier se complexifie (multi-pays, reglementations differentes, module comptable avance), migrer progressivement vers une architecture hexagonale par module — sans tout refaire.

_Niveau de confiance : Tres eleve — consensus fort entre pragmatisme et principes solides_
_Sources : [Dev.to - Domain-Driven Hexagon](https://dev.to/sairyss/domain-driven-hexagon-18g5), [Medium - NestJS Modularization for Scale](https://medium.com/@hadiyolworld007/breaking-the-monolith-nestjs-modularization-for-scale-and-speed-5981a6397998), [LevelUp - NestJS Modular Architecture](https://levelup.gitconnected.com/nest-js-and-modular-architecture-principles-and-best-practices-806c2cb008d5)_

#### Structure Backend Detaillee (NestJS)

```
src/
├── modules/
│   ├── auth/
│   │   ├── controllers/        auth.controller.ts
│   │   ├── services/           auth.service.ts
│   │   ├── guards/             jwt-auth.guard.ts, roles.guard.ts
│   │   ├── strategies/         jwt.strategy.ts, local.strategy.ts
│   │   ├── dto/                login.dto.ts, register.dto.ts
│   │   ├── decorators/         roles.decorator.ts, current-user.decorator.ts
│   │   ├── tests/              auth.service.spec.ts, auth.controller.spec.ts
│   │   └── auth.module.ts
│   │
│   ├── users/
│   │   ├── controllers/        users.controller.ts
│   │   ├── services/           users.service.ts
│   │   ├── dto/                create-user.dto.ts, update-profile.dto.ts
│   │   ├── tests/              users.service.spec.ts
│   │   └── users.module.ts
│   │
│   ├── companies/              (profil entreprise, SIRET, logo, mentions)
│   ├── clients/                (carnet clients, contacts)
│   ├── catalog/                (produits, prestations, prix)
│   ├── quotes/                 (devis, cycle de vie, duplication)
│   ├── invoices/               (factures, numerotation, conformite)
│   ├── payments/               (statuts, Stripe webhooks)
│   ├── reminders/              (relances auto, BullMQ jobs)
│   ├── dashboard/              (metriques, filtres, exports)
│   └── documents/              (generation PDF, stockage S3)
│
├── common/
│   ├── filters/                http-exception.filter.ts
│   ├── interceptors/           logging.interceptor.ts, transform.interceptor.ts
│   ├── pipes/                  validation.pipe.ts
│   ├── decorators/             api-paginated.decorator.ts
│   ├── dto/                    pagination.dto.ts, api-response.dto.ts
│   └── utils/                  date.utils.ts, number.utils.ts
│
├── infrastructure/
│   ├── database/
│   │   ├── prisma/             schema.prisma, migrations/, seed.ts
│   │   └── prisma.service.ts
│   ├── storage/                s3.service.ts
│   ├── mail/                   mail.service.ts, templates/
│   ├── queue/                  queue.module.ts, processors/
│   └── config/                 configuration.ts, validation.ts
│
├── app.module.ts
└── main.ts
```

**Principes cles :**
- Un module par domaine metier (pas par entite — eviter les dependances circulaires)
- Chaque module contient ses propres controllers, services, DTOs, tests
- Le dossier `common/` pour le code transversal (filtres, intercepteurs, pipes)
- Le dossier `infrastructure/` pour les concerns techniques (BDD, stockage, email, queues)
- Prefixes/suffixes clairs dans les noms de fichiers pour la lisibilite

_Source : [GeeksforGeeks - NestJS Folder Structure](https://www.geeksforgeeks.org/javascript/folder-structure-of-a-nestjs-project/), [GitHub - NestJS Modular Monolith Template](https://github.com/deadislove/nestJS-modular-monolith-architecture-template), [Medium - NestJS Best Practices Structuring](https://arnab-k.medium.com/best-practices-for-structuring-a-nestjs-application-b3f627548220)_

### Architecture Frontend — Feature-Based (Next.js)

#### Pourquoi PAS Atomic Design

La recherche revele un changement de paradigme en 2025 : **Atomic Design est de moins en moins utilise** pour les applications SaaS complexes avec logique metier. Pour les projets avec entites business (devis, factures, clients), l'architecture **Feature-Based** ou **Feature-Sliced Design** est preferee :

- Atomic Design fonctionne bien pour les Design Systems et les UI libraries
- Mais pour un SaaS avec dashboard, workflows et logique metier, il cree de la confusion entre "ou mettre la logique"

#### Structure Frontend Recommandee

```
src/
├── app/                        (Next.js App Router)
│   ├── (auth)/                 Login, Register, Forgot Password
│   │   ├── login/page.tsx
│   │   └── register/page.tsx
│   ├── (dashboard)/            Layout authentifie
│   │   ├── layout.tsx          Sidebar, Header, Navigation
│   │   ├── page.tsx            Dashboard principal
│   │   ├── quotes/             Pages devis
│   │   ├── invoices/           Pages factures
│   │   ├── clients/            Pages clients
│   │   ├── settings/           Profil entreprise, parametres
│   │   └── reports/            Metriques, exports
│   └── api/                    API Routes (si necessaire)
│
├── features/                   (Logique metier par domaine)
│   ├── quotes/
│   │   ├── components/         QuoteForm, QuoteList, QuoteStatusBadge
│   │   ├── hooks/              useQuotes, useCreateQuote, useQuoteStatus
│   │   ├── services/           quotes.api.ts (appels API)
│   │   ├── types/              quote.types.ts
│   │   └── utils/              quote.utils.ts
│   ├── invoices/
│   ├── clients/
│   ├── payments/
│   └── dashboard/
│
├── shared/                     (Composants UI reutilisables)
│   ├── ui/                     Button, Input, Modal, Table, Badge
│   ├── layout/                 Sidebar, Header, Footer
│   ├── forms/                  FormField, FormSelect, FormDatePicker
│   └── feedback/               Toast, Alert, Loading, EmptyState
│
├── lib/                        (Utilitaires globaux)
│   ├── api/                    Client API (Axios/fetch), interceptors
│   ├── auth/                   AuthProvider, useAuth, tokens
│   ├── hooks/                  useDebounce, usePagination
│   └── utils/                  format-date, format-currency, cn()
│
└── types/                      Types globaux partages
```

**Gestion d'etat :**
- **React Query (TanStack Query)** : Cache, synchronisation serveur, mutations — parfait pour un SaaS data-driven
- **Zustand** (optionnel) : Etat client leger si necessaire (preferences UI, sidebar open/close)
- **Pas de Redux** : Overkill pour ce projet, React Query couvre 90% des besoins

_Niveau de confiance : Eleve — evolution confirmee vers feature-based en 2025_
_Sources : [Dev.to - Atomic Design Relevance 2025](https://dev.to/m_midas/atomic-design-and-its-relevance-in-frontend-in-2025-32e9), [RaftLabs - Next.js Best Practices 2025](https://www.raftlabs.com/blog/building-with-next-js-best-practices-and-benefits-for-performance-first-teams/), [SoftwareMill - Modern Full Stack Next.js 15+](https://softwaremill.com/modern-full-stack-application-architecture-using-next-js-15/)_

### Architecture de Donnees — Multi-Tenant avec PostgreSQL RLS

#### Strategie : Shared Schema + Row-Level Security (RLS)

C'est LA decouverte architecturale cle de cette recherche. PostgreSQL offre un mecanisme natif d'isolation multi-tenant au niveau de la base de donnees :

**Comment ca marche :**
1. Chaque table metier a une colonne `tenant_id`
2. PostgreSQL RLS (Row-Level Security) est active sur ces tables
3. Une politique RLS filtre automatiquement : `WHERE tenant_id = current_setting('app.current_tenant')`
4. Meme si un developpeur oublie un WHERE dans sa requete, **RLS protege les donnees**

**Avantages pour votre SaaS :**
- **Securite au niveau BDD** : L'isolation ne depend pas du code applicatif seul
- **Zero overhead** : Pas de base de donnees separee par tenant (cout et complexite reduits)
- **Performance** : Index sur `tenant_id` pour des requetes rapides
- **Conformite** : Etancheite totale entre entreprises (idee #74 du brainstorming)
- **Simplifie Prisma** : Un middleware Prisma peut injecter le `tenant_id` automatiquement

**Schema conceptuel (simplifie) :**
```sql
-- Toutes les tables metier ont tenant_id
CREATE TABLE quotes (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  tenant_id UUID NOT NULL REFERENCES tenants(id),
  quote_number VARCHAR NOT NULL,        -- Numerotation sequentielle par tenant
  client_id UUID NOT NULL,
  status VARCHAR NOT NULL DEFAULT 'draft',
  total_ht DECIMAL(10,2),
  total_ttc DECIMAL(10,2),
  valid_until DATE,
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW()
);

-- RLS activee
ALTER TABLE quotes ENABLE ROW LEVEL SECURITY;
CREATE POLICY tenant_isolation ON quotes
  USING (tenant_id = current_setting('app.current_tenant')::UUID);
```

_Niveau de confiance : Tres eleve — pattern eprouve, recommande par AWS_
_Sources : [AWS - Multi-Tenant Data Isolation PostgreSQL RLS](https://aws.amazon.com/blogs/database/multi-tenant-data-isolation-with-postgresql-row-level-security/), [TheNile.dev - Multi-Tenant RLS](https://www.thenile.dev/blog/multi-tenant-rls), [TechBuddies - PostgreSQL RLS Multi-Tenant SaaS](https://www.techbuddies.io/2026/01/01/how-to-implement-postgresql-row-level-security-for-multi-tenant-saas/), [SimplyBlock - PostgreSQL Multi-Tenancy RLS](https://www.simplyblock.io/blog/underated-postgres-multi-tenancy-with-row-level-security/)_

### Strategie de Tests — La Pyramide de Tests

#### Approche Recommandee pour votre SaaS

```
         /\
        /  \       E2E Tests (peu nombreux, scenarios critiques)
       / E2E\      Ex: Creer un devis → Convertir en facture → Payer
      /------\
     /        \    Integration Tests (moderement nombreux)
    / Integr.  \   Ex: POST /quotes cree bien un devis en BDD
   /------------\
  /              \ Unit Tests (tres nombreux, rapides)
 /   Unit Tests   \Ex: QuotesService.calculateTotal() retourne le bon montant
/------------------\
```

**Tests unitaires (Jest — natif NestJS) :**
- Chaque service et controller teste isolement
- Mocks pour les dependances (Prisma, services externes)
- Un fichier `.spec.ts` a cote de chaque fichier source
- Couvrir les cas succes ET echec
- **Regle d'or** : Un test = une responsabilite

**Tests d'integration (Supertest + base de test) :**
- Tester les endpoints API reels avec une base PostgreSQL de test
- Verifier la validation des DTOs, les codes HTTP, la pagination
- **TestContainers** : Lancer un PostgreSQL Docker ephemere pour les tests
- Tester les webhooks Stripe avec des payloads simules

**Tests E2E (scenarios critiques uniquement) :**
- Parcours complet : Inscription → Profil → Devis → Facture → Paiement
- Verifier la numerotation sequentielle des factures
- Tester les relances automatiques (BullMQ)
- **Limiter le nombre** : Couteux a maintenir, reserver aux parcours business critiques

**Bonnes pratiques :**
- Tests independants les uns des autres (pas de dependance d'ordre)
- Pas de donnees partagees entre tests
- CI/CD : Tests automatiques a chaque push (GitHub Actions)

_Niveau de confiance : Tres eleve — pyramide de tests largement adoptee_
_Sources : [FreeCodeCamp - NestJS Unit and E2E Testing](https://www.freecodecamp.org/news/nestjs-unit-testing-e2e-testing-guide/), [Toxigon - Testing NestJS 2025](https://toxigon.com/best-practices-for-testing-nestjs-applications), [Dev.to - TestContainers NestJS](https://dev.to/medaymentn/improving-intergratione2e-testing-using-nestjs-and-testcontainers-3eh0), [Amplication - Testing NestJS Best Practices](https://amplication.com/blog/best-practices-and-common-pitfalls-when-testing-my-nestjs-app)_

### Architecture de Deploiement et Operations

#### Pipeline CI/CD avec GitHub Actions

```
┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐
│   Push    │───▶│  Lint +  │───▶│  Build   │───▶│  Deploy  │
│  (main)   │    │  Tests   │    │  Docker  │    │ Staging/ │
└──────────┘    └──────────┘    └──────────┘    │  Prod    │
                                                └──────────┘
```

**Pipeline recommandee :**

1. **Lint & Format** : ESLint + Prettier (coherence du code)
2. **Tests unitaires** : Jest (rapide, bloquant si echec)
3. **Tests d'integration** : Supertest + TestContainers PostgreSQL
4. **Build** : Docker multi-stage (image optimisee)
5. **Deploy staging** : Automatique sur push `develop`
6. **Deploy production** : Sur push `main` (ou approbation manuelle)

**Docker :**
- Dockerfile multi-stage pour NestJS (build → production slim)
- docker-compose pour le dev local (NestJS + PostgreSQL + Redis)
- Images Docker legeres (~100-150MB)

**Environnements :**
- **Local** : docker-compose (PostgreSQL + Redis + NestJS en hot-reload)
- **Staging** : Railway (preview environments automatiques)
- **Production** : Railway (NestJS) + Vercel (Next.js)

_Niveau de confiance : Eleve — pratiques CI/CD standards bien documentees_
_Sources : [NestJS Docs - CI/CD Integration](https://docs.nestjs.com/devtools/ci-cd-integration), [Medium - CI/CD Pipeline NestJS GitHub Actions](https://medium.com/@ghaith.arfaoui34/ci-cd-pipeline-for-a-nest-js-83149c3f9ece), [MxD.codes - Docker CI/CD Next.js GitHub Actions](https://mxd.codes/articles/docker-ci-cd-for-nextjs-with-github-actions)_

### Bibliotheque de Composants UI — shadcn/ui + Tailwind CSS

#### Pourquoi shadcn/ui

shadcn/ui s'impose comme la reference pour les SaaS React/Next.js en 2025-2026 (83,000+ GitHub stars). Ce n'est pas une bibliotheque classique — c'est un **generateur de composants** : vous copiez les composants dans votre projet et vous en devenez proprietaire.

**Avantages pour le projet :**
- **Coherence UI** : Tous les composants partagent le meme design system (couleurs, typographie, espacement) via les tokens Tailwind CSS
- **Accessibilite native (WCAG)** : Construit sur Radix UI, support complet WAI-ARIA, navigation clavier, compatibilite lecteurs d'ecran — zero effort supplementaire
- **Collaboration equipe** : Un nouveau developpeur retrouve des composants standardises et documentes, pas de "chacun fait a sa sauce"
- **Ownership total** : Pas de dependance npm externe, composants personnalisables a 100%, zero vendor lock-in
- **Bundle size minimal** : Seuls les composants utilises sont inclus dans le bundle
- **Tailwind natif** : Coherent avec l'ecosysteme Next.js moderne

**Composants utiles pour votre SaaS :**
- `Table` + `DataTable` : Listes de devis, factures, clients avec tri, pagination
- `Form` + `Input` + `Select` : Formulaires de creation/edition
- `Dialog` + `Sheet` : Modales de confirmation, panneaux lateraux
- `Badge` + `Status` : Statuts visuels (Brouillon, En attente, Paye, Retarde)
- `Card` + `Chart` : Dashboard metriques
- `Toast` : Notifications (devis envoye, paiement recu)
- `Command` : Recherche rapide clients/devis (auto-completion)
- `DropdownMenu` : Actions contextuelles (dupliquer, convertir, supprimer)

**Integration dans la structure frontend :**
```
src/
├── shared/
│   ├── ui/                     ← Composants shadcn/ui (generes via CLI)
│   │   ├── button.tsx
│   │   ├── input.tsx
│   │   ├── table.tsx
│   │   ├── dialog.tsx
│   │   ├── badge.tsx
│   │   ├── card.tsx
│   │   ├── toast.tsx
│   │   └── ...
│   ├── layout/                 ← Composants layout specifiques projet
│   └── forms/                  ← Composants form specifiques projet
```

**Design tokens Tailwind (theming) :**
shadcn/ui utilise des variables CSS pour le theming, ce qui permet :
- Theme clair/sombre (dark mode) sans effort
- Personnalisation des couleurs de marque par entreprise (idee #54 du brainstorming)
- Coherence automatique sur tout le site

_Niveau de confiance : Tres eleve — shadcn/ui est le standard de facto pour les SaaS React/Next.js en 2025-2026_
_Sources : [shadcn/ui Official](https://ui.shadcn.com/docs), [Makers Den - React UI Libs 2025 Comparison](https://makersden.io/blog/react-ui-libs-2025-comparing-shadcn-radix-mantine-mui-chakra), [Dev.to - 5 Best React UI Libraries 2026](https://dev.to/ansonch/5-best-react-ui-libraries-for-2026-and-when-to-use-each-1p4j), [Subframe - React Tailwind Design Systems Startups 2026](https://www.subframe.com/tips/best-react-tailwind-design-systems-for-startups), [Medium - Scalable React Component Library ShadCN](https://medium.com/@sonilamohanty26/how-to-build-a-scalable-react-component-library-with-shadcn-ui-tailwind-css-57ce33a296f1)_

### Schema d'Architecture Global

```
                    ┌─────────────────────────────────────┐
                    │           UTILISATEURS                │
                    │    (Entrepreneurs, Comptables)        │
                    └──────────────┬──────────────────────┘
                                   │
                    ┌──────────────▼──────────────────────┐
                    │         NEXT.JS (Vercel)             │
                    │  ┌─────────────────────────────────┐ │
                    │  │ features/  │ shared/  │ lib/    │ │
                    │  │ quotes     │ ui       │ api     │ │
                    │  │ invoices   │ layout   │ auth    │ │
                    │  │ clients    │ forms    │ hooks   │ │
                    │  │ dashboard  │ feedback │ utils   │ │
                    │  └─────────────────────────────────┘ │
                    └──────────────┬──────────────────────┘
                                   │ REST API (HTTPS)
                    ┌──────────────▼──────────────────────┐
                    │         NESTJS API (Railway)          │
                    │  ┌─────────────────────────────────┐ │
                    │  │         modules/                 │ │
                    │  │  auth │ quotes │ invoices │ ...  │ │
                    │  ├─────────────────────────────────┤ │
                    │  │  common/ (guards, pipes, filters)│ │
                    │  ├─────────────────────────────────┤ │
                    │  │  infrastructure/ (DB, S3, mail)  │ │
                    │  └─────────────────────────────────┘ │
                    └───┬────────┬────────┬────────┬──────┘
                        │        │        │        │
              ┌─────────▼┐ ┌────▼────┐ ┌─▼──────┐ │
              │PostgreSQL │ │ Redis   │ │  S3    │ │
              │ (RLS)     │ │(Upstash)│ │(R2)   │ │
              │ Railway   │ │ BullMQ  │ │ PDFs  │ │
              └───────────┘ └─────────┘ └───────┘ │
                                                   │
                        ┌──────────────────────────┘
                        │
              ┌─────────▼──────┐  ┌──────────────┐
              │  Stripe         │  │  Resend/Brevo │
              │  (Paiements)    │  │  (Emails)     │
              └────────────────┘  └──────────────┘
```

## Implementation Approaches and Technology Adoption

### Conformite Legale Francaise — Facturation Electronique 2026

**ALERTE CRITIQUE** : La reforme de la facturation electronique en France entre en vigueur progressivement a partir du **1er septembre 2026**.

**Calendrier des obligations :**
- **1er septembre 2026** : Obligation de **recevoir** des factures electroniques pour TOUTES les entreprises
- **1er septembre 2026** : Obligation d'**emettre** pour les grandes et moyennes entreprises
- **1er septembre 2027** : Obligation d'**emettre** pour les TPE et micro-entreprises

**Impact sur votre SaaS :**
Meme si vos utilisateurs cibles (TPE) n'auront l'obligation d'emettre qu'en septembre 2027, ils devront **recevoir** des factures electroniques des septembre 2026. Et integrer cette fonctionnalite **des le depart** vous donne un avantage concurrentiel majeur.

**Formats acceptes :**
- **Factur-X** (hybride PDF/A-3 + XML) — le plus adapte pour les TPE (lisible par un humain ET par une machine)
- UBL et CII (formats XML purs)
- PeppolBIS et EDIFACT (interoperabilite)

**Libraries Node.js disponibles :**
- **node-zugferd** : Generation de documents ZUGFeRD/Factur-X conformes, XML embarque dans PDF/A
- **@stafyniaksacha/facturx** : Generation PDF-A/3, extraction et validation XML Factur-X

**Plateforme de depot :**
Les factures devront transiter via une **Plateforme de Dematerialisation Partenaire (PDP)** agreee par l'Etat, ou via le **Portail Public de Facturation (PPF)**. Votre SaaS devra s'interfacer avec l'une de ces plateformes.

**Penalites non-conformite :**
- 15EUR par facture non emise electroniquement (plafond 15,000EUR/an)
- 250EUR par transmission e-reporting manquante (plafond 15,000EUR/an)

_Niveau de confiance : Tres eleve — legislation publiee et calendrier confirme_
_Sources : [Portail Auto-Entrepreneur - Facturation Electronique 2026](https://www.portail-autoentrepreneur.fr/academie/gestion-auto-entreprise/facturation/facturation-electronique-2026), [ClearTax - E-Invoicing France](https://www.cleartax.com/fr/facturation-electronique-france), [Stripe - Factur-X Format France](https://stripe.com/resources/more/factur-x-format-france), [GitHub - node-zugferd](https://github.com/jslno/node-zugferd), [npm - @stafyniaksacha/facturx](https://www.npmjs.com/package/@stafyniaksacha/facturx)_

### Workflow de Developpement et Qualite de Code

**Outils de qualite de code (a configurer des le jour 1) :**

| Outil | Role | Quand |
|-------|------|-------|
| **ESLint** | Analyse statique, detection d'erreurs | A chaque save + pre-commit |
| **Prettier** | Formatage automatique du code | A chaque save + pre-commit |
| **Husky** | Git hooks (pre-commit, pre-push) | A chaque commit |
| **lint-staged** | Lint uniquement les fichiers modifies | Pre-commit (rapide) |
| **Commitlint** (optionnel) | Convention de messages de commit | Pre-commit |
| **TypeScript strict mode** | Typage strict, zero `any` | A la compilation |

**Workflow de commit :**
```
git add . → Husky pre-commit → lint-staged (ESLint + Prettier) → commit
```

Un futur collaborateur qui clone le projet aura **automatiquement** le meme formatage et les memes regles de qualite — zero configuration manuelle.

_Sources : [AmandHimself - Next.js ESLint Prettier Husky](https://amanhimself.dev/blog/setup-nextjs-project-with-eslint-prettier-husky-lint-staged/), [ReactSquad - Next.js 15 Production Setup 2025](https://www.reactsquad.io/blog/how-to-set-up-next-js-15-for-production)_

### Monitoring et Observabilite

**Stack de monitoring recommandee :**

| Outil | Role | Cout |
|-------|------|------|
| **Sentry** | Error tracking + performance (front + back) | Gratuit (5K events/mois) → $26/mois |
| **Pino** (NestJS) | Logging structure JSON | Gratuit (integre) |
| **Vercel Analytics** | Performance front-end, Web Vitals | Inclus dans Vercel Pro |
| **Railway Metrics** | CPU, RAM, reseaux du backend | Inclus dans Railway |
| **Uptime Robot** (optionnel) | Monitoring uptime + alertes | Gratuit (50 monitors) |

**Pourquoi Sentry ?**
- Supporte Node.js (NestJS) ET React (Next.js) dans un seul dashboard
- Source maps pour des stack traces lisibles
- Performance monitoring integre
- Alertes configurables (Slack, email)
- Tier gratuit suffisant pour un MVP

_Niveau de confiance : Eleve — Sentry est le standard pour les startups_
_Sources : [SigNoz - Frontend Cloud Logging Tools 2026](https://signoz.io/comparisons/best-frontend-cloud-logging-tools/), [BayTechConsulting - Sentry Guide 2025](https://www.baytechconsulting.com/blog/sentry-io-comprehensive-guide-2025)_

### Estimation des Couts d'Infrastructure

#### Budget mensuel au lancement (0-100 utilisateurs)

| Service | Plan | Cout/mois |
|---------|------|-----------|
| Vercel (Next.js) | Hobby → Pro | $0 → $20 |
| Railway (NestJS) | Hobby | $5 |
| Railway PostgreSQL | Inclus | ~$5-10 |
| Upstash Redis | Free → Pay-as-you-go | $0 → $5 |
| Cloudflare R2 (stockage) | Free tier | $0 |
| Resend (emails) | Free (100/jour) | $0 |
| Sentry | Free tier | $0 |
| Domaine (.fr) | Annuel | ~$1 |
| **TOTAL** | | **~$11-41/mois** |

#### Budget en croissance (100-1000 utilisateurs)

| Service | Plan | Cout/mois |
|---------|------|-----------|
| Vercel | Pro | $20 |
| Railway (NestJS) | Pro | $20 + usage |
| Railway PostgreSQL | Pro | $20-50 |
| Upstash Redis | Pro | $10 |
| Cloudflare R2 | Usage | $5-10 |
| Resend | Pro | $20 |
| Sentry | Team | $26 |
| **TOTAL** | | **~$120-160/mois** |

**Le modele est tres progressif** : on demarre quasi-gratuitement et les couts augmentent avec le revenu.

_Sources : [Railway Docs - Pricing](https://docs.railway.com/maturity/compare-to-vercel), [SaaS Price Pulse - Railway Pricing 2026](https://www.saaspricepulse.com/tools/railway), [LazyAdmin - Railway vs Vercel](https://lazyadmin.nl/it/railway-vs-vercel-choosing-the-right-hosting-for-your-app/)_

### Evaluation des Risques et Mitigation

| Risque | Probabilite | Impact | Mitigation |
|--------|-------------|--------|------------|
| Non-conformite facture electronique 2026 | Moyenne | Critique | Integrer Factur-X des le MVP, veille legale active |
| Perte de donnees | Faible | Critique | Backups auto PostgreSQL, archivage S3, RLS |
| Vendor lock-in Vercel | Moyenne | Moyen | Next.js deployable partout (Docker), migration possible |
| Prisma vendor lock-in (DSL) | Moyenne | Moyen | Acceptable au demarrage, migration TypeORM possible |
| Surcharge couts Vercel a fort trafic | Faible (au debut) | Moyen | Monitoring des couts, migration Railway si necessaire |
| Complexite croissante du monolithe | Faible (a moyen terme) | Moyen | Modules NestJS bien isoles, extraction possible |
| Faille de securite multi-tenant | Faible | Critique | PostgreSQL RLS + guards NestJS + tests d'isolation |

## Technical Research Recommendations

### Roadmap d'Implementation

```
PHASE 1 — FONDATIONS (Semaines 1-4)
├── Setup projet : NestJS + Next.js + PostgreSQL + Docker Compose
├── Configuration qualite : ESLint, Prettier, Husky, TypeScript strict
├── CI/CD : GitHub Actions (lint + tests + build)
├── Module Auth : JWT + Passport + RBAC (Owner, Admin, Comptable)
├── Multi-tenant : PostgreSQL RLS + TenantGuard
└── Swagger : Documentation auto des premiers endpoints

PHASE 2 — COEUR PRODUIT (Semaines 5-10)
├── Module Companies : Profil entreprise (SIRET, logo, mentions legales)
├── Module Clients : Carnet clients, auto-completion
├── Module Catalog : Produits/prestations, prix, references
├── Module Quotes : Creation devis, cycle de vie, PDF generation
├── Module Invoices : Conversion devis→facture, numerotation sequentielle
├── Frontend : Dashboard, formulaires devis/factures (shadcn/ui)
└── Tests : Unitaires + integration sur chaque module

PHASE 3 — AUTOMATISATION & CONFORMITE (Semaines 11-14)
├── Module Payments : Integration Stripe, webhooks, liens de paiement
├── Module Reminders : BullMQ, relances automatiques, cron jobs
├── Conformite legale : Mentions obligatoires auto, inalterabilite
├── Export : CSV, PDF archives, filtres comptables
├── Factur-X : Generation factures au format electronique
└── Tests E2E : Parcours complets (devis → facture → paiement)

PHASE 4 — POLISH & LANCEMENT (Semaines 15-18)
├── Dashboard metriques : CA, taux conversion, creances
├── Monitoring : Sentry (front + back), logging Pino
├── Securite : Audit, rate limiting, headers de securite
├── Onboarding : Parcours premiere utilisation guide
├── Dark mode : Theme sombre via shadcn/ui tokens
└── Beta testing : Premiers utilisateurs reels
```

### Stack Technologique Final Recommande

| Couche | Technologie | Version |
|--------|-------------|---------|
| **Langage** | TypeScript | 5.x (strict mode) |
| **Frontend** | Next.js | 16.x (App Router) |
| **UI Components** | shadcn/ui + Radix UI | Latest |
| **Styling** | Tailwind CSS | 4.x |
| **State** | React Query (TanStack) | 5.x |
| **Backend** | NestJS | 10.x |
| **ORM** | Prisma | 6.x |
| **BDD** | PostgreSQL | 16+ (avec RLS) |
| **Cache/Queues** | Redis + BullMQ | Via Upstash |
| **Auth** | Passport.js + JWT | NestJS natif |
| **PDF** | Puppeteer + node-zugferd | Factur-X ready |
| **Email** | Resend ou Brevo | API transactionnelle |
| **Paiement** | Stripe | Payment Links + Webhooks |
| **Stockage** | Cloudflare R2 ou S3 | PDFs, logos |
| **Monitoring** | Sentry | Front + Back |
| **CI/CD** | GitHub Actions + Docker | Multi-stage |
| **Front hosting** | Vercel | Pro |
| **Back hosting** | Railway | Pro |
| **Qualite** | ESLint + Prettier + Husky | Pre-commit hooks |
| **Tests** | Jest + Supertest + TestContainers | Pyramide |
| **Documentation** | @nestjs/swagger | OpenAPI auto |

### Competences a Developper

En tant que developpeur intermediaire avec experience React/Next.js et PHP, voici les axes d'apprentissage prioritaires :

| Priorite | Competence | Ressource |
|----------|-----------|-----------|
| 1 | NestJS (modules, guards, interceptors) | docs.nestjs.com |
| 2 | Prisma (schema, migrations, queries) | prisma.io/docs |
| 3 | PostgreSQL RLS (row-level security) | Documentation PostgreSQL |
| 4 | Jest pour NestJS (tests unitaires/integration) | docs.nestjs.com/fundamentals/testing |
| 5 | BullMQ (queues, cron jobs) | docs.nestjs.com/techniques/queues |
| 6 | Factur-X (format facturation electronique) | fnfe-mpe.org/factur-x |

**Bonne nouvelle :** Votre experience PHP Symfony se transpose tres bien vers NestJS (meme philosophie : modules, injection de dependances, decorateurs). Et votre experience React/Next.js est directement applicable.

### Indicateurs de Succes (KPIs)

**Phase MVP :**
- Un utilisateur peut s'inscrire, creer son profil, et generer un devis PDF en < 10 minutes
- Conversion devis → facture en zero re-saisie
- 100% des documents generes conformes a la legislation francaise
- Couverture de tests > 70% sur les modules critiques (quotes, invoices, payments)
- Score Lighthouse > 90 (performance front-end)
- Swagger documente 100% des endpoints API

**Phase Croissance :**
- Temps moyen de creation d'un devis < 3 minutes
- Taux de conversion devis → facture mesurable
- Uptime > 99.5%
- Temps de reponse API < 200ms (p95)

---

_Recherche technique realisee le 2026-02-06 par Mary (Business Analyst) pour Amine._
_Methodologie : Recherche web multi-sources avec verification croisee, 25+ sources consultees et citees._
