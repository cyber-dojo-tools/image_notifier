
[![CircleCI](https://circleci.com/gh/cyber-dojo-languages/image_notifier.svg?style=svg)](https://circleci.com/gh/cyber-dojo-languages/image_notifier)

- issues http POST requests to CircleCI projects to trigger their workflows
- receives the names of the projects to trigger from [cyberdojofoundation/image_dependents](https://github.com/cyber-dojo-languages/image_dependents)
- used in the main [build_test_push_notify.sh](https://github.com/cyber-dojo-languages/image_builder/blob/master/build_test_push_notify.sh) script of all [cyber-dojo-languages](https://github.com/cyber-dojo-languages) repos .circleci/config.yml files

```bash
$ DEPENDENTS="csharp-moq csharp-nunit csharp-specflow"
$ docker run \
  --env CIRCLE_API_MACHINE_USER_TOKEN \
  --rm \
    cyberdojofoundation/image_notifier \
      ${DEPENDENTS}

# curl ... https://circleci.com/api/v1.1/project/github/cyber-dojo-languages/csharp-moq/tree/master
# curl ... https://circleci.com/api/v1.1/project/github/cyber-dojo-languages/csharp-nunit/tree/master
# curl ... https://circleci.com/api/v1.1/project/github/cyber-dojo-languages/csharp-specflow/tree/master
```

- - - -

![cyber-dojo.org home page](https://github.com/cyber-dojo/cyber-dojo/blob/master/shared/home_page_snapshot.png)
