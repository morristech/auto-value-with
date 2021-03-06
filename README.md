# AutoValue: With Extension

An extension for Google's [AutoValue][auto] that implements "with-er" methods for AutoValue objects.

**Note**: This is an early version that requires the extension support currently in AutoValue 1.2-SNAPSHOT.

## Usage

Include auto-value-with in your project and "with-er" methods to your auto-value objects.

```java
@AutoValue public abstract class User {
  abstract String id();
  abstract String name();
  abstract String email();

  abstract User withEmail(String email);

  // you can also use multiple
  abstract User withNameAndEmail(String name, String email);
}
```

The extension will generate an implementation of `withEmail(String)` that returns a new instance of `User` with the given email.


By convention "with-er" methods have to use `with` as prefix and use the exact property name for both method name and parameter name.



## Download

Add a Gradle dependency (Android):

```groovy
annotationProcessor 'com.gabrielittner.auto.value:auto-value-with:1.1.0-rc1'
```

or Gradle (Java):

```groovy
apt 'com.gabrielittner.auto.value:auto-value-with:1.1.0-rc1'
```
(Using the [gradle-apt-plugin][apt])

or Maven:
```xml
<dependency>
  <groupId>com.gabrielittner.auto.value</groupId>
  <artifactId>auto-value-with</artifactId>
  <version>1.0.0</version>
  <scope>provided</scope>
</dependency>
```

Snapshots of the development version are available in [Sonatype's `snapshots` repository][snap].

## License


```
Copyright 2016 Gabriel Ittner.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```



 [auto]: https://github.com/google/auto
 [snap]: https://oss.sonatype.org/content/repositories/snapshots/
 [apt]: https://github.com/tbroyer/gradle-apt-plugin

