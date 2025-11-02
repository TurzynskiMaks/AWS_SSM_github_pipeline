# How does it work?

Using github actions, and prebuilt python script, on every push onto 'main branch', workflow file activate a series of events, such as:
    logging into dockerhub with credentials stored in github secrets
    using python script it iterates through every directory included in root folder, looking for a Dockerfile
        When it finds one, script then builds and pushes it into repository
    Then it SSHs into EC2...
    ... Pulls docker-compose.yml, in case of any changes here...
    ... and gets it running, therefore pulls images from dockerhub repo!
