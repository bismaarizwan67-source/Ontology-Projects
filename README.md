# AI Platform Knowledge Base Ontology

This repository contains a formal Web Ontology Language (OWL) specification designed to model the ecosystem of modern conversational and generative AI platforms. It establishes structural relationships between core architectural layers, including hardware infrastructure, deep learning models, software applications, subscription services, and engineering roles.

# Ontology Overview

* **Ontology IRI:** `[http://www.semanticweb.org/rc/ontologies/2026/3/untitled-ontology-18](http://www.semanticweb.org/rc/ontologies/2026/3/untitled-ontology-18)`
* **Format:** OWL 2 XML (Structural Specification)
* **Namespace Prefixes:**
* `schema:` -> `[http://schema.org/](http://schema.org/)`
* `owl:` -> `[http://www.w3.org/2002/07/owl#](http://www.w3.org/2002/07/owl#)`
* `rdf:` -> `[http://www.w3.org/1999/02/22-rdf-syntax-ns#](http://www.w3.org/1999/02/22-rdf-syntax-ns#)`
* `xsd:` -> `[http://www.w3.org/2001/XMLSchema#](http://www.w3.org/2001/XMLSchema#)`
# Core Architectural Taxonomy (Classes)

The schema defines a multi-layered structure mapping infrastructure directly to end-user capabilities:

# 1. Core Classes & Concepts

* **`ConversationalAIPlatform`**: Software platforms enabling natural language interaction between humans and machine learning instances.
* **`LargeLanguageModel`**: Deep neural networks trained on large text corpora (with specialized sub-classes `AutoregressiveModel` and `EncoderOnlyModel`).
* **`AICapability`**: Functional features provided to users, including `NaturalLanguageProcessing`, `ImageGeneration`, `CodeInterpreter`, and `WebSearchIntegration`.
* **`Infrastructure`**: Physical and cloud compute resources including `CloudProvider` units and `GPUCluster` environments.
* **`SubscriptionTier`**: Business accessibility layers mapping to a `FreeTier`, `PaidService`, or `PremiumTier`.
* **`Audience`**: Intended user types segmented into `SoftwareDeveloper`, `PromptEngineer`, and `Student`.

# 2. Schema.org Extensions

The ontology integrates and builds upon foundational upper-level terms from **Schema.org**:

* `schema:Organization` (extended by `AIResearchLab`)
* `schema:CreativeWork` (extended by models, vectors, and outputs)
* `schema:SoftwareApplication`
* `schema:Dataset` (extended by `TrainingDataset` and `RealTimeWebIndex`)

# Logical Properties & Schema Relationships

# Object Properties (Semantic Links)

* **Model Provenance:** `isFineTunedFrom` (Functional Property mapping specialized variants to base LLMs), `isTrainedOn` / `isUsedForTrainingOf` (Asymmetric relations linking models to datasets).
* **Execution & Capabilities:** `utilizesModel`, `executesLanguage` (mapping Code Interpreters to target environments), and `powersVisuals` (linking Diffusion Models or Vision Transformers to generation layers).
* **Infrastructure Layering:** `isOperatingSystemOf` (binding cluster layers to AI applications) and `isProvidedBy` (linking infrastructure back to cloud platforms).

# Data Properties (Attributes)

The taxonomy enforces exact data types for semantic metadata properties:

* `hasContextWindow` ($\to$ `xsd:integer`) — Maximum token tracking limits.
* `price` ($\to$ `xsd:float`) — Cost metrics for premium access subscription levels.
* `isBetaFeature` ($\to$ `xsd:boolean`) — Feature deployment tracking flag.
* `softwareVersion`, `datasetSize`, `refreshRate` ($\to$ `xsd:string`) — Version compliance data.

# Instantiated Knowledge Graph (Sample Individuals)

The ontology includes pre-defined individuals modeling verified real-world relationships:

```
[OpenAI] (AIResearchLab)
   └── isAuthorOf ──> [CommonCrawlData] (TrainingDataset)
   └── providesAccess ──> [ChatGPTInst] (ConversationalAIPlatform)
                                │
                                ├── utilizesModel ──> [GPT4o] (AutoregressiveModel)
                                └── executesLanguage ──> [JavaScript] (ComputerLanguage)

[HuggingFace] (Organization)
   └── schema:provider ──> [ClinicalGPT] (FineTunedModel)
                                │
                                └── isFineTunedFrom ──> [GPT4o]

```

# Project Team Instance Mapping

The model defines a closed project team (`ProjectTeam`) mapped explicitly via an `owl:oneOf` enumeration layer for specific engineering nodes:

* **`AimenDev`**: `SoftwareDeveloper` writing application code in `JavaScript`.
* **`BismaDev`**: `SoftwareDeveloper` specializing directly in `NLPCapability`.
* **`UmmamahDev`**: `SoftwareDeveloper` specializing in `ReactFramework` development and platform configurations.

# Usage & Integration

This `.owl` file can be opened directly within **Protégé**, or integrated natively inside semantic pipeline environments using programmatic tools:

