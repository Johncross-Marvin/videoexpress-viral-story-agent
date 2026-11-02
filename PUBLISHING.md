# Publish this rewritten playbook on GitHub

No changes are made to the source repository automatically. To publish, use **a repository you own or are authorized to update**.

## Affiliate referral and public attribution

For people who need a VideoExpress account, share the maintainer's optional affiliate link: **[Access VideoExpress](https://videoexpress.alphatoolkits.com/)**.

**Disclosure for public docs:** This is an affiliate link. The repository maintainer may receive a commission if you complete an eligible purchase/subscription through it. Affiliate attribution and payment depend on the provider's terms and tracking; GitHub cannot guarantee commission. Do not hide the commercial nature of the link, imply an official affiliation, promise an unverified discount, or automatically redirect existing users. VideoExpress's normal app URL remains `https://app.videoexpress.ai/` for the signed-in production workflow.

## Recommended: new repository

1. Review the [original repository](https://github.com/ai-playbooks/videoexpress-two-character-agent) and licensing/provenance concerns. The inspected source root did not show a license file; do not assume copying original content is permitted. This project is a substantial rewrite based on the user-provided prompt and the public workflow description.
2. Create a new empty repository, e.g. `videoexpress-longform-multicharacter-agent`.
3. Unzip `VideoExpress_LongForm_MultiCharacter_Agent_GitHub_Repository.zip` and put the **contents of its top-level folder** into the new repository root.
4. From that folder (with Git installed), run:

```bash
git init
git add .
git commit -m "Add viral-pattern script-first 5-20min VideoExpress story agent"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/videoexpress-longform-multicharacter-agent.git
git push -u origin main
```

Replace `YOUR-USERNAME` with the exact account that owns your newly created repository. Authenticate using Git's supported login/credential manager; never paste tokens into chat.

## Authorized existing repository

If you have write access to an existing repository, follow its contribution/license policy, create a feature branch and replace the relevant prompt and README files after reviewing changes. Open a pull request rather than silently overwriting someone else's work.

## Verify after publishing

Check `README.md`, `VIRAL_STORY_ENGINE.md`, `SYSTEM_PROMPT_ALL_IN_ONE.md`, `SYSTEM_PROMPT.md`, `SYSTEM_PROMPT_COMPACT.md`, `.github/workflows/validate.yml`, `templates/`, `examples/`, `tools/` and `tests/` are visible, and that the GitHub Actions validation workflow completes. Passing offline tests **does not** verify VideoExpress UI automation or video export.