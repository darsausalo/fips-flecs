fips-flecs
=========

fipsified flecs (https://github.com/SanderMertens/flecs)

fips build system: https://github.com/floooh/fips

## How to integrate:

Add the dependency to your fips.yml file:

```yaml
imports:
    fips-flecs:
        git: https://github.com/darsausalo/fips-flecs
```

Use flecs as dependency in your targets:

```cmake
fips_begin_*(...)
    ...
    fips_deps(flecs)
fips_end_*(...)
```
