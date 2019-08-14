# axion-release_issue249
exemplary repo to reproduce allegro/axion-release-plugin/issues/249

To reproduce the issue:

1. Clone gralde project as regular git repo

```
git clone git@github.com:edio/axion-release_issue249_gradle.git
cd axion-release_issue249_gradle
./gradlew cV
```

correct version `1.2.3` is reported

2. Clone gralde project as a submodule (this repository already has it added)

```
git clone --recursive git@github.com:edio/axion-release_issue249.git
cd axion-release_issue249/axion-release_issue249_gradle
./gradlew cV
```

The plugin fails to detect `.git/` location

```
Failed to open repository, trying to work without it org.eclipse.jgit.errors.RepositoryNotFoundException: repository not found: /tmp/axion-release_issue249/axion-release_issue249_gradle
Could not resolve current position on uninitialized repository, returning default
Couldn't perform check uncommitted changes command on uninitialized repository
:currentVersion

Project version: 0.1.0-SNAPSHOT
```

