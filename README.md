# China website

This contains information for the trip to China for young orienteers.

[Jekyll](https://jekyllrb.com/) is used to render the site and serve it on github.io.

[TravisCI](https://travis-ci.org/) is used to build and deploy the code. All branches are build, only `master` is deployed. Deployment is done to the `gh-pages` branch.

To serve the site locally and rebuild it on updates using Docker, run `docker-compose up -d`. When you're done, run `docker-compose down`. If you modify `config.yml`, you'll need to do a `docker-compose restart`. You'll need to modify `docker-compose.yml` to point to the correct path where you have your code checked out.

[Live site](https://bwindsor.github.io/china)
