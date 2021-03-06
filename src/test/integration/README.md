# ID Images API Integration Tests

This directory contains files that run integration tests against the ID Images API.

First, create a configuration.json file from configuration_example.json. "osu_id_no_image" should be an OSU ID that exists but doesn't have an ID Card image associated with it in Banner. "osu_id_with_image" should be an OSU ID that has an ID Card image associated with it in Banner.

Next, use these commands to build and run the container. All you need installed is Docker.

    docker build -t idimages-tests .
    # Run the integration tests in *nix
    docker run -v "$PWD"/configuration.json:/usr/src/app/configuration.json:ro idimages-tests
    # Run the integration tests in Windows
    docker run -v c:\path\to\configuration.json:/c:\usr\src\app\configuration.json:ro idimages-tests

Successfully passing all the tests with the command above would output this result:

![success_test](images/success.png)