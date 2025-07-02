---
title: FAQs
sidebar_label: FAQs
description: Frequently asked questions about CodeRabbit.
sidebar_position: 9
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

## General Questions {#general-questions}

### How to trigger a CodeRabbit Review?

Once installed, CodeRabbit automatically triggers a review when a pull request is opened against the main branch of any repository. We automatically detect the name of the primary branch (whether this be master, main, dev, etc). This branch restriction can be customized in your settings.

You can also manually trigger a review at any time by commenting on a pull request with one of these commands (see [Commands](/guides/commands.md) for full list):

- `@coderabbitai review` - Triggers a standard review
- `@coderabbitai full review` - Triggers a comprehensive review

### How to run a review from my IDE?

You can trigger CodeRabbit reviews directly from your IDE using our editor plugins:

- [VSCode Extension](./guides/about-vscode.md) - For VSCode, Cursor or Windsurf users

These plugins allow you to request reviews without leaving your development environment. See the individual plugin documentation for installation and usage instructions.

### How to install CodeRabbit?

View step by step instructions depending on your platform:

<Tabs>
  <TabItem value="github" label="GitHub" default>
    See our [GitHub App installation guide](./platforms/github-com.md) for step-by-step instructions.
  </TabItem>
  <TabItem value="gitlab" label="GitLab">
    Follow our [GitLab integration guide](/platforms/gitlab-com.mdx) to get started.
  </TabItem>
  <TabItem value="bitbucket" label="Bitbucket">
    Check out the [Bitbucket installation steps](/platforms/bitbucket-cloud.md) for detailed setup.
  </TabItem>
  <TabItem value="azure" label="Azure DevOps">
    View our [Azure DevOps setup guide](/platforms/azure-devops.md) for complete installation instructions.
  </TabItem>
</Tabs>

### How accurate is CodeRabbit?

> CodeRabbit demonstrates high accuracy in code reviews based on early adoption results. While 100% accuracy isn't guaranteed due to AI's evolving nature, our technology continuously improves through:

- Regular model updates
- Enhanced pattern recognition
- Growing language support
- Refined code analysis

### Language Support

CodeRabbit works with all programming languages, with varying proficiency based on:

- Language popularity
- Available training data
- Community usage patterns

### Whats the difference between CodeRabbit Code Reviews and CodeRabbit Reports?

CodeRabbit offers two distinct features that serve different roles in your development workflow:

#### CodeRabbit Code Reviews

**Role**: Developer, QA, and Code Reviewer
**Access Level**: Full code access with comprehensive analysis capabilities

**Key Features:**

- **Complete Toolchain**: Runs all available analysis tools on your codebase
- **Static Analysis**: Can execute shell commands and perform deep static analysis against your codebase
- **Direct Code Access**: Has full access to code in issues and pull requests
- **Interactive Chat**: Provides chat features for real-time collaboration and questions
- **Comprehensive Review**: Analyzes code quality, security, performance, and best practices
- **Actionable Feedback**: Provides specific, line-by-line suggestions and improvements
- **Comment Interaction**: Engages with users through comments in pull requests and issues for clarifications and discussions
- **Available in All Tiers**: All features are available across Free, Lite, and Pro plans

#### CodeRabbit Reports

**Role**: Project Manager and Communication Hub
**Access Level**: Summary-only access without direct code interaction

**Key Features:**

- **Summary Generation**: Creates convenient, formatted summaries of all your recent pull requests
- **Customizable Prompts**: Allows you to select or create your own summarization templates
- **High-Level Overview**: Focuses on project progress and changes without code details
- **Comment Analysis**: Reads and summarizes existing comments and discussions
- **No Code Access**: Operates only on summaries and metadata, not the actual codebase
- **Communication Tool**: Designed for stakeholders who need updates without technical details
- **Multi-Channel Delivery**: Sends reports through various communication channels:
  - Email notifications
  - Slack integration
  - Discord webhooks
  - Microsoft Teams updates
- **Pro Plan Exclusive**: Reports feature is available only in the Pro plan tier

**In Summary:**

- **Code Reviews** = Technical analysis with full code access for developers
- **Reports** = High-level summaries with no code access for project management

### Data Security

<Tabs>
  <TabItem value="storage" label="Code Storage" default>
    - Complete data isolation
    - Caching of encrypted code and dependency archives for faster reviews
    - Code indexing in which we store vector representations of code for efficient code base context
    - Both caching and code indexing can be disabled which means we store nothing post-review
  </TabItem>
  <TabItem value="training" label="Training Data">
    - Uses only public datasets
    - No proprietary code usage
    - Private repositories excluded
  </TabItem>
