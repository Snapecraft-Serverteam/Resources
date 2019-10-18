## Motivation
Isn't it annoying to always have to copy your exported plugins into the `plugins` folder of your testing server?

Well, no more, because here's how to let Maven do the work:

## Guide
First of all, make sure that you are using Maven for your project.
If you do use Maven, add this plugin to your pom.xml file:

```xml
            <plugin>
                <artifactId>maven-antrun-plugin</artifactId>
                <version>1.8</version>
                <executions>
                    <execution>
                        <id>copy</id>
                        <phase>package</phase>
                        <configuration>
                            <target>
                                <echo>Copying plugin file to:</echo>
                                <echo>${project.basedir}</echo>
                                <copy todir="${project.basedir}/server/plugins" overwrite="true" flatten="true">
                                    <fileset dir="${project.basedir}/target" includes="${project.artifactId}-${project.version}.jar" >
                                        <include name="*.jar" />
                                    </fileset>
                                </copy>
                            </target>
                        </configuration>
                        <goals>
                            <goal>run</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>
```

See that <copy...> bracket? `todir` describes the directory where Maven should copy the plugin file. `${project.basedir}` will be filled in by maven automatically, it's just the root directory of your project, where the pom.xml file is located.
The `dir` parameter in the `<fileset>` bracket describes the directory where Maven should copy the file from.

You have to place it in the <plugins> brackets of your pom.xml file. These are in the <build> brackets.

**If you are already running your Spigot server in intelliJ and have set it up using [this]() guide, this should work OOB** (out of the box)

## Appendix
This is an example pom.xml file that enables Auto-Copy:
[Click here to open on GitHub Gist](https://gist.github.com/realmayus/276edd1ae4c0d6733d441e8ad3c4eb3f)
