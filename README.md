This repository contains main project and subproject.
main-project depends on subproject

When using profiles, they do not seem to be applied to dependencies, even when passed explicitly to `run_dependencies`

To reproduce issue.
```
❯ cd main-project
❯ devspace deploy --profile test
```

Check cluster, you'll see that main project is using `alpine:3.15` as an image, but the dependency did not get it applied from profile.

If you try to deploy just the sub-project:
```
❯ cd sub-project
❯ devspace deploy --profile test
```

It works fine, container runs with a a proper profile image.
