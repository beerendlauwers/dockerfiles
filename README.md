# `Dockerfile` overview

* `hakyll-host-to-host`: Mount a volume and pass it as a parameter to have the container build your site:
  
  Usage:
  
  ```
  $ docker build -t=host2host .
  $ docker run -i -t -v PATH/TO/DIRECTORY/ON/HOST:/artifacts host2host "/artifacts"
  ```
  
* `hakyll-repo-to-host`: Given a public Git repository and a branch, pulls the repository, switches to the branch and builds it. Then it outputs it to the `/artifacts` mounted volume.

  Usage:
  
  ```
  $ docker build -t=repo2host .
  $ docker run -i -t -v PATH/TO/DIRECTORY/ON/HOST:/artifacts repo2host "https://github.com/beerendlauwers/beerendlauwers.github.io.git" "remotes/origin/code"
  ```
