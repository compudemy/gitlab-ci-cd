
## first Execution

```yaml
    run_test:
    before_script:
        - echo "preparing test data"
    script:
        - echo "Running Test"
    after_script:
        - echo "cleaning up temporary files"

    build_image:
    script:
        - echo "Building the docker image"
        - echo "Tagging Docker image"

    push_image:
    script:
        - echo "logging into Docker registery"
        - echo "Pushing docker image into registery"
```

## Execution with stages

```yaml
stages:
  - test
  - build
  - deploy

run_unit_test:
  stage: test
  before_script:
    - echo "preparing test data"
  script:
    - echo "Running Test"
  after_script:
    - echo "cleaning up temporary files"

run_lint_test:
  stage: test
  before_script:
    - echo "preparing test data"
  script:
    - echo "Running Test"
  after_script:
    - echo "cleaning up temporary files"

build_image:
  stage: build
  script:
    - echo "Building the docker image"
    - echo "Tagging Docker image"

push_image:
  stage: build
  script:
    - echo "logging into Docker registery"
    - echo "Pushing docker image into registery"

deploy_image:
  stage: deploy
  script:
    - echo "Deploying new docker image to dev server"
```

## Needs and Dependencies Job

```yaml

push_image:
  stage: build
  needs:
    - build_image
  script:
    - echo "logging into Docker registery"
    - echo "Pushing docker image into registery"

```

