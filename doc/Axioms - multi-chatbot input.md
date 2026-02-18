# Kimi K2

Det er et fascinerende og ambitiøst setup du har designet\! Lad mig søge efter de mest moderne best practices inden for AI-agent arkitektur, prompt engineering, og projekt governance for at give dig konkrete forbedringsforslag.  
Lad mig søge efter mere specifik information om GitHub repository struktur og agent governance patterns:  
Lad mig søge efter mere specifik information om prompt engineering patterns og skill versioning:  
Baseret på min forskning kan jeg nu give dig en omfattende analyse og forbedringsforslag til dit axiombaserede AI-agent setup. Dit koncept er banebrydende, men der er flere områder hvor moderne best practices kan styrke robusthed og levedygtighed.

1\. Arkitektur: Fra Statisk til Adaptivt System

Nuværende Styrke  
Dine otte axiomer danner et solidt værdigrundlag (glæde, nytte, kvalitet, sikkerhed, transparens). Dette minder om Agent Skills konceptet fra Anthropic og Spring AI , hvor YAML-frontmatter med metadata muliggør progressiv disclosure.

Forbedringsforslag: Hierarkisk Axiom-System

\`\`\`  
AXIOMS.md (Root Manifest)  
├── Core Axioms (uforanderlige)  
│   ├── 01-joy.md  
│   ├── 02-utility.md  
│   └── ...  
├── Domain Axioms (kontekst-afhængige)  
│   ├── software-development.md  
│   ├── creative-design.md  
│   └── ...  
└── Project-Specific Axioms (genererede)  
    └── {project-name}/axioms.md  
\`\`\`

Hvorfor dette virker: Ifølge forskning i AI-agent arkitektur  bør moderne systemer adskille working memory (kortsigtet) fra persistent knowledge (langsigtet). Dit nuværende setup ligner en "goldfish with amnesia"  \- det starter fra nul ved hver session.

2\. Skill Registry & Versionering

Kritisk Mangel: Ingen versionskontrol af axiomer

Moderne prompt engineering kræver immutable versioning . Når du ændrer et axiom, bør du:

1\. Semantic Versioning: \`axioms/v1.2.3/\`  
   \- Major: Grundlæggende værdiskift  
   \- Minor: Nye domæne-axiomer  
   \- Patch: Præciseringer

2\. Tagging Strategy:  
   \- \`latest\` → aktiv udvikling  
   \- \`stable\` → produktionsprojekter  
   \- \`{project}-snapshot\` → projektspecifikke låse

3\. Schema Validation: Hvert axiom bør have et JSON Schema der validerer at nye skills overholder værdigrundlaget .

Meta-Skill Kvalitetssikring

Din meta-skill til kvalitet bør implementere Frame-Research-Plan-Execute cyklus :

\`\`\`yaml  
\# meta-quality-skill/SKILL.md  
\---  
name: axiom-quality-gate  
description: Validerer at nye skills overholder axioms før de registreres  
allowed-tools: Read, Evaluate, Git  
\---

\#\# Kvalitetsgate Proces

1\. \*\*Frame\*\*: Indlæs alle aktive axiomer fra AXIOMS.md  
2\. \*\*Research\*\*: Analyser skill-modul mod hvert axiom  
3\. \*\*Plan\*\*: Identificer konflikter eller mangler  
4\. \*\*Execute\*\*:   
   \- Godkend hvis compliance \> 95%  
   \- Afvis med begrundelse hvis \< 80%  
   \- Escalér til menneskelig review ellers  
\`\`\`

3\. Axiom-Discovery: Fra Ad-hoc til Systematisk

Din nuværende proces for nye axiomer bør struktureres som en Knowledge Graph :

\`\`\`  
Axiom Discovery Pipeline  
├── Observation (produktionslogs)  
├── Pattern Recognition (clustering af edge cases)  
├── Axiom Candidate Generation  
├── Impact Analysis (hvad bryder det?)  
├── Shadow Mode (test uden at blokere)  
└── Gradual Rollout (canary deployment)  
\`\`\`

Værktøj: Implementér en \`AxiomRegistry\` klasse der fungerer som central autoritet . Denne bør:

\- Registrere alle aktive axiomer med hash-værdier  
\- Spore hvilke projekter der bruger hvilke axiom-versioner  
\- Muliggøre A/B-testning af nye axiomer mod eksisterende

4\. Persistens & Memory Management

To-Lags Arkitektur 

Lag	Type	Formål	Implementering	  
Working Memory	Episodic	Aktiv projektkontekst	Claude Code's native context \+ CLAUDE.md	  
Persistent Memory	Semantic	Axiom-historik, skill-evalueringer, projektartefakter	Vector DB (f.eks. Pinecone) \+ Git LFS	

Kritisk: Dit setup mangler cross-session continuity. Når en session slutter, mister du:  
\- Hvilke skills der fungerede godt/dårligt  
\- Brugerpræferencer fra tidligere projekter  
\- Iterative forbedringsmønstre

Løsning: Agent Memory System 

\`\`\`yaml  
\# .claude/memory/project-{id}.yaml  
session\_history:  
  \- timestamp: 2026-02-18T10:00:00Z  
    skills\_used: \[api-design, testing-strategy\]  
    success\_rate: 0.94  
    user\_feedback: "God struktur, men manglende fejlhåndtering"  
      
axiom\_compliance:  
  joy: 0.89  
  utility: 0.95  
  quality: 0.92  
    
learned\_patterns:  
  \- "Brugeren foretrækker TypeScript fremfor Python til API'er"  
  \- "Sikkerheds-axiomet kræver altid input-validering"  
\`\`\`

5\. GitHub Integration: Repository-First Arkitektur

Repository Struktur (Moderniseret)

\`\`\`  
github.com/din-org/axiom-core/          \# Kerne-axiomer (public)  
github.com/din-org/axiom-skills/        \# Fælles skills (public)  
github.com/din-org/axiom-projects/      \# Projekt-templates (private)  
github.com/din-org/{project-name}/      \# Specifikke projekter  
├── .claude/  
│   ├── skills/          \# Projekt-specifikke skills  
│   ├── memory/          \# Persistens (gitignored)  
│   └── CLAUDE.md        \# Projekt-instruktioner  
├── axioms.lock          \# Låst axiom-version  
└── skills.manifest      \# Registrerede skills med hashes  
\`\`\`

CI/CD Integration 

GitHub Actions bør:  
1\. Validere skill-syntaks mod JSON Schema  
2\. Køre meta-skill evalueringer på nye skills  
3\. Blokere merge hvis axiom-compliance \< threshold  
4\. Auto-generere dokumentation fra SKILL.md filer

6\. Governance & Sikkerhed

Kritisk Risiko: "YOLO Mode" 

Claude Code's "YOLO mode" tillader bypass af tilladelser. Dit setup bør:

1\. Mandatere menneskelig review for:  
   \- Nye axiomer (fundamentale værdiskift)  
   \- Skills der ændrer på sikkerheds-axiomet  
   \- Projekt-guardrails der afviger fra standard

2\. Implementér Audit Trails :  
     
\`\`\`json  
   {  
     "timestamp": "2026-02-18T10:00:00Z",  
     "action": "skill\_created",  
     "actor": "claude-code-agent",  
     "axiom\_version": "v1.2.3",  
     "skill\_hash": "sha256:abc123...",  
     "compliance\_score": 0.96  
   }  
   \`\`\`

3\. Feature Flags : Nye skills bør deployes bag flags (\`skill-{name}-v2\`) så de kan deaktiveres uden redeploy.

7\. Iterativ Forbedring: Data-Driven

Nuværende Gap: Manglende målinger

Din iterative forbedring bør baseres på :

Metrik	Hvordan måles	Handling	  
Skill Success Rate	% af opgaver fuldført uden escalation	\< 90% → review	  
Axiom Compliance	LLM-as-judge evaluering mod hvert axiom	\< 85% → blokering	  
User Satisfaction	Implicit (færre rettelser) \+ explicit feedback	Trending ned → analyse	  
Token Efficiency	Gennemsnitlige tokens per opgave	Stigende → optimering	  
Time-to-Completion	Varighed fra opgavestart til færdig	Outliers → mønsteranalyse	

Feedback Loops

\`\`\`  
Produktion → Observability → Evaluering → Axiom-tuning → Deployment  
     ↑\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_|  
\`\`\`

Værktøj: Brug en platform som Maxim AI  eller LangSmith  til at spore prompt-versioner, køre regressionstests og automatiske rollbacks.

8\. Multi-Agent Orchestration (Fremtidssikring)

Dit nuværende setup antager én agent. Moderne systemer bruger multi-agent orchestration :

\`\`\`  
Supervisor Agent (din nuværende)  
├── Axiom Guardian (validerer compliance)  
├── Skill Forge (skaber nye skills)  
├── Quality Assurance (meta-skill executor)  
└── Project Agent (specifik opgaveudfører)  
\`\`\`

Hver agent har sit eget AXIOMS.md subset:  
\- Guardian: Sikkerhed, Transparens  
\- Forge: Nytte, Kvalitet  
\- QA: Kvalitet, Sikkerhed  
\- Project: Alle, men projektspecifik vægtning

Konklusion: Roadmap til Robusthed

Fase	Fokus	Varighed	  
1\. Foundation	Versionskontrol af axiomer, Skill Registry	2 uger	  
2\. Persistens	Memory-system, cross-session kontinuitet	3 uger	  
3\. Governance	Audit trails, feature flags, CI/CD gates	2 uger	  
4\. Optimering	Metrikker, A/B-testning, auto-rollbacks	4 uger	  
5\. Skalering	Multi-agent, ekstern skill-markedsplads	Løbende	

Dit fundament er solidt, men moderne AI-agent arkitektur kræver state management, versionering og observability for at overgå fra prototype til produktion . Implementér disse patterns gradvist \- start med versionskontrol og persistens, før du bevæger dig mod kompleks multi-agent orchestration.

# ChatGPT

Du har allerede et stærkt udgangspunkt: **værdier (axiomer) → agent-designet projekt → skills \+ guardrails → løbende forbedring i GitHub**. Det, der typisk knækker sådanne setups over tid, er ikke idéen, men **manglende “beviser” for at axiomerne faktisk bliver overholdt** (i CI, i runtime og i ændringsstyring), samt **agent-sikkerhed** (tool access, prompt injection, supply chain).

Nedenfor er et sæt forbedringer, der matcher moderne best practice for agentiske udviklingsplatforme (plan/execute/verify), AI governance og sikker softwareleverance. ([developers.googleblog.com](https://developers.googleblog.com/build-with-google-antigravity-our-new-agentic-development-platform/?utm_source=chatgpt.com))

---

## **Den vigtigste designregel: Axiomer skal kunne håndhæves og auditeres**

**Målet:** Flyt AXIOMS.md fra “inspirerende tekst” til et **policy-system med målinger**, så du kan svare ja/nej på: *overholder projektet axiomerne – og hvor er evidensen?*

Det betyder i praksis:

1. **Maskinlæsbar policy** (kontrakter)  
2. **Evals \+ gates i CI** (regression)  
3. **Runtime-guardrails** (least privilege, kontrolpunkter, kvoter, logging)

---

## **Topprioriterede forbedringer (høj effekt først)**

### **1\) Split AXIOMS.md i “menneske \+ maskine”**

**Problem:** Tekst alene driver drift og fortolkning over tid.  
**Løsning:** Behold AXIOMS.md som “manifest”, men generér en `axioms.policy.yml` (eller `json`) med faste felter.

**Forslag til policy-felter (minimum):**

* `axiom_id`, `intent`, `non_goals`  
* `must`, `must_not` (checkbare regler)  
* `risk_level` \+ “stop conditions”  
* `required_evidence` (hvilke tests/logs skal findes)  
* `waiver_process` (hvornår må man afvige, og hvordan dokumenteres det)

Det gør det muligt at skrive automatiske checks: “har projektet dokumenteret X? kører eval Y? er guardrail Z slået til?”

---

### **2\) Gør “verify” til en hård gate i pipeline (ikke en høflig anbefaling)**

Google Antigravity beskriver netop agent-flowet som **planlæg → eksekvér → verificér**; din robusthed kommer af at gøre “verify” uomgængelig. ([developers.googleblog.com](https://developers.googleblog.com/build-with-google-antigravity-our-new-agentic-development-platform/?utm_source=chatgpt.com))

**Konkrete gates:**

* *Plan-gate:* agenten må ikke skrive kode før den har produceret en plan i et fast format  
* *Diff-gate:* agenten må kun ændre filer inden for en allowlist (fx `src/`, ikke `.github/` uden særskilt godkendelse)  
* *Test-gate:* agenten skal køre tests/lint og gemme output som artefakt  
* *Policy-gate:* et “axiom compliance check” skal være grønt før merge

---

### **3\) Byg et egentligt eval-harness for skills (prompt-regression \+ “golden tasks”)**

**Problem:** Skills degenererer langsomt, især når du tilføjer nye axiomer eller nye toolchains.  
**Løsning:** Lav en mappe med “golden” scenarier og forventede outputs/egenskaber.

**Eval-typer:**

* **Deterministiske checks**: schema-validering, lint, statiske constraints  
* **Metamorfiske tests**: samme opgave med små variationer må ikke ændre kritiske egenskaber  
* **Adversarial tests**: prompt injection-forsøg, data leakage, “excessive agency”  
* **Budget-tests**: token/omkostningsloft, runtime-loft (OWASP “unbounded consumption”) ([OWASP Gen AI Security Project](https://genai.owasp.org/llm-top-10/?utm_source=chatgpt.com))

---

### **4\) Formalisér “skill-kontrakter” og review-rubric (din meta-skill bliver stærkere)**

Anthropic skelner bl.a. mellem problem-first vs tool-first skills og lægger vægt på tydelige mønstre og evaluering. ([resources.anthropic.com](https://resources.anthropic.com/hubfs/The-Complete-Guide-to-Building-Skill-for-Claude.pdf?hsLang=en&utm_source=chatgpt.com))

**Gør hver skill til en lille “pakke” med:**

* `README.md` (purpose, inputs/outputs, begrænsninger)  
* `contract.schema.json` (hvilket format skillen lover)  
* `threat-model.md` (minitrusselmodel)  
* `evals/` (tests)  
* `changelog.md` (hvad ændrede sig og hvorfor)

Din meta-skill kan så køre et fast rubric:

* klarhed (hvad gør den / ikke gør)  
* korrekthed (tests \+ evals)  
* sikkerhed (OWASP LLM-risici)  
* drift (observability, timeouts, retries)  
* vedligehold (ejerskab, versionering)

---

### **5\) Agent-sikkerhed efter OWASP LLM Top 10 (2025/1.1): mindst privilegium \+ output-kontrol**

OWASP’s LLM Top 10 er et godt “minimumssæt” af risici at designe imod: prompt injection, insecure output handling, excessive agency, leakage, supply chain, consumption osv. ([owasp.org](https://owasp.org/www-project-top-10-for-large-language-model-applications/?utm_source=chatgpt.com))

**Tre guardrails der giver mest robusthed:**

1. **Tool-wrappers med allowlists**  
   * fx “git” kun via sikre subcommands, ingen vilkårlige shell-kommandoer  
2. **Human-in-the-loop på destruktive handlinger**  
   * sletning, force-push, secrets, `.github/`, prod-konfig  
3. **Output-validering før handling**  
   * alt der rammer filer, netværk, økonomi eller eksekvering skal schema-valideres og sanitizes (OWASP “insecure output handling”) ([owasp.org](https://owasp.org/www-project-top-10-for-large-language-model-applications/?utm_source=chatgpt.com))

*Note:* Agentiske toolchains kan få reelle sikkerhedshuller (fx MCP-komponenter), så behandl alle connectors/servers som “rigtig software” med versionering, patching og hardening. ([TechRadar](https://www.techradar.com/pro/security/anthropics-official-git-mcp-server-had-some-worrying-security-flaws-this-is-what-happened-next?utm_source=chatgpt.com))

---

### **6\) Supply chain-hærdning af dine “bootstrap artefakter” (SLSA \+ signering)**

Når din agent bootstrapper projekter, bliver templates, actions, dependencies og tool-plugins en del af angrebsfladen.

**Minimumsbest practice:**

* Pin GitHub Actions til commit-SHA (ikke `@v3`)  
* Generér SBOM (fx CycloneDX) og kør dependency scanning  
* Stram branch protection \+ required checks  
* Arbejd mod SLSA-niveauer som en modenhedsstige (især provenance) ([SLSA](https://slsa.dev/spec/v1.0/levels?utm_source=chatgpt.com))  
* Signér artefakter i CI med Sigstore/cosign, så du kan verificere integritet ved deploy ([Sigstore](https://docs.sigstore.dev/quickstart/quickstart-ci/?utm_source=chatgpt.com))

---

### **7\) Observability som first-class: “hvad gjorde agenten – og hvorfor?”**

Levedygtighed handler om drift: du skal kunne debugge, forklare og forbedre uden gæt.

**Log som standard:**

* plan (structured), beslutningspunkter, værktøjs-kald, diff-resumé  
* policy-check-resultater (axiom compliance)  
* budget (tid/tokens/omkostning)  
* “incident breadcrumbs” (hvad gik galt, hvilken guardrail stoppede det)

Det er ikke bare telemetry – det er **dokumentation af ansvarlighed**.

---

### **8\) Vendor-robusthed: adapter-lag for modeller \+ “capability matrix”**

Hvis du binder skills tæt til én platform, bliver du sårbar ved ændrede priser, policy, modeladfærd eller features.

**Gør det simpelt:**

* Definér et internt interface: `LLMProvider`, `ToolRunner`, `MemoryStore`  
* Hav en `capability-matrix.md`: hvilke skills kræver hvilke capabilities (function calling, web, sandbox, osv.)  
* Kør dine evals på mindst 2 “providers” en gang imellem (bare for at opdage lock-in tidligt)

---

### **9\) Ændringsstyring for axiomer: semver \+ “axiom migration notes”**

Når du opdager nye axiomer, ændrer du implicit *hele systemets* kontrakt.

**Best practice:**

* Versionér axiomer (`AXIOMS_VERSION`) og brug semver:  
  * **MAJOR:** nyt axiom eller ændret fortolkning der kan bryde eksisterende projekter  
  * **MINOR:** præciseringer  
  * **PATCH:** rettelser/typos  
* Kræv “migration notes” ved MAJOR: hvilke skills/projekter påvirkes, og hvilke evals skal opdateres

---

### **10\) Align med etablerede governance-rammer (uden at blive tung)**

Du kan bruge **ISO/IEC 42001** som “management system”-skabelon for ansvarlig AI (politik, risici, livscyklus, leverandører) og **NIST AI RMF** som praktisk risikoloop (Govern/Map/Measure/Manage). ([iso.org](https://www.iso.org/standard/42001?utm_source=chatgpt.com))

**Lav en let mapping:**

* Axiomer → *policy & governance* (42001 / NIST “Govern”)  
* Project bootstrap → *lifecycle & controls* (Map/Manage)  
* Skills \+ evals → *Measure (TEVV: test/eval/validation/verification)*  
* Telemetry \+ incidents → *continual improvement*

Det giver dig “enterprise-grade” rygdækning uden at du behøver implementere bureaukrati.

---

## **Repo-struktur der understøtter alt ovenstående (praktisk og skalerbar)**

Et forslag, der gør policy/evals/guardrails “svære at omgå”:

* `/axioms/`  
  * `AXIOMS.md`  
  * `axioms.policy.yml`  
  * `versions/`  
* `/skills/skill-name/`  
  * `README.md`  
  * `contract.schema.json`  
  * `threat-model.md`  
  * `evals/`  
  * `changelog.md`  
* `/templates/` (project bootstrap)  
* `/guardrails/` (tool wrappers, allowlists, budgets)  
* `/eval-harness/` (runner \+ datasets \+ scoring)  
* `/.github/workflows/` (required checks, provenance, signing)  
* `/docs/operating-model/` (incident, waivers, review process)

---

## **Den kritiske blind vinkel at undgå**

Når man har axiomer \+ agent \+ skills, er den klassiske fælde at tro, at “det er indbygget i kulturen”. Over tid bliver det i stedet “indbygget i hukommelsen” – og så forsvinder det ved travlhed, nye projekter eller nye platformfeatures.

Robusthed kommer af, at **overholdelse bliver en egenskab ved systemet** (policy \+ evals \+ gates \+ logging) og ikke en egenskab ved din disciplin.

---

# Claude

Godt, det ændrer billedet en smule. Lad mig justere anbefalingerne ud fra det.

---

## **Opdateret arkitektur med et centralt axiom-repo**

Fordi du er den eneste axiom-forfatter, forsvinder den største governance-risiko. Men det introducerer en anden: **du er et single point of failure**. Dit axiom-repo bør derfor være designet til at overleve og forklare sig selv uden dig.

### **Axiom-repo'et som hjerte**

Det bør indeholde mere end bare AXIOMS.md. Tænk på det som et levende dokument-system:

**AXIOMS.md** – selve aksiomerne med versionering og dato for hver ændring.

**AXIOM\_RATIONALE.md** – *hvorfor* hvert aksiom eksisterer, hvilke situationer der udløste det, og hvad det erstatter eller præciserer. Dette er afgørende for at en AI-agent kan fortolke korrekt i nye kontekster.

**AXIOM\_TESTS.md** – konkrete eksempler: "Dette projekt overholder aksiom 3" og "Dette ville *bryde* aksiom 3". Uden dette fortolker agenten ud fra mønstergenkendelse, ikke intention.

**AXIOM\_CHANGELOG.md** – ikke bare git-historik, men menneskelig begrundelse for hver ændring.

### **Kernskill til axiom-kvalitet**

Din ide om en kernskill til kvalitetsvurdering af nye aksiomer er præcis det rigtige. Den bør specifikt tjekke for:

**Konsistens** – modsiger det eksisterende aksiomer, direkte eller implicit? **Redundans** – er det allerede dækket af et eksisterende aksiom i en anden formulering? **Dækningsgrad** – er det specifikt nok til at guide beslutninger, eller er det så abstrakt at det ikke tilføjer reel styringsevne? **Krydsdomæne-gyldighed** – fungerer aksiomerne på tværs af *alle* dine projekttyper, altså både software og artikler?

Det sidste punkt er særligt vigtigt for dig, fordi dit setup er usædvanligt bredt. Et aksiom der er intuitivt i en software-kontekst kan være meningsløst eller direkte skadeligt som guideline for en artikel.

---

## **Fordi projekterne er meget forskellige**

Multi-repo med heterogene projekttyper stiller særlige krav til, hvordan agenten oversætter aksiomerne til projekt-specifikke guardrails. Her er den centrale risiko: **generelle aksiomer fortolkes for smalt** fordi agenten primært har set software-projekter.

En god løsning er at indføre et mellemlag – **projektskabeloner per domæne** – i dit axiom-repo. Ikke fuldstændige templates, men et kort dokument for hvert domæne (software, artikel, research, design, osv.) der beskriver, hvad hvert aksiom konkret *betyder* i det domæne. Agenten bruger dette som fortolkningslag frem for at udlede det selv hver gang.

---

## **Den vigtigste enkeltting du kan gøre nu**

Skriv AXIOM\_RATIONALE.md. Ikke fordi det er teknisk nødvendigt i dag, men fordi det tvinger dig til at eksternalisere den tavse viden du selv har om *hvorfor* aksiomerne er som de er. Det er den viden der ellers kun lever i dit hoved, og som bestemmer om systemet er robust eller skrøbeligt på lang sigt.

Vil du have hjælp til at designe strukturen for axiom-repo'et konkret?

# Gemini

Dit setup fanger præcis det skift, vi ser her i 2026, hvor vi bevæger os fra simple chat-assistenter til ægte agent-orkestrering. At bygge fundamentet på et stærkt, dansk værdigrundlag via dit AXIOMS.md sikrer, at alt fra komplekse kodebaser til forretningsudvikling og rådgivningsprojekter afspejler en konsekvent høj standard og en rød tråd.

Når man bygger arkitektur på dette niveau, er den største udfordring ikke at få agenterne til at *læse* axiomerne, men at forhindre "agentic drift" – altså at agenterne over tid eller under komplekse opgaver glemmer at efterleve dem.

Her er de mest etablerede best practices for at fremtidssikre, forbedre og robustgøre dit setup på tværs af Claude Code og Google Antigravity:

### **1\. Operatisering af Axiomer (Fra Filosofi til Guardrails)**

Bløde værdier som "glæde", "nytte" og "transparens" er fremragende ledestjerner, men de skal gøres maskinlæsbare og testbare for at fungere som sande guardrails.

* **Constitutional Evaluation i CI/CD:** I stedet for kun at bruge AXIOMS.md ved bootstrapping, bør din meta-skill implementeres som en uafhængig "Reviewer Agent" i dine GitHub Actions. Hver gang en agent (via Antigravity eller Claude Code) åbner en Pull Request – uanset om det er kode, et forretningskoncept eller data-dokumentation – skal meta-skill'en systematisk score resultatet ud fra de 8 axiomer og blokere for merge, hvis kvaliteten fejler.  
* **Kontekst-Broen:** Claude Code anvender automatisk Claude.md filer til at forstå lokal kontekst. Dit bootstrap-script bør dynamisk generere en projekt-specifik Claude.md ud fra dit overordnede AXIOMS.md, så Claude-agenten altid har axiomerne pre-loadet i terminalen, uden at de skal skrives i hver prompt.

### **2\. Standardisering af Skills via Model Context Protocol (MCP)**

For at sikre, at dit system overlever på tværs af platforme og kan håndtere projekter, der *ikke* er software, er Model Context Protocol (MCP) det vigtigste bindeled.

* **Pak dine Skills som MCP-servere:** Både Claude Code og Google Antigravity understøtter MCP. Ved at bygge dine skills og din meta-skill som MCP-servere, gør du dem platformsuafhængige.  
* **Integration med non-software:** MCP gør det muligt for dine agenter at trække kontekst fra eksterne værktøjer (Google Drive, Notion, Slack). Det betyder, at din AI kan bruge AXIOMS.md til at validere "transparens" i et strategidokument eller en rapport lige så let, som den tjekker en Python-fil.

### **3\. Udnyttelse af Antigravitys "Agent Manager" og Artifacts**

Google Antigravity er bygget præcis til den type parallelle workflows, du har etableret. Du bør udnytte platformens unikke features til at styrke transparensen.

* **Parallel Orkestrering:** Brug Antigravitys "Agent Manager" (Mission Control) til at adskille udførsel og kontrol. Lad én agent bygge selve projektet, mens en anden agent kører parallelt i baggrunden med din meta-skill for løbende at evaluere arbejdsprocessen mod dine axiomer.  
* **Verificering via Artifacts:** Antigravity lader agenterne generere verificerbare "Artifacts" – ikke bare tekst, men også automatiserede testkørsler og optagelser via dens indbyggede Browser Agent. Du kan instruere din meta-skill i at køre automatiserede "vibe checks" gennem Browser Agenten for konkret at validere "glæde" og "nytte" i brugergrænsefladen eller slutproduktet.

### **4\. Robusthed ved Opdagelse af Nye Axiomer og Skills**

Din proces for at iterere på skills og opdage nye axiomer er et afgørende feedback-loop, men det introducerer en risiko for, at nye regler utilsigtet skaber konflikter i eksisterende projekter.

* **Automated Impact Analysis:** Før et nyt axiom eller en opdateret skill rulles ud globalt, bør du etablere et automatiseret sandbox-workflow. Lad Claude Code tjekke en kopi af 3-4 eksisterende (og vidt forskellige) GitHub-projekter ud, implementere de nye regler, og køre din fulde test-suite. Hvis det nye axiom sænker "kvalitets"-scoren i et ældre projekt, fanges det før udrulning.  
* **Skill Versioning:** Behandl dine skills og prompts som produktionskode. Brug semantisk versionering i dit GitHub repository for alle skills, så et projekt altid bootstrapper med en låst, stabil version af en skill, medmindre du eksplicit beder om at opgradere.

Vil du have, at vi dykker ned i, hvordan du rent teknisk pakker din nuværende meta-skill ind i en MCP-server, så den kan kaldes gnidningsløst af både Claude Code og Antigravitys agenter?

