# Badgery fork

This is Badgery's fork of [mc1arke/sonarqube-community-branch-plugin](https://github.com/mc1arke/sonarqube-community-branch-plugin),
kept so Badgery can follow SonarQube Community Build releases while upstream
releases are paused. It is not a takeover: fixes go back upstream as pull
requests, and Badgery returns to upstream releases when they resume.

The plugin remains licensed under the GNU LGPL v3, as upstream.

## What is in it

Branch `badgery/26.9` targets SonarQube Community Build **26.9.0.129388**. It is
upstream `master` (26.5.0) plus these open upstream pull requests, merged with
their original commits and authorship:

| Upstream PR | Author | What |
|---|---|---|
| [#1296](https://github.com/mc1arke/sonarqube-community-branch-plugin/pull/1296) | [@Nacho-Larreta](https://github.com/Nacho-Larreta) | SonarQube 26.7 and 26.8 support (includes [#1280](https://github.com/mc1arke/sonarqube-community-branch-plugin/pull/1280) by [@gsaraiva2109](https://github.com/gsaraiva2109)) |
| [#1298](https://github.com/mc1arke/sonarqube-community-branch-plugin/pull/1298) | [@Adrian-Eckardt](https://github.com/Adrian-Eckardt) | SonarQube 26.9 support |
| [#1302](https://github.com/mc1arke/sonarqube-community-branch-plugin/pull/1302) | [@mpet](https://github.com/mpet) | Automated branch and pull-request integration test (`scripts/integration-test.sh`) |

Thanks to them, and to [@mc1arke](https://github.com/mc1arke) for the plugin itself.

## Releases

Tags are `<sonarqube version>-badgery.<n>`, for example `26.9.0-badgery.1`, so
they never collide with upstream's own `26.9.0`. A tag builds the plugin JAR and
the matching `sonarqube-webapp.zip`, runs the integration test against that
commit, and publishes both with `SHA256SUMS`
(`.github/workflows/badgery-release.yml`). Always install the JAR and webapp
from the same release.
