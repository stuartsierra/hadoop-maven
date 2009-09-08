hadoop-maven

This project contains a POM file for installing the Apache Hadoop JAR
files with Maven 2.

This POM works with Apache Hadoop 0.18.3.

The installation created by this POM is *not* currently suitable for
running Hadoop on a cluster.  It does not include the native-code
libraries and may be missing some dependencies.  However, it is
sufficient for compiling code that depends on the Hadoop APIs.


To use this project:

1. Download the Apache Hadoop Core 0.18.3 distribution.
2. Copy pom.xml into the distribution directory. 
3. Run "mvn install" in the distribution directory.

The Hadoop core JAR is now installed in your local Maven 2 repository.
You can reference Hadoop as a dependency in your Maven projects with
the following in your pom.xml:

    <dependencies>
      ...

      <dependency>
        <groupId>org.apache.hadoop</groupId>
        <artifactId>hadoop-core</artifactId>
        <version>0.18.3</version>
      </dependency>

      ...
    </dependencies>


If you maintain your own Maven 2 repository, you can add your own
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
