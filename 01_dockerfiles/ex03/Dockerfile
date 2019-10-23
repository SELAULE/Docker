
Docker can be useful to test an application that’s still being developed without polluting your libraries. You will have to design a Dockerfile that gets the development
version of Gitlab - Community Edition installs it with all the dependencies and the necessary configurations, and launches the application, all as it builds. The container will be
deemed valid if you can access the web client, create users and interact via GIT with this
container (HTTPS and SSH). Obviously, you are not allowed to use the official container
from Gitlab, it would be a shame...

ANS

FROM ubuntu:16.04

RUN apt-get update
RUN apt-get install -y curl openssh-server ca-certificates postfix
RUN curl -sS https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | bash
RUN apt-get install -y gitlab-ce
RUN apt-get install -y vim
RUN echo "registry_external_url \"https://registry.example.com\"" >> /etc/gitlab/gitlab.rb
RUN echo "mattermost_external_url \"https://mattermost.example.com\"" >> /etc/gitlab/gitlab.rb
RUN cat /etc/gitlab/gitlab.rb
RUN gitlab-ctl reconfigure