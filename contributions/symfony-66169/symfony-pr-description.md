| Q             | A
| ------------- | ---
| Branch?       | 6.4
| Bug fix?      | no
| New feature?  | no
| Deprecations? | no
| Issues        | Fix #66169
| License       | MIT

Reviewed the Indonesian (id) audio validation messages as a native speaker
and removed the `needs-review-translation` state from them.

The 17 strings (ids 149-165) already read naturally, use the same tone as the
rest of the file, and keep every placeholder identical (`{{ duration }}`,
`{{ min_duration }}`, `{{ codec }}`, ...), so no translation text is changed —
only the review state is cleared.

Changed file:
- `src/Symfony/Component/Validator/Resources/translations/validators.id.xlf`