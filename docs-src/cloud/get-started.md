---
id: get-started
title: Get started with Temporal Cloud
sidebar_label: Get started
description: Create an account, issue certificates, create a Namespace, invite users, and connect.
tags:
  - introduction
  - temporal cloud
---

Follow these steps to start using Temporal Cloud:

**1. Sign up for Temporal Cloud!**

To request a Temporal Cloud account, complete the [request form](https://pages.temporal.io/cloud-request-access).

**2. Accept Global Admin permissions**

<!--- Onboarding guide for Temporal Cloud --->

You received email from Temporal that welcomes you to your new Temporal account.
Your email address is now the first [Global Admin](/cloud/users-account-level-roles) for your account.

**3. Setup CA certificates**

You must provide your own CA certificates.
These certificates are needed to create a Namespace, which are in turn used to grant Temporal Clients and Workers access to it.

For certificate requirements, see the following:

- [Requirements for CA certificates](/cloud/certificates-requirements)
- [Issue root CA and end-entity certificates](/cloud/certificates-issue)

**4. Create a Namespace**

[Create a Namespace in Temporal Cloud](/cloud/namespaces-create) using the Temporal Cloud UI or tcld, if you don't already have a Namespace (or want to create another).

**5. Invite users**

Adding a user to your Temporal Cloud Account includes sending an email invite that the user must then accept.
To add users, see the following:

[How to invite users to your Temporal Cloud account](/cloud/users-invite)

**6. Connect to Temporal Cloud**

Update your Temporal Client connections and Workers to use your Temporal Cloud Namespace credentials.

Each SDK has a way to use your CA certificates and private keys to authenticate and authorize access to your Temporal Cloud Namespace.

- [Connect to Temporal Cloud in Go](/go/connect-to-temporal-cloud)
- [Connect to Temporal Cloud in Python](/python/connect-to-temporal-cloud)
- [Connect to Temporal Cloud in TypeScript](/typescript/connect-to-temporal-cloud)

- [Run a Temporal Cloud Worker in Go](/go/run-a-temporal-cloud-worker)
- [Run a Temporal Cloud Worker in TypeScript](/typescript/run-a-temporal-cloud-worker)