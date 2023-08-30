## Project description

This is an example project that demonstrates a bug plugin micronaut aot and `io.micronaut.test-resources` plugin

### Project structure
1. The project has 2 modules: [module1](./modules/module1) and [module2](./modules/module2).
2. Both modules have an empty `build.gradle`
3. The root [build.gradle](./build.gradle) has all necessary information.
4. We declareted plugins as:
   ```groovy
    plugins {
      id("com.github.johnrengelman.shadow") version "$johnrengelmanVVersion" apply false
      id("io.micronaut.application") version "$micronautLibraryVersion" apply false
      id("io.micronaut.library") version "$micronautLibraryVersion" apply false
      id("io.micronaut.test-resources") version "$micronautTestResourceVersion" apply false
      id("io.micronaut.aot") version "$micronautAotVersion" apply false
    }
   ```
5. in `subproject {` We just apply their plugins to the current subproject
6. When we try to compile: `gradle clean build we can see the error`
7. When we comment line 13 in [build.gradle](./build.gradle) and then compile the project. The problem was solved 