</Tabs>

### Organization Management

Switch between organizations easily:

1. Click organization name (top-left corner)
2. Select desired organization
3. Access organization-specific settings

![Organization Switcher](/img/faq/cr_support_orgs_light.png#gh-light-mode-only)
![Organization Switcher](/img/faq/cr_support_orgs_dark.png#gh-dark-mode-only)

### Comparison with Other Tools

> Code reviews remain essential, whether the code is written by a human or a bot. This is mainly because the perspective of the reviewer differs from that of the code generator, whether human or machine. This distinction is precisely why human peer reviews have been effective for so long. While AI-powered code-generation tools like GitHub Copilot hold immense potential, it's important to recognize that these generators are still in their early stages and may not be equipped to auto-generate meaningful code for moderately complex applications.

#### vs AI Code Generators

- Provides review perspective different from code generation
- Complements tools like GitHub Copilot
- Focuses on code quality and best practices

#### vs Traditional Review Tools

- Context-aware feedback
- Actionable suggestions
- Direct commit capabilities
- AI-powered intent understanding

## Usage and Configuration {#usage-and-configuration}

### When Does CodeRabbit Review PRs?

- ✅ **New PRs**: Automatic review when created
- ✅ **New Commits**: Automatic review when pushed to any PR
- ⚡ **Older PRs**: Use `@coderabbitai review` to trigger manually

![CodeRabbit- Full-Review](/img/faq/full-review.png)

### Customization Options

#### How to Add or Update Your Billing Email

To add or update your billing email, navigate to the Subscription page and
select Manage Subscription > **Billing Address**. Enter your email address in the
Email field and click Update to save your changes.

### Usage and Configuration

- **Language Settings**: Configure review language in repository settings
- **Review Rules**: Customize via [review instructions](/guides/review-instructions.md)
- **Branch Selection**: Default branch reviews enabled by default (configurable)

### Access & Permissions

- Minimal repository access required
- Review permissions during installation
- Individual developer support available

### Interaction Guide

Interact with CodeRabbit by:

1. Replying directly to CodeRabbit comments
2. Tagging `@coderabbitai` in PR discussions
3. Adding review comments for specific lines
4. Customize via [review instructions](/guides/review-instructions.md)

:::tip Collaboration Mode
When team members are active in PRs, use `@coderabbitai` to engage the bot.
:::

### Usage Limits

:::note

In-trial and open-source plans have lower rate limits than the paid plan. In all cases, we re-allow further reviews/conversations after a brief timeout.

:::

The following limits enforced _per developer_:

| Feature                          | Free Plan                                  | Trial Plan                        | OSS Plan                      | Pro/Lite Plan                 |
| -------------------------------- | ------------------------------------------ | --------------------------------- | ----------------------------- | ----------------------------- |
| Files per hour                   | 200/hour                                   | 200/hour                          | 200/hour                      | 400/hour                      |
| Files per PR                     | 100                                        | 100                               | 100                           | 200                           |
| Reviews per hour                 | 3 back-to-back, then 2/hour (Summary only) | 4 back-to-back, then 3/hour       | 3 back-to-back, then 2/hour   | 5 back-to-back, then 4/hour   |
| Reviews per hour (IDE Extension) | 1/hour                                     | 5/hour (Pro trial), 1/hour(Other) | 1/hour                        | 5/hour (Pro), 1/hour(Lite)    |
| Chat                             | N/A                                        | 25 back-to-back, then 50/hour     | 10 back-to-back, then 25/hour | 25 back-to-back, then 50/hour |

## Integration Guide {#integration-guide}

### Prerequisites

- Organization admin access
- Domain allowlist (GitLab: add `coderabbit.ai`)
- Default branch configuration

### Quick Setup

1. Sign up at [coderabbit.ai](https://coderabbit.ai) using your GitHub account
2. Add your repository through the dashboard
3. That's it. CodeRabbit will automatically start reviewing your PRs

:::tip Need Help?
Visit our [Support](/getting-started/support.md) page for additional assistance or reach out to our team on [Discord](http://discord.gg/coderabbit).
:::

#### Unable to View Repositories in GitLab

If you cannot view repositories in the CodeRabbit UI, please ensure that you
are added as a Developer in the primary group for GitLab Cloud or in the first
level group for Self-Hosted GitLab.

#### Unable to Enable Repositories in GitLab

If you're having trouble enabling the GitLab Repositories toggle, confirm that
you have Maintainer access in the primary group for GitLab Cloud or in the first
level group for Self-Hosted GitLab.

## Account Management {#account-management}

### How to troubleshoot CodeRabbit not functioning on certain repositories?

If CodeRabbit is not functioning on certain repositories, it is likely due to the repository not being accessible to CodeRabbit and you must reinstall the GitHub App or GitLab Integration.

To troubleshoot this issue, please attempt to reinstall the GitHub App or GitLab Integration by following the steps below:

<Tabs>
  <TabItem value="general" label="General Instructions" default>
    1. Confirm that the author of a pull request has an active seat in CodeRabbit. If not please provide a seat to the user under [Subscription](https://coderabbit.ai/settings/subscription) page to enable CodeRabbit for the user.  Then have the user close/reopen a new pull request for the change to see coderabbit active on the new user. ![Seat Assignment](/img/faq/seat-assignment.png)
    3. Please insure if not selecting all repositories, that you have added all repositories that you would like to enable to the selected list in the app configuration.
    4. If the repository is not in the list, you do not have to uninstall and reinstall the CodeRabbit App. Please add it to the list. ![Select Repos](/img/faq/select-repos.png)
  </TabItem>

  <TabItem value="github" label="GitHub">
    1. Go to Repository settings
    2. Click **GitHub Apps** in the left sidebar under **Integrations**
    3. Select **Configure** ![Select Repos](/img/faq/github-app-settings.png)
    4. Click **Uninstall** at the bottom of the app configuration page. ![Uninstall](/img/faq/coderabbit-github-menu.png)
    5. Go into the [Coderabbit App](https://github.com/apps/coderabbitai) and install it again with the **Add Repository** button. ![Add Repository](/img/faq/add-repository.png)
  </TabItem>

  <TabItem value="gitlab" label="GitLab">
    1. Remove OAuth App from User Settings > Applications
    2. Remove Webhook from Group > Project Settings > Webhooks
    3. Go into the [Coderabbit App](https://gitlab.com/apps/coderabbitai) and install it again. ![Install](/img/faq/gitlab-webhook.png)
  </TabItem>
</Tabs>

### How do I delete my CodeRabbit account?

:::danger Irreversible Account Deletion
Deleting your CodeRabbit account is permanent and cannot be undone. This action will permanently erase:

- Organization and Repository data
- AI Bot learnings and insights
- Subscriptions and billing information
- All settings and configurations
- Reports and recurring reports
- Third-party service integrations
  :::

<Tabs>
  <TabItem value="deletion" label="Account Deletion Steps" default>
    1. Sign into your CodeRabbit account
    2. Navigate to the **Subscription** page
    3. Click the orange **Delete Account** button
    4. Review the deletion confirmation modal
    5. Type "delete" to confirm
    6. Complete platform-specific cleanup steps below

    :::info
    The Delete Account button is only visible to admin users.
    :::

A confirmation modal will appear explaining the consequences of account deletion. You can expand each section for detailed information:

    <div align="center">
    ![Delete Account](/img/guides/delete_account_light.png#gh-light-mode-only)
    ![Delete Account](/img/guides/delete_account_dark.png#gh-dark-mode-only)
    </div>

  </TabItem>
  <TabItem value="github" label="GitHub Cleanup">
    After account deletion, you must:

    **Remove OAuth App:**
    1. Go to Organization settings
    2. Click **OAuth Application Policy**
    3. Find **coderabbitai** and click the pencil icon
    4. Click **Revoke**

    **Uninstall GitHub App:**
    1. Go to Organization settings
    2. Click **GitHub Apps**
    3. Select **Configure**
    4. Click **Uninstall**

  </TabItem>
  <TabItem value="gitlab" label="GitLab Cleanup">
    Complete these steps:

    1. Remove OAuth App from User Settings > Applications
    2. Remove Webhook from Group > Project Settings > Webhooks
    3. Remove Bot User from Group > Manage > Members

  </TabItem>
  <TabItem value="azure" label="Azure DevOps Cleanup">
    1. Go to Project Settings > Service Hooks
    2. Delete CodeRabbit webhooks
    3. Remove CodeRabbit user or delete associated Personal Access Token
  </TabItem>
  <TabItem value="bitbucket" label="Bitbucket Cleanup">
    1. Go to Project Settings > Webhooks
    2. Delete CodeRabbit webhooks
    3. Remove CodeRabbit user or delete associated App Passwords
  </TabItem>
</Tabs>

:::warning Post-Deletion Steps
The platform-specific cleanup steps are necessary to completely remove CodeRabbit access. Without completing these steps:

- CodeRabbit may retain some platform permissions
- Signing back in will recreate minimal account data
  :::
