Добавление темы на сайт GitHub Pages с помощью Jekyll
Вы можете персонализировать свой сайт Jekyll, добавив и настроив тему оформления.

Кто может использовать эту функцию?
GitHub Pages доступен в общедоступных репозиториях с GitHub Free и GitHub Free для организаций, а также в общедоступных и частных репозиториях с GitHub Pro, GitHub Team, GitHub Enterprise Cloudи GitHub Enterprise Server. Дополнительные сведения см. в разделе "Планы GitHub".

GitHub Pages теперь использует GitHub Actions для выполнения сборки Jekyll. При использовании ветви в качестве источника сборки GitHub Actions необходимо включить в репозитории, если вы хотите использовать встроенный рабочий процесс Jekyll. Кроме того, если GitHub Actions недоступен или отключен, добавление .nojekyll файла в корень исходной ветви будет обойти процесс сборки Jekyll и развернуть содержимое напрямую. Дополнительные сведения о включении GitHub Actionsсм. в разделе "Управление параметрами GitHub Actions для репозитория".

В этой статье
Adding a theme
Customizing your theme's CSS
Customizing your theme's HTML layout
Further reading
People with write permissions for a repository can add a theme to a GitHub Pages site using Jekyll.

If you are publishing from a branch, changes to your site are published automatically when the changes are merged into your site's publishing source. If you are publishing from a custom GitHub Actions workflow, changes are published whenever your workflow is triggered (typically by a push to the default branch). If you want to preview your changes first, you can make the changes locally instead of on GitHub. Then, test your site locally. For more information, see "Testing your GitHub Pages site locally with Jekyll."

Adding a theme
On GitHub, navigate to your site's repository.

Navigate to the publishing source for your site. For more information, see "Configuring a publishing source for your GitHub Pages site."

Navigate to _config.yml.

In the upper right corner of the file view, click  to open the file editor.

Screenshot of a file. In the header, a button, labeled with a pencil icon, is outlined in dark orange.
Note: Instead of editing and committing the file using the default file editor, you can optionally choose to use the github.dev code editor by selecting the  dropdown menu and clicking github.dev. You can also clone the repository and edit the file locally via GitHub Desktop by clicking GitHub Desktop.

Screenshot of a file. In the header, a downwards-facing triangle icon is outlined in dark orange.
Add a new line to the file for the theme name.

To use a supported theme, type theme: THEME-NAME, replacing THEME-NAME with the name of the theme as shown in the _config.yml of the theme's repository (most themes follow a jekyll-theme-NAME naming convention). For a list of supported themes, see "Supported themes" on the GitHub Pages site. For example, to select the Minimal theme, type theme: jekyll-theme-minimal.
To use any other Jekyll theme hosted on GitHub, type remote_theme: THEME-NAME, replacing THEME-NAME with the name of the theme as shown in the README of the theme's repository.
Click Commit changes...

In the "Commit message" field, type a short, meaningful commit message that describes the change you made to the file. You can attribute the commit to more than one author in the commit message. For more information, see "Creating a commit with multiple authors."

If you have more than one email address associated with your account on GitHub, click the email address drop-down menu and select the email address to use as the Git author email address. Only verified email addresses appear in this drop-down menu. If you enabled email address privacy, then a no-reply will be the default commit author email address. For more information about the exact form the no-reply email address can take, see "Setting your commit email address."

Screenshot of a GitHub pull request showing a dropdown menu with options to choose the commit author email address. octocat@github.com is selected.
Below the commit message fields, decide whether to add your commit to the current branch or to a new branch. If your current branch is the default branch, you should choose to create a new branch for your commit and then create a pull request. For more information, see "Creating a pull request."

Screenshot of a GitHub pull request showing a radio button to commit directly to the main branch or to create a new branch. New branch is selected.
Click Commit changes or Propose changes.

Customizing your theme's CSS
These instructions work best with themes that are officially supported by GitHub Pages. For a complete list of supported themes, see "Supported themes" on the GitHub Pages site.

Your theme's source repository may offer some help in customizing your theme. For example, see Minimal's README.

On GitHub, navigate to your site's repository.

Navigate to the publishing source for your site. For more information, see "Configuring a publishing source for your GitHub Pages site."

Create a new file called /assets/css/style.scss.

Add the following content to the top of the file:

---
---

@import "{{ site.theme }}";
Add any custom CSS or Sass (including imports) you'd like immediately after the @import line.

Customizing your theme's HTML layout
These instructions work best with themes that are officially supported by GitHub Pages. For a complete list of supported themes, see "Supported themes" on the GitHub Pages site.

Your theme's source repository may offer some help in customizing your theme. For example, see Minimal's README.

On GitHub, navigate to your theme's source repository. For example, the source repository for Minimal is https://github.com/pages-themes/minimal.
In the _layouts folder, navigate to your theme's default.html file.
Copy the contents of the file.
On GitHub, navigate to your site's repository.
Navigate to the publishing source for your site. For more information, see "Configuring a publishing source for your GitHub Pages site."
Create a file called _layouts/default.html.
Paste the default layout content you copied earlier.
Customize the layout as you'd like.
