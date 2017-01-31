#### Notes for building Docker container on Blumix (can't build locally)

To create a docker container on blumix
`cf ic cpi mysql registry.ng.bluemix.net/${cf ic namespace get}/mysql`

edit the Dockerfile to be:
`FROM registry.ng.bluemix.net/namespace/mysql`

Then build the docker image
`cf ic build -t registry.ng.bluemix.net/namespace/mysql-abc .`

Be careful with the names though, you do not want to write to the same name)
