# eteaching.skos.vocabularies


This repository ist a fork of [skohub-io/skohub-pages](https://github.com/skohub-io/skohub-pages) and provides various SKOS vocabularies via the GitHub infrastructure. These are vocabularies that are intended to enable problem-oriented access for searches based on metadata. The following vocabularies are provided in the Terse RDF Triple Language (Turtle): 

- affected_by_problem.ttl
- problem_areas.ttl
- problems.ttl
- symptoms.ttl

The vocabularies are made available in a more human-readable form [via a website](https://e-teachingorg.github.io/eteaching.skos.vocabularies/).

# GitHub-workflow-action

Every time a change is made to a vocabulary a GitHub-workflow-action is triggered to publish the most recent vocabulary to the `gh-pages`-branch, which is used by GitHub pages.
It spins up a Docker container made from [SkoHub Vocabs](https://github.com/hbz/skohub-vocabs).

## Usage

If you want to reuse this repo and have your vocabulary automatically pushed und published via GitHub-Pages, follow these steps:

1. Fork this repo. **Uncheck the box to only fork the main branch**.
1. Go to "Actions" tab and if not already activated, activate GitHub Actions.
1. Go to "Settings", navigate to the "Pages" setting and select `gh-pages` as the branch your site is being built from. 
1. Go back to the main page of your repo and click the little gear icon in the top right of the "About" section. Check the box at "Use your GitHub Pages website".
1. Add a commit to the main branch and your vocabulary will be automatically published (sometimes it takes a little to see the changes, remember to do some hard refreshing).

Any issues? Please open up a issue [here](https://github.com/skohub-io/skohub-pages/issues)

## Custom Domain

If you want to host your vocabularies under your GitHub pages domain (so no W3 perma-id or purl.org redirect), you have to provide that domain in the [`config.yaml`](./config.yaml).

Example:

Your GitHub Pages domain is: `https://skohub-io.github.io/skohub-pages/`
Then provide `https://skohub-io.github.io/skohub-pages/` as `custom_domain` in your `config.yaml`.

The base of your concept scheme could then be something like: `https://skohub-io.github.io/skohub-pages/colours/`

Notice that this will apply to all your hosted vocabularies.

## Troubleshooting

### There is no `gh-pages` branch to select for GitHub Pages

You probably only forked the main branch.
You have two options:

- Delete the repo and fork it again, but make sure to uncheck the box to only fork the main branch
- Make sure the GitHub Action is activated ➡️ Go to "Actions" tab and activate it. After that commit changes to a vocabulary in the main branch. This should trigger the build and create a `gh-pages` branch.

### I push changes, but they seem to have no effect. My vocabulary stays the same

Maybe your GitHub Action is not activated yet.
Go to the "Actions" tab and activate GitHub Actions for your repository.

### During the build I get an error saying `The requested URL returned error: 403`

You maybe need to update permissions like described here: https://github.com/peaceiris/actions-gh-pages/issues/744
Go to `Settings` > `Actions` > `General` > `Workflow permissions` and toggle the Read and write permissions.


## Authors

* 

## Contribute

- Issue Tracker: https://github.com/e-teachingorg/eteaching.skos.vocabularies/issues
- Source Code: https://github.com/e-teachingorg/eteaching.skos.vocabularies/

## Support

If you are having issues, please let us know.

## License

The project is licensed under the Apache-2.0 license.

## Funding information
The creation and development of the vocabulary (affected_by_problem.ttl, problem_areas.ttl, problems.ttl, symptoms.ttl) was funded as part of a publicly financed project by the Federal Ministry of Research, Technology and Space of the Federal Republic of Germany.

