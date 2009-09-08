hadoop-maven

This project contains POM files for installing Apache Hadoop Core with
Maven 2.

These POMs work with Apache Hadoop 0.18.3.

Unfortunately, the Hadoop distribution is packaged with a number of
non-standard JARs, including custom builds of some libraries, which
are not found in public Maven repositories.  Therefore, there are two
different POMs provided here:


core-pom.xml:

  This POM installs only the hadoop-0.18.3-core.jar file in your local
  Maven repository.  It does not include any dependencies.

  You can refer to this artifact in your projects as:

      <dependency>
        <groupId>org.apache.hadoop</groupId>
        <artifactId>hadoop-core</artifactId>
        <version>0.18.3</version>
      </dependency>


core-with-dependencies.xml

  This POM merges the hadoop-0.18.3-core.jar, hadoop-0.18.3-tools.jar,
  and all the JAR files in the lib/ directory of the Hadoop
  distribution into one large JAR named
  hadoop-core-with-dependencies-0.18.3.jar.

  This does not include the native code libraries.

  You can refer to this artifact in your projects as:

      <dependency>
        <groupId>org.apache.hadoop</groupId>
        <artifactId>hadoop-core-with-dependencies</artifactId>
        <version>0.18.3</version>
      </dependency>



To install Hadoop using these POMs:

1. Download the Apache Hadoop Core 0.18.3 distribution.
2. Copy your preferred POM file into the Hadoop directory.
3. In the Hadoop directory, run:

    mvn -f name-of-pom.xml install

The project will be installed in your local Maven 2 repository and can
be referenced as a dependency in your own POMs.

If you maintain your own Maven 2 repository, you can add a
<distributionManagement> section to the pom.xml and then run
"mvn deploy" to deploy it.



   Copyright 2009 Stuart Sierra

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
