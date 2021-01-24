# Introduction

PowerShell module for interacting with Docker Engine and Docker Registry

[![Build status](https://ci.appveyor.com/api/projects/status/hx2asalvycum5lj0?svg=true)](https://ci.appveyor.com/project/nicholasdille/powershell-dockerregistry) [![Download](https://img.shields.io/badge/powershellgallery-DockerRegistry-blue.svg)](https://www.powershellgallery.com/packages/DockerRegistry/)

get manifests (in v2 schema)

post every layer.digest in the new repo

post config.layer

put whole manifest to new repo

details:

GET manifest from reg:5000/v2/{oldRepo}/manifests/{oldtag} withaccept header:application/vnd.docker.distribution.manifest.v2+json

For every layer : POST reg:5000/v2/{newRepo}/blobs/uploads/?mount={layer.digest}&from={oldRepoNameWithaoutTag}

POST reg:5000/v2/{newRepo}/blobs/uploads/?mount={config.digest}&from={oldRepoNameWithaoutTag}

PUT reg:5000/v2/{newRepo}/manifests/{newTag} with content-type header:application/vnd.docker.distribution.manifest.v2+json and body from step 1 response

enjoy!
