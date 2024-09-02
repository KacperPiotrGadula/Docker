1) Challenges encountered

- errors in dependencies:
    - package.json did not have the required dependencies by the running project. This resulted in showing errors from the dependencies
- design errors encountered:
    - 2.134 Could not find a required file.
    2.135   Name: index.js
    2.135   Searched in: /code/src

    4.698 src/index.js
    4.698   Line 10:1:  'ReactDOM' is not defined  no-undef
    4.698 Search for the keywords to learn more about each error.

    2.056 Could not find a required file.
    2.057   Name: index.html
    2.057   Searched in: /code/public

The errors resulted from the wrong file naming, and not adjusting the relationship files.

2) How to build docker image

docker image build -t <docker image name>:<version> .

docker container run -d -it --name=<docker container name> -p 8085:80 <docker image name>:<version>

3. Hadolint - a program that enables dockerfile validation

In powershell ->

$env:Path += ';<system location hodolint exe file>\'