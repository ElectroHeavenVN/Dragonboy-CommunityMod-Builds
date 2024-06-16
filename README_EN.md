# Dragonboy-CommunityMod-Builds - [VI](README.md) | EN
Automatically checkout and compile [Dragonboy](https://github.com/pk9r327/Dragonboy/tree/Unity-project) using GitHub Actions daily. Can be manually run when needed.

Supported OS: Windows, Linux, Android. The iOS operating system will not be supported due to limitations on the execution of dynamically generated code.
## Download
There are 2 methods to download:
<details>
<summary>Method 1 (No GitHub account required): Download via Release</summary>

- Select [Latest build](../../releases/tag/latest) in the [Releases](../../releases) section.
- Choose the appropriate file for your operating system in the `Assets` section.

</details>
<details>
<summary>Method 2 <u><b>(GitHub account required)</b></u>: Download via Artifact</summary>

- Select the [Actions](../../actions) tab at the top.
- Choose the [Biên dịch QLTK và Game](../../actions/workflows/build.yml) workflow from the list of workflows on the left side.
- Select the latest successful `workflow run`.
- Choose the appropriate file for your operating system in the `Artifacts` section.
  
</details>

## Setup
To build the [Dragonboy](https://github.com/pk9r327/Dragonboy/tree/Unity-project) project or ypur own fork using Github Actions, follow these steps:
- Fork this repository
- Go to the `Settings` of your forked repository, then select `Actions` in the `Secrets and variables` section.
- Under `Repository secrets`, click `New repository secrets`.
- In the `Name` field, enter `SOURCE_CODE_REPOSITORY`, and in the `Secret` field, enter `pk9r327/Dragonboy`, or the path to your fork (if you want to compile the game from your own fork).
- Click `Add secret` to add the secret.
- Repeat the above steps with the values of the `Name` field and `Secret` field as follows:
    + `SOURCE_CODE_BRANCH`: branch you want to compile, if the `SOURCE_CODE_REPOSITORY` secret value is `pk9r327/Dragonboy` then enter `Unity-project`
    + `UNITY_EMAIL`: the email you used to create your Unity account
    + `UNITY_PASSWORD`: your Unity account password
    + `UNITY_LICENSE`: the content of the `Unity_lic.ulf` file (refer to the [GameCI](https://game.ci/)'s documentation [here](https://game.ci/docs/github/activation/#activating-a-license-file) for the path to the `Unity_lic.ulf` file)
    + `ANDROID_KEYSTORE_BASE64`: the base64 encoded content of your keystore file
    + `ANDROID_KEYSTORE_PASS`: your keystore password
    + `ANDROID_KEYALIAS_NAME`: the alias name in your keystore file
    + `ANDROID_KEYALIAS_PASS`: the alias password in your keystore file
    + (Optional) `DISCORD_WEBHOOK`: Discord Webhook URL for build result notifications

    <sub>**Refer to the [Deploy to Google Play](https://game.ci/docs/github/deployment/android/) section of [GameCI](https://game.ci/) for more information about Android keystore.**</sub>

- Activate [`build.yml`](.github/workflows/build.yml) in your fork (if you want to automate the build):
    + Select workflow [Biên dịch QLTK và Game](../../actions/workflows/build.yml)
    + Click `Enable workflow`
- Run [`selective-build.yml`](.github/workflows/selective-build.yml) (if you want to build manually):
    + Select workflow [Biên dịch QLTK và Game (selective)](../../actions/workflows/selective-build.yml)
    + Click `Run workflow`
    + Select checkboxes and type in the webhook link according to your preferences
    + Select `Run workflow` at the bottom

Workflows usually run for about 20 - 50 minutes, depending on the amount of code you modified compared to the previous compilation. The first run will usually take the longest. Once the workflow has finished running, you can download the `artifacts` according to the guide in the [Download](#download) section.

---
#### If you come across any issues, let me know! You can create an issue here or request help in [pk9r327](https://github.com/pk9r327)'s [Discord server](https://discord.gg/mYtgWabd33).