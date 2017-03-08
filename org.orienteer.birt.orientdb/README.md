## OrientDB Birt Plugin (OrientDB ODA BIRT driver)

### What is this?

This is plugin for use [OrientDB](http://orientdb.com/) in [BIRT](https://www.eclipse.org/birt/) reports as DataSource. 
Can be used as [Eclipse plugin](insert link to plugin) or [Maven package](insert maven archetype link here)- it is need, if you use [BIRT runtime package](https://mvnrepository.com/artifact/org.eclipse.birt.runtime). 

### How to...

#### How to install as Eclipse plugin

- Run you Eclipse
- Follow Help->Install new software
- Add resource site [insert link to plugin](insert link to plugin)
- Install plugin. Plugin versions equals OrientDB versions.

#### How to install as Maven package

Include in your POM next snippets:

- Maven package depedency
```
<dependency>
  <groupId>org.orienteer.birt.orientdb</groupId>
  <artifactId>org.orienteer.birt.orientdb</artifactId>
  <version><!--Your version of OrientDB--></version>
</dependency>
```

- Workaround for use OSGI module loading

```
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-dependency-plugin</artifactId>
    <executions>
        <execution>
            <id>copy</id>
            <phase>install</phase>
            <goals>
                <goal>copy-dependencies</goal>
            </goals>
            <configuration>
            	<includeArtifactIds>org.orienteer.birt.orientdb</includeArtifactIds>
                <outputDirectory>
                  ${project.build.outputDirectory}/WEB-INF/lib
                </outputDirectory>
            </configuration>
        </execution>
    </executions>
</plugin>	
```