
A [Maven](https://maven.apache.org/) plugin to generate UML diagrams using [PlantUML](https://plantuml.sourceforge.net/) syntax. Artifacts are available from [Maven Central Repository](https://search.maven.org/search?q=g:cz.alry%20a:plantuml-maven-plugin)

# Usage

To generate images from PlantUML description add following dependency to your _pom.xml_:

```xml
...
<build>
  <plugins>
    <plugin>
      <groupId>cz.alry</groupId>
      <artifactId>plantuml-maven-plugin</artifactId>
      <version>1.5</version>
      <configuration>
        <sourceFiles>
          <directory>${basedir}</directory>
          <truncatePattern>src/main/*</truncatePattern>
          <includes>
            <include>src/main/plantuml/**/*.txt</include>
          </includes>
        </sourceFiles>
      </configuration>
      <dependencies>
        <dependency>
          <groupId>net.sourceforge.plantuml</groupId>
          <artifactId>plantuml</artifactId>
          <version>1.2018.11</version>
        </dependency>
      </dependencies>
    </plugin>
  </plugins>
</build>
```

Note that you must explicitely define the PlantUML version you want to use.

Then execute command:

```
mvn clean cz.alry:plantuml-maven-plugin:generate
```

# Extra configuration options

`outputDirectory` Directory where generated images are generated. Defaults to `${basedir}/target/plantuml`

`outputInSourceDirectory` Whether or not to generate images in same directory as the source file. Defaults to `false`.

`format` Output format. Defaults to `png`.

`verbose` Wether or not to output details during generation. Defaults to `false`.


Released under [Apache 2 license](http://www.apache.org/licenses/LICENSE-2.0.html).
