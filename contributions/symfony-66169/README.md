# Symfony contribution: Indonesian (id) validator translations

Target issue: symfony/symfony#66169 — "Missing translations for Indonesian (id)"
(`Good first issue` + `Help wanted`, unassigned, no PR at the time of writing)

## What changed

`src/Symfony/Component/Validator/Resources/translations/validators.id.xlf` on branch `6.4`.

The 17 audio validation messages (trans-unit ids 149-165) carried
`state="needs-review-translation"`. They were reviewed as a native speaker and the
state attribute was removed. No translation text was changed: the wording already
reads naturally and matches the tone of the rest of the file.

## Validation performed

- XML is well-formed, 161 `trans-unit` entries intact.
- Every placeholder is preserved: 0 mismatches between `<source>` and `<target>`
  for `{{ duration }}`, `{{ min_duration }}`, `{{ max_duration }}`, `{{ bitrate }}`,
  `{{ sample_rate }}`, `{{ channels }}`, `{{ codec }}`, `{{ container }}`, etc.
- `<source>` strings match `validators.en.xlf` exactly (0 mismatches).
- `needs-review-translation` count after the change: 0.

## Files

- `symfony-validator-id-translations.patch` — apply with `git am`
- `symfony-pr-description.md` — PR body following the Symfony pull request template

## How to submit

```bash
gh repo fork symfony/symfony --clone
cd symfony
git checkout -b validator-id-translations 6.4
git am --keep-non-patch /path/to/symfony-validator-id-translations.patch
git log -1 --format=%s   # expect: [Validator] Review Indonesian (id) translations
git push origin validator-id-translations
```

`--keep-non-patch` matters: plain `git am` strips the leading `[Validator]` from
the subject line because it looks like a mail list tag. Symfony's commit message
convention expects the component in brackets, so dropping it would fail the check.

Then open the PR against `symfony:6.4` using `symfony-pr-description.md`.

Comment on issue #66169 first to claim it, as the issue asks.
