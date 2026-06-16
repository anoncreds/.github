# Hyperledger AnonCreds

Welcome to **Hyperledger AnonCreds**, a verifiable credentials project of the [Linux Foundation Decentralized Trust](https://www.lfdecentralizedtrust.org).

Hyperledger AnonCreds is an opinionated implementation of verifiable credentials using Zero Knowledge Proofs (ZKPs) to maximize privacy and unlinkability in the sharing of verifiable data.

You can find more information on the [Hyperledger AnonCreds project page](https://www.lfdecentralizedtrust.org/projects/hyperledger-anoncreds).

<!-- TODO: Add a Hyperledger AnonCreds banner image here -->
<!-- ![Hyperledger AnonCreds Banner](link-to-banner-image) -->

## What is Hyperledger AnonCreds?

Hyperledger AnonCreds is an opinionated implementation of verifiable credentials using Zero Knowledge Proofs (ZKPs) to maximize privacy and unlinkability in the sharing of verifiable data. Anoncreds v1 is based on CL Signatures, while v2 is flexible enough to support different underlying signature schemes.

The open source AnonCreds v1 implementations (here in Hyperledger Indy and here in Hyperledger AnonCreds) provide capabilities that many see as important for digital identity use cases in particular, and verifiable data in general. These features include:

- A full implementation of the Layer 3 verifiable credential “Trust Triangle” of the Trust over IP Model.
- Complete flows for issuing verifiable credentials (Issuer to Holder), and requesting, generating and verifying presentations of verifiable claims (Holder to Verifier).
- Fully defined data models for all of the objects in the flows, including verifiable credentials, presentation requests and presentations sourced from multiple credentials.
- Fully defined applications of cryptographic primitives.
- The use of Zero Knowledge Proofs (ZKPs) in the verifiable presentation process to enhance the privacy protections available to the holder in presenting data to verifiers, including:
  - Blinding issuer signatures to prevent correlation based on those signatures.
  - Holder binding based on the use of unrevealed identifiers to prevent correlation based a holder identifier.
  - Selective disclosure in the generation of presentations to minimize data sharing to that required for the business need.
  - The use of predicate proofs to reduce the sharing of PII and potentially correlating data, especially dates (birth, credential issuance/expiry, etc.).
  - A revocation scheme that proves a presentation is based on credentials that have not been revoked by the issuers without revealing correlatable revocation identifiers.

The AnonCreds working group produced the AnonCreds v1.0 specification that describes the existing implementation minus any dependency on the Hyperledger Indy ledger ("ledger-agnostic"). AnonCreds v2.0 has been started that adds new capabilities while retaining the core features of AnonCreds v1 (listed above). v2 includes features such as replacing CL Signatures with BBS Signatures (and other schemes), and includes a more scalable revocation scheme. Those participating in this Working Group define the direction of future versions of Hyperledger AnonCreds.

## Architecture

Hyperledger AnonCreds is organized around the core roles and flows of verifiable credential exchange:

- **Issuer** — Creates schemas and credential definitions, issues credentials to holders, and manages revocation data.
- **Holder** — Receives credentials, stores them, creates presentations, and controls what data is disclosed to verifiers.
- **Verifier** — Requests presentations, verifies proofs, and checks whether presented credentials satisfy the requested claims.
- **Specification** — Defines the data models, cryptographic primitives, presentation formats, revocation model, and ledger-agnostic behavior.
- **Implementations** — Provide libraries and tooling for issuing, holding, presenting, verifying, and revoking AnonCreds credentials.

Together, these components support privacy-preserving verifiable credential exchange with selective disclosure, predicate proofs, and unlinkability.

## What Hyperledger AnonCreds Enables

Hyperledger AnonCreds allows developers and ecosystems to:

- Issue and verify privacy-preserving verifiable credentials
- Use zero-knowledge proofs for selective disclosure
- Prove predicates without revealing underlying values
- Reduce correlation across credential presentations
- Support ledger-agnostic credential exchange
- Build credential workflows that protect holder privacy
- Implement revocation without revealing correlatable revocation identifiers
- Use AnonCreds with Indy, Aries, Credo, and other decentralized identity ecosystems

Example use cases include:

- Digital identity wallets
- Education and workforce credentials
- Age verification
- KYC and compliance workflows
- Government digital identity services
- Healthcare credential exchange
- Privacy-preserving access control
- Verifiable organization and membership credentials
- Cross-ecosystem decentralized identity interoperability

## Repositories

| Repository | Description |
|---|---|
| [**anoncreds**](https://github.com/anoncreds/anoncreds) | Top-level project repository with project overview, governance references, contribution guidance, maintainers, security policy, and project documentation. |
| [**anoncreds-rs**](https://github.com/anoncreds/anoncreds-rs) | Rust implementation of AnonCreds v1.0. |
| [**anoncreds-v2-rs**](https://github.com/anoncreds/anoncreds-v2-rs) | Rust implementation work for AnonCreds v2.0 and anonymous credential exchange 2.0. |
| [**anoncreds-spec**](https://github.com/anoncreds/anoncreds-spec) | Source repository for the AnonCreds v1.0 specification. |
| [**anoncreds-spec-v2**](https://github.com/anoncreds/anoncreds-spec-v2) | Source repository for AnonCreds v2.0 specification work. |
| [**anoncreds-clsignatures-rs**](https://github.com/anoncreds/anoncreds-clsignatures-rs) | Rust CL Signatures implementation used by AnonCreds v1.0. |
| [**anoncreds-methods-registry**](https://github.com/anoncreds/anoncreds-methods-registry) | Registry of AnonCreds object methods for registering and resolving AnonCreds objects on Verifiable Data Registries. |

## Resources

The following documents will help you understand Hyperledger AnonCreds' vision, workflows, specifications, and community.

- The [Hyperledger AnonCreds project page](https://www.lfdecentralizedtrust.org/projects/hyperledger-anoncreds) gives an overview of the project, documentation, videos, and community links.
- The [Hyperledger AnonCreds GitHub organization](https://github.com/anoncreds) contains the AnonCreds project repositories.
- The [anoncreds repository](https://github.com/anoncreds/anoncreds) contains the top-level project overview and project files.
- The [anoncreds-rs repository](https://github.com/anoncreds/anoncreds-rs) contains the Rust implementation of AnonCreds v1.0.
- The [anoncreds-v2-rs repository](https://github.com/anoncreds/anoncreds-v2-rs) contains implementation work for AnonCreds v2.0.
- The [AnonCreds v1.0 specification](https://anoncreds.github.io/anoncreds-spec/) describes the ledger-agnostic AnonCreds specification.
- The [anoncreds-spec repository](https://github.com/anoncreds/anoncreds-spec) contains the source documents for the AnonCreds open specification.
- The [AnonCreds Methods Registry](https://anoncreds.github.io/anoncreds-methods-registry/) lists methods for registering and resolving AnonCreds objects on Verifiable Data Registries.
- The [AnonCreds Working Group wiki](https://lf-hyperledger.atlassian.net/wiki/spaces/ANONCREDS/pages/20291468/AnonCreds+Working+Group) provides working group information and links to specifications and implementations.
- Watch Hyperledger AnonCreds videos through the [official Hyperledger AnonCreds YouTube playlist](https://www.youtube.com/playlist?list=PL0MZ85B_96CG36a8kancuItxx4RtZWG1_).
- Watch AnonCreds working group recordings through the [AnonCreds Working Group Meetings YouTube playlist](https://www.youtube.com/playlist?list=PL0MZ85B_96CE4pz8_S_CcQgbtAqL9gGKk).
- Watch the workshop: [Hyperledger AnonCreds Workshop: Using ZKP Verifiable Credentials Everywhere](https://www.youtube.com/watch?v=1RrJky42dvg).
- Watch the webinar: [Next-Gen Digital Credentials: AnonCreds v2, Powered By BBS Signatures](https://www.youtube.com/watch?v=fElVhhBviUU).
- Our [Code of Conduct](https://www.lfdecentralizedtrust.org/code-of-conduct) describes expected behavior across the LFDT community.
- For security related issues, please follow the security policy in the relevant repository. Do not post security related content, issues, or discussions publicly in any repository.

## How to contribute

Hyperledger AnonCreds welcomes developers, cryptographers, identity architects, wallet builders, organizations, and privacy advocates interested in verifiable credentials and zero-knowledge proof-based digital identity.

Good ways to get started:

1. Review the [anoncreds repository](https://github.com/anoncreds/anoncreds).
2. Explore the [AnonCreds Working Group wiki](https://lf-hyperledger.atlassian.net/wiki/spaces/ANONCREDS/pages/20291468/AnonCreds+Working+Group).
3. Join community discussions on [LFDT Discord](https://discord.lfdecentralizedtrust.org). Channel: #anoncreds
4. Attend community meetings. AnonCreds working group meetings are open to everyone. These meetings are a good place to ask questions, discuss specification work, and learn how to contribute.

| Meeting | Calendar Link |
|---|---|
| AnonCreds Working Group Meeting |  https://zoom.us/j/92023385582?pwd=bb7CFdbibQKGTkqKnXzEi3xhbbi1du.1|

Past meeting recordings and presentations can be accessed through:

- [LFX Individual Dashboard](https://openprofile.dev/)
- [LFDT Meeting Calendar](https://zoom-lfx.platform.linuxfoundation.org/meetings/lf-decentralized-trust)
- [Hyperledger AnonCreds YouTube playlist](https://www.youtube.com/playlist?list=PL0MZ85B_96CG36a8kancuItxx4RtZWG1_)
- [AnonCreds Working Group Meetings YouTube playlist](https://www.youtube.com/playlist?list=PL0MZ85B_96CE4pz8_S_CcQgbtAqL9gGKk)

For larger changes, please open an issue first so the community can discuss the design before implementation.

## Current Status

Hyperledger AnonCreds is an **incubating** LFDT project. The project includes the AnonCreds v1.0 specification and implementation work, as well as ongoing AnonCreds v2.0 work focused on new capabilities such as flexible signature schemes and more scalable revocation.

## License

Hyperledger AnonCreds code repositories are generally licensed under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0), unless otherwise noted in a specific repository.

Specification work may operate under the [Community Specification License v1.0](https://github.com/anoncreds/anoncreds-spec/blob/main/LICENSE).
