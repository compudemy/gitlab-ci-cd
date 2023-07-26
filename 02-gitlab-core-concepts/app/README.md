## Notes


scripts are build with yaml configurations 

an example snippet is seen in the code thus

```yaml
    run_test:
        before_script:
            - echo "preparing test data"
        script:
            - echo "Running Test"
        after_script:
            - echo "cleaning up temporary files"

```

``The before script``: this command runs before the script command

``The after script``: this command runs after each job, including failed jobs, 

``Job Keywords``: these are reserved keywords for the gitlab configuration files, an example is 

- before_script
- after_script

you will learn more as the lectures proceeds