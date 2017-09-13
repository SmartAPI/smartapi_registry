[![Build Status](https://travis-ci.org/SmartAPI/smartapi_registry.svg?branch=master)](https://travis-ci.org/SmartAPI/smartapi_registry)

# SmartAPI Registry
This repo provides an optional place for those who need to have a place to host their own API metadata. Then they can register their API in [SmartAPI Project](http://smart-api.info) using the URL of their API metadata from this repo.

## How to add your API

1. First, each API should create a separate folder to host its metadata. The folder "_example_api" provides basic template for adding API metadata, so you can start with copying "_example_api" folder and renaming it to your API name.
2. Second, fill in the metadata about your API according to the instruction. Also please refer to the existing examples like "[mygene.info](mygene.info)" and "[myvariant.info](myvariant.info)" APIs.
3. Add an entry to [API_LIST.yml](API_LIST.yml) file following the existing example. This is the master list of the APIs available in this repo. Our SmartAPI application will import all the API metadata based on this file.

If you have the permission, commit your changes to this repo. Otherwise, feel free to submit a pull-request. Please check the "build status" badge above, and make sure it's green after your changes. We run some basic tests in this "[tests.py](tests.py)" for each commit.

## API_LIST.yml file
This is a YAML file at the root of this repo to keep track of all APIs available in this repo. Our SmartAPI application will import all the API metadata based on this file and render an API registry web frontend.

For each API, you just need to add a text block like this:

    - metadata: mygene.info/openapi_minimum.yml


* ***metadata*** field

  The value of this field should be either the URL or the relative path pointing to the API metadata. The API metadata should follow [OpenAPI specifications](https://www.openapis.org/), in either JSON or YAML format. Specifically, we support OpenAPI v3 specification documented [here](https://github.com/OAI/OpenAPI-Specification/blob/OpenAPI.next/versions/3.0.0.md), plus the SmartAPI extensions documented [here](https://github.com/SmartAPI/OpenAPI-Specification/blob/OpenAPI.next/versions/3.0.0.md).
