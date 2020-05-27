# Application Security

## (SC-100) Never Commit Secrets

No secrets, credentials, or sensitive data shall ever be committed to a Git
repository, either local or remote.

Rationale:

-   Secrets provide access to administrative functions as well as protected data.
    Exposing secrets in a repository is a primary attack vector for compromised
    systems that are exploited every day on the internet. Secrets must be protected
    at all times and are instantly at risk and exposed when committed into a source
    code repository.

Alternatives:

-   Communicating shared secrets should only be done via email or Slack. (Note:
    This will change as we're working on making a secrets management tool available.)
-   Use [dotenv](https://github.com/motdotla/dotenv)
    or an equivalent tool to put secrets into your local environment, which can
    then be read by your application at runtime.

## (SC-200) Never Store Secrets

No software shall maintain user secrets in application storage.

Rationale:

-   Effectively storing and protecting secrets is extremely difficult and incurs
    a great deal of design, development, and operational overhead.

Alternatives:

-   Always use a trusted 3rd party Identity Provider (IdP) to authenticate users.

Exceptions:

-   Non-user specific secrets (e.g. API keys, etc.) should be stored using secure
    services and provided to the application at runtime using environment variables.
