# Stats

With this action you can add your schedule statistics to a markdown sheet.

In order to use this action you must have a wakatime account.

Steps to put this action into operation:

* Create an account on wakatime -> https://wakatime.com/signup
* Integrate wakatime with your favorite code editor
* Go to the github repository where you want to put the statistics and click on the actions tab
* Click on set up a workflow yourself and write the following code : 
```yml
name: Readme stats

on:
  workflow_dispatch:
  schedule:
    # Runs at 12am UTC
    - cron: "0 0 * * *"

jobs:
  update-readme:
    name: Update this repo's README
    runs-on: ubuntu-latest
    steps:
      - uses: daniellop1/stats@master
        with:
          WAKATIME_API_KEY: ${{ secrets.WAKATIME_API_KEY }}
 ```

* Go to your repository secrets (Setting-> Secrets) and add one called `WAKATIME_API_KEY` and paste your wakatime api which you can find at (https://wakatime.com/settings/account)
* To finish add this code in your README.md where you want the statistics to appear:

```md
<pre>
<!--START_SECTION:stats-->
<!--END_SECTION:stats-->
</pre>
```

### Status

![Markdown editor](https://status.2005danielus.ml/status/github.com-daniellop1-stats-443.svg?t=1609936466844)

### Legal
The original creator of this action is athul (https://github.com/athul) and its repository is (https://github.com/athul/waka-readme), this action is customized for me because the original gave me problems. Copyright claims -> contact@2005danielus.ml
