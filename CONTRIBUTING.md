# Contributing to Awesome Ad Fraud

First off, thank you for considering contributing to Awesome Ad Fraud. We appreciate your time and effort in helping us build a comprehensive, practitioner-focused resource for combating digital advertising fraud.

The goal of this project is to curate a high-quality list of open-source tools, verification platforms, supply chain utilities, datasets, technical standards, and primary research for detecting, measuring, and preventing ad fraud and invalid traffic (IVT). To maintain the quality of this list, please review the guidelines below before submitting a pull request.

By participating in this project you agree to abide by our [Code of Conduct](CODE_OF_CONDUCT.md).

## Submission Guidelines

Please ensure your submission adheres to the following core criteria:

- **Relevance:** The resource must directly support ad fraud prevention, invalid traffic (IVT) detection, bot mitigation, supply chain transparency (`ads.txt`, `app-ads.txt`, `sellers.json`, `schain`), malvertising defense, mobile attribution security, or MFA filtering.
- **Active Maintenance or Authoritative Source:** We prioritize actively maintained open-source repositories and authoritative primary sources (standards bodies, public datasets, peer-reviewed research, and established verification platforms). Abandoned or unmaintained tools will not be merged.
- **Direct Links Only:** Absolutely no affiliate, tracking, or referral links are allowed.
- **No Duplicates:** Search `README.md` before submitting to verify the project or URL is not already listed.

## Description Standards

Descriptions must be concise, objective, and purely informational.

- **Do:** Focus on the exact utility and core technical capabilities of the tool.
  > *Example: "Parses ads.txt and app-ads.txt records and validates seller authorization."*
- **Don't:** Use marketing fluff, superlatives, or subjective claims.
  > *Example: "The world's best platform that revolutionizes your ad spend protection."*

Keep each description to one factual sentence (roughly 25–220 characters) ending with a period, with no pricing details or promotional claims.

## Step-by-Step Submission Process

To add a new tool or resource to the list, please follow these steps:

1. **Star the repository:** Show your support and help the community grow.
2. **Locate the file:** Navigate to the `README.md` file in the `main` branch of this repository.
3. **Edit the document:** Click the **Edit** (pencil) icon to begin making your changes.
4. **Format your entry:** Add your link in alphabetical order within the appropriate category using the exact Markdown syntax below. Use the `github` icon when the primary link is a GitHub repository and the `web` icon otherwise. Always link directly to the tool's site or repository — never through search engines or redirect services:

   ```markdown
   ![github](image/alg_R.png) [Tool Name](https://github.com/org/repo) - Short, objective description of what it does.

   ![web](image/alg_I.png) [Tool Name](https://example.com) - Short, objective description of what it does.
   ```

   Do not include pricing or promotional claims in descriptions.

5. **Verify links and formatting:** Confirm that your URL uses `https://`, resolves without errors, has no tracking parameters, and follows the icon and description standards above.
6. **Create a Pull Request:** Submit your PR with a clear and descriptive title using the following format:
   `Add [Tool Name]`

## Pull Request Review

Once submitted, your pull request will be reviewed. If it meets all the criteria outlined above, it will be merged. If any formatting adjustments or description changes are needed, we will leave feedback in the PR comments.

Please keep one resource per pull request. Large re-orderings, category renames, and bulk additions are easier to review as separate PRs.

## Code of Conduct

This project follows the [Contributor Covenant 2.1](CODE_OF_CONDUCT.md). Be kind in issues and reviews, critique entries rather than people, and report unacceptable behavior to the maintainers as described in the Code of Conduct.

Thank you for your contributions!
