# GitHub Fork Default

This TamperMonkey script helps with the situation where you have a fork of a repository, and you don't want to break the upstream relationship, but you also don't want your Pull Requests to go to the upstream repository _by default_. As of writing this, GitHub has neglected this issue for at least 3 1/2 years (since February 2022), and the only workaround proposed thus far is to permanently sever the upstream relationship by using the "Leave fork network" option.

What this little script does is, you can configure one or more repositories so that they default to themselves when making pull requests. Then, the next time you click "Compare & pull request" or "Open pull request", when it detects that a new Pull Request page has loaded for creating a pull request against the upstream repository, it immediately redirects to the equivalent page for making a pull request against your fork. If you want to override it, you can click "Back" to return to the upstream repository version and it'll let you use it.

With this script installed, a new button is injected into the Pull Request view to allow you to configure which repositories should be given this treatment:

<img width="584" height="145" alt="image" src="https://github.com/user-attachments/assets/ac8941a5-8fd7-447a-b65f-37e3eb16244e" />

In this version, the resulting window is not very polished, but it does work. A future version might improve on things :-)

<img width="1453" height="797" alt="image" src="https://github.com/user-attachments/assets/1cceedf5-a040-49a1-9f2c-b12f0aa6ee5a" />

As shown here, simply specify your repositories in the format "USERNAME/REPONAME".

## Installing

This script is hosted on Greasy Fork.

https://greasyfork.org/en/scripts/544320-github-fork-default

To install it through Greasy Fork, navigate to the script's page and then click on the green "Install this script" button.

### Manual Installation

You can install the script the old-fashioned way if you want. I've always done it this way:

1. Pull up the script's source code: [script.js](https://raw.githubusercontent.com/logiclrd/GitHubForkDefault/refs/heads/main/script.js?raw=1)

2. Copy it to the clipboard.

3. Click on the TamperMonkey extension's icon and click on "Create a new script..."

    <img width="441" height="543" alt="image" src="https://github.com/user-attachments/assets/54c66a55-a892-4eac-915a-429b932649e6" />

4. Paste the script text into the Editor.

5. Press Ctrl+S to save.

6. Refresh any tab where you want it to be active.

## Uninstalling

1. Click on the TamperMonkey extension's icon and click on "Dashboard".

2. In the "Installed Userscripts" tab, locate "GitHub Fork Default".

3. Click on the little trash can icon at the far right of the row to uninstall it.

It is also possible to temporarily disable it if you need.

## Why is it active on all pages?

The functionality of disabling the redirect when you click Back, if you really do want an upstream PR, depends on knowing what URL the tab came _from_. This script matches every URL so that it can stash the URL in TamperMonkey's per-tab data, so that when you click Back, it knows whether you were on the Create Pull Request page it sent you to or not.

## Contributing

Source code is in GitHub:

https://github.com/logiclrd/GitHubForkDefaults/

Feel free to fork it and propose PRs. :-)
