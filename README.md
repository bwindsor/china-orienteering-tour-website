# China website

This contains information for the trip to China for young orienteers.

[Jekyll](https://jekyllrb.com/) is used to render the site and serve it on github.io.

[TravisCI](https://travis-ci.org/) is used to build and deploy the code. All branches are build, only `master` is deployed. Deployment is done to the `gh-pages` branch.

Multiple languages are managed by the `jekyll-multiple-languages-plugin` plugin for Jekyll.

## Locally running the site
To serve the site locally and rebuild it on updates using Docker, run `docker-compose up -d`. When you're done, run `docker-compose down`. If you modify `config.yml`, you'll need to do a `docker-compose restart`. You'll need to modify `docker-compose.yml` to point to the correct path where you have your code checked out.

Here is the [live site](https://bwindsor.github.io/china)


## Development setup (Windows)
You will need a github account.

1. Download and install [Git for Windows](https://git-scm.com/download/win)
2. Open a command prompt. (Start -> Run -> cmd)
3. Run `cd C:\path\to\my\folder`, replacing the directory with the place where you want to put the code
4. Run `git clone https://github.com/bwindsor/china.git`. This copies the code to your computer.
5. Now, using a text editor of your choice (Notepad++ is a very basic option, but something like [Visual Studio Code](https://code.visualstudio.com/) is better), you can make modifications to the website (see section below)
6. When you've made your changes, run `git add .` to add all files in the current folder, then `git commit -m "Description of change"`. Make sure you put quotes around your message. You should replace `Description of change` with a message describing what it is you changed about the website.
7. Run `git push`. This will copy your changes back to the internet.
8. After a few minutes, your changes should appear on the deployed version of the website [here](https://bwindsor.github.io/china)

## Modifying the website
### Translations
Translations are stored under the `_i18n` directory. Within this, there are folders for each language. Modifying the files in the `cz` subfolder will change the translations for the Czech version of the site. Files are written in [markdown](https://en.wikipedia.org/wiki/Markdown) format. Here's a [markdown cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

The files `en.yml`, `cz.yml`, and so on are where translations of specific phrases are stored. These two files should have the same structure, but just different values for the keys in each.

### Add a new page
To add a new page, the following needs changing:
1. Add the page to `_data/navigation`
2. Create the page in the `pages` folder with the same structure as the other files - this refers to the translated version of the file for each language.
3. Create the file in each of the `_i18n/en`, `_i18n/cz` folders, and so on, which contain each translation of the page.

### Add a new language
To add a new language, the following needs changing:
1. Add the language abbreviation (e.g. `en`) to the `languages` key in `_config.yml`
2. Add a `.yml` file under `_i18n` with the equivalent translations for your new language (e.g. `en.yml`)
3. Add a folder under `_i18n` with the name of your new language, and translated copies of all the markdown files from one of the existing folders
4. Under `assets/images` add a `.svg` file with the flag of your new language

### Disable a language
Just remove that language from the `languages` key in `_config.yml`.
