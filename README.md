# Anthos Config Management – Policy Controller Library

## Contents
- [Background](#background)
- [Bundles](#bundles)
- [Usage](#usage)

## Background

[Policy Controller](https://cloud.google.com/anthos-config-management/docs/concepts/policy-controller), part of [Anthos Config Management](https://cloud.google.com/anthos-config-management/), is a Kubernetes [dynamic admission controller](https://kubernetes.io/docs/reference/access-authn-authz/extensible-admission-controllers/) that checks, audits, and enforces your clusters' compliance with policies related to security, regulations, or arbitrary business rules.

Policy Controller is based on the open source [Open Policy Agent Gatekeeper](https://github.com/open-policy-agent/gatekeeper) project. Gatekeeper policies are defined using two separate resource types: `Constraint`s and `ConstraintTemplate`s. Having two distinct resource types allows for separation of policy **definition** ([`ConstraintTemplate`](https://cloud.google.com/anthos-config-management/docs/concepts/policy-controller#constraint_templates)) from policy **enforcement** ([`Constraint`](https://cloud.google.com/anthos-config-management/docs/concepts/policy-controller#constraints)).

Policy Controller comes with a [library of `ConstraintTemplate`s](https://cloud.google.com/anthos-config-management/docs/reference/constraint-template-library) for common security and compliance controls.

This repository contains **sample** `Constraint`s which make use of Policy Controller's `ConstraintTemplates` to demonstrate how you might configure policy enforcement on your own cluster.

## Policy Bundles

- [ASM Policy v0.0.1](./bundles/asm-policy-v0.0.1)
- [CIS Kubernetes v1.5.1](./bundles/cis-k8s-v1.5.1)
- [Pod Security Policy v2022](./bundles/psp-v2022)
- [Pod Security Standards Baseline v2022](./bundles/pss-baseline-v2022)
- [Policy Essentials v2022](./bundles/policy-essentials-v2022)

## Anthos Policy Bundles

[Anthos](https://cloud.google.com/anthos) Policy Bundles may only be used on an Anthos cluster, including any associated ci/cd use. “Anthos cluster” is defined as “A Cluster (of any kind) registered to a [fleet project](https://cloud.google.com/anthos/fleet-management/docs/fleet-concepts) where the Anthos API is enabled”.

- [National Institute of Standards and Technology SP 800 r5](./anthos-bundles/nist-800-r5)
- [Payment Card Industry Data Security Standard (PCI DSS) v3.2.1](./anthos-bundles/pci-dss-v3.2.1) and [PCI DSS v3.2.1 Extended](./anthos-bundles/pci-dss-v3.2.1-extended)
- [Pod Security Standards Restricted v2022](./anthos-bundles/pss-restricted-v2022)

## Usage

See [Creating constraints](https://cloud.google.com/anthos-config-management/docs/how-to/creating-constraints)
