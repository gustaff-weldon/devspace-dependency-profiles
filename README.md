This repository contains main project and subproject.
main-project depends on subprojecy

To reproduce issue.
```
❯ cd ../main-project
❯ devspace deploy
```

You will get an error:
```
info Using namespace 'devspace'
info Using kube context 'docker-desktop'
sub-project couldn't find flag profile
fatal exit status 1
```

If you try to deploy just the project a:
```
❯ cd sub-project
❯ devspace deploy
```

It works fine

In this repro I have used global `profile`  flag but it also fails if I try to read deploy flag eg.:
```
❯ devspace deploy
info Using namespace 'devspace'
info Using kube context 'docker-desktop'
sub-project couldn't find flag build-sequential
fatal exit status 1
```
