# sortpom-config

Configuration resource for the [maven-sortpom-plugin](https://code.google.com/p/sortpom).

This plugin may cause problems if dependencies and/or plugins are dependent on
order of specification.

---

## Sample Usage

The following plugin configuration will run after every build, resorting the
POM file if it is not already sorted.

```
<build>
    <plugins>
        ...
        <plugin>
            <groupId>com.google.code.sortpom</groupId>
            <artifactId>maven-sortpom-plugin</artifactId>
            <version>2.3.0</version>
            <configuration>
                <sortOrderFile>com/shankyank/pom_sort_order.xml</sortOrderFile>
                <lineSeparator>\n</lineSeparator>
                <encoding>UTF8</encoding>
                <sortProperties>true</sortProperties>
                <keepBlankLines>true</keepBlankLines>
                <sortDependencies>scope,groupId,artifactId</sortDependencies>
                <sortPlugins>groupId,artifactId</sortPlugins>
                <nrOfIndentSpace>4</nrOfIndentSpace>
                <createBackupFile>false</createBackupFile>
            </configuration>
            <dependencies>
                <dependency>
                    <groupId>com.shankyank</groupId>
                    <artifactId>sortpom-config</artifactId>
                    <version>1.0</version>
                </dependency>
            </dependencies>
            <executions>
                <execution>
                    <goals>
                        <goal>verify</goal>
                    </goals>
                    <phase>verify</phase>
                </execution>
            </executions>
        </plugin>
        ...
    </plugins>
</build>
```
