# WebPageTest GitHub Action
[![All Contributors](https://img.shields.io/badge/all_contributors-1-orange.svg?style=flat-square)](#contributors)

⚡️🚀 GitHub Action to print [webPageTest.org](https://www.webpagetest.org/) results as a commit comment after a push.

<p></p>
<details>
  <summary> Click to see example commit comment </summary>
<p align="center">
  <img alt="example image" src="https://github.com/JCofman/webPagetestAction/blob/master/example.png"/>
</p>
</details>
<p></p>

Make sure to pass a WEBPAGETEST_API_KEY which you can get [here](https://www.webpagetest.org/getkey.php) and a TEST_URL.

## Secrets

- GITHUB_TOKEN - Required GitHub token provided by actions to validate requests and make sure you are allowed to comment on the repo
- WEBPAGETEST_API_KEY - Required API key which you either can provide by your own hosted WebPageTest instance or can get here [here](https://www.webpagetest.org/getkey.php)

## Environment Variables

- WEBPAGETEST_SERVER_URL - Optional By default this repo uses the awesome free WebPageTest `www.webpagetest.org` server offered by Akami but you can provide your own hosted version.
- TEST_URL - URL to run the audit e.g. `https://jcofman.de`

## Args

You should be able to provide custom args as mentioned in the [marcelduran/webpagetest-api](https://github.com/marcelduran/webpagetest-api#test-works-for-test-command-only) under the `Test (works for test command only)` section.

## Examples

```yml
on: push
name: Run Webpagetest
jobs:
  webPageTestActions:
    name: WebPageTestActions
    runs-on: ubuntu-latest
    steps:
      - uses: JCofman/webPagetestAction@master
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          TEST_URL: https://example.com
          WEBPAGETEST_API_KEY: ${{ secrets.WEBPAGETEST_API_KEY }}
```

With self hosted WebPagetest server

```yml
on: push
name: Run Webpagetest
jobs:
  webPageTestActions:
    name: WebPageTestActions
    runs-on: ubuntu-latest
    steps:
      - uses: JCofman/webPagetestAction@master
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          TEST_URL: https://example.com
          WEBPAGETEST_API_KEY: ${{ secrets.WEBPAGETEST_API_KEY }}
          WEBPAGETEST_SERVER_URL: www.your-custom-server.org
```

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore -->
<table>
  <tr>
    <td align="center"><a href="https://twitter.com/markusstaab"><img src="https://avatars2.githubusercontent.com/u/120441?v=4" width="100px;" alt="Markus Staab"/><br /><sub><b>Markus Staab</b></sub></a><br /><a href="https://github.com/JCofman/webPagetestAction/commits?author=staabm" title="Documentation">📖</a></td>
  </tr>
</table>

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!