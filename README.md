# Data Prep

![cm-available](https://cdap-users.herokuapp.com/assets/cm-available.svg)
![cdap-transform](https://cdap-users.herokuapp.com/assets/cdap-transform.svg)
[![Build Status](https://travis-ci.org/cdapio/hydrator-plugins.svg?branch=develop)](https://travis-ci.org/cdapio/hydrator-plugins)
[![Coverity Scan Build Status](https://scan.coverity.com/projects/11434/badge.svg)](https://scan.coverity.com/projects/hydrator-wrangler-transform)
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/io.cdap.wrangler/wrangler-core/badge.svg)](https://maven-badges.herokuapp.com/maven-central/io.cdap.wrangler/wrangler-core)
[![Javadoc](https://javadoc-emblem.rhcloud.com/doc/io.cdap.wrangler/wrangler-core/badge.svg)](http://www.javadoc.io/doc/io.cdap.wrangler/wrangler-core)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Join CDAP community](https://cdap-users.herokuapp.com/badge.svg?t=wrangler)](https://cdap-users.herokuapp.com?t=1)

A collection of libraries, a pipeline plugin, and a CDAP service for performing data
cleansing, transformation, and filtering using a set of data manipulation instructions
(directives). These instructions are either generated using an interative visual tool or
are manually created.

  * Data Prep defines few concepts that might be useful if you are just getting started with it. Learn about them [here](wrangler-docs/concepts.md)
  * The Data Prep Transform is [separately documented](wrangler-transform/wrangler-docs/data-prep-transform.md).
  * [Data Prep Cheatsheet](wrangler-docs/cheatsheet.md)

## New Features

More [here](wrangler-docs/upcoming-features.md) on upcoming features.

  * **User Defined Directives, also known as UDD**, allow you to create custom functions to transform records within CDAP DataPrep or a.k.a Wrangler. CDAP comes with a comprehensive library of functions. There are however some omissions, and some specific cases for which UDDs are the solution. Additional information on how you can build your custom directives [here](wrangler-docs/custom-directive.md).
    * Migrating directives from version 1.0 to version 2.0 [here](wrangler-docs/directive-migration.md)
    * Information about Grammar [here](wrangler-docs/grammar/grammar-info.md)
    * Various `TokenType` supported by system [here](../api/src/main/java/io/cdap/wrangler/api/parser/TokenType.java)
    * Custom Directive Implementation Internals [here](wrangler-docs/udd-internal.md)

  * A new capability that allows CDAP Administrators to **restrict the directives** that are accessible to their users.
More information on configuring can be found [here](wrangler-docs/exclusion-and-aliasing.md)

## Demo Videos and Recipes

Videos and Screencasts are best way to learn, so we have compiled simple, short screencasts that shows some of the features of Data Prep. Additional videos can be found [here](https://www.youtube.com/playlist?list=PLhmsf-NvXKJn-neqefOrcl4n7zU4TWmIr)

### Videos

  * [SCREENCAST] [Creating Lookup Dataset and Joining](https://www.youtube.com/watch?v=Nc1b0rsELHQ)
  * [SCREENCAST] [Restricted Directives](https://www.youtube.com/watch?v=71EcMQU714U)
  * [SCREENCAST] [Parse Excel files in CDAP](https://www.youtube.com/watch?v=su5L1noGlEk)
  * [SCREENCAST] [Parse File As AVRO File](https://www.youtube.com/watch?v=tmwAw4dKUNc)
  * [SCREENCAST] [Parsing Binary Coded AVRO Messages](https://www.youtube.com/watch?v=Ix_lPo-PDJY)
  * [SCREENCAST] [Parsing Binary Coded AVRO Messages & Protobuf messages using schema registry](https://www.youtube.com/watch?v=LVLIdWnUX1k)
  * [SCREENCAST] [Quantize a column - Digitize](https://www.youtube.com/watch?v=VczkYX5SRtY)
  * [SCREENCAST] [Data Cleansing capability with send-to-error directive](https://www.youtube.com/watch?v=aZd5H8hIjDc)
  * [SCREENCAST] [Building Data Prep from the GitHub source](https://youtu.be/pGGjKU04Y38)
  * [VOICE-OVER] [End-to-End Demo Video](https://youtu.be/AnhF0qRmn24)
  * [SCREENCAST] [Ingesting into Kudu](https://www.youtube.com/watch?v=KBW7a38vlUM)
  * [SCREENCAST] [Realtime HL7 CCDA XML from Kafka into Time Parititioned Parquet](https://youtu.be/0fqNmnOnD-0)
  * [SCREENCAST] [Parsing JSON file](https://youtu.be/vwnctcGDflE)
  * [SCREENCAST] [Flattening arrays](https://youtu.be/SemHxgBYIsY)
  * [SCREENCAST] [Data cleansing with send-to-error directive](https://www.youtube.com/watch?v=aZd5H8hIjDc)
  * [SCREENCAST] [Publishing to Kafka](https://www.youtube.com/watch?v=xdc8pvvlI48)
  * [SCREENCAST] [Fixed length to JSON](https://www.youtube.com/watch?v=3AXu4m1swuM)

### Recipes

  * [Parsing Apache Log Files](wrangler-demos/parsing-apache-log-files.md)
  * [Parsing CSV Files and Extracting Column Values](wrangler-demos/parsing-csv-extracting-column-values.md)
  * [Parsing HL7 CCDA XML Files](wrangler-demos/parsing-hl7-ccda-xml-files.md)

## Available Directives

These directives are currently available:

| Directive                                                              | Description                                                      |
| ---------------------------------------------------------------------- | ---------------------------------------------------------------- |
| **Parsers**                                                            |                                                                  |
| [JSON Path](wrangler-docs/directives/json-path.md)                              | Uses a DSL (a JSON path expression) for parsing JSON records     |
| [Parse as AVRO](wrangler-docs/directives/parse-as-avro.md)                      | Parsing an AVRO encoded message - either as binary or json       |
| [Parse as AVRO File](wrangler-docs/directives/parse-as-avro-file.md)            | Parsing an AVRO data file                                        |
| [Parse as CSV](wrangler-docs/directives/parse-as-csv.md)                        | Parsing an input record as comma-separated values                |
| [Parse as Date](wrangler-docs/directives/parse-as-date.md)                      | Parsing dates using natural language processing                  |
| [Parse as Excel](wrangler-docs/directives/parse-as-excel.md)                    | Parsing excel file.                                              |
| [Parse as Fixed Length](wrangler-docs/directives/parse-as-fixed-length.md)      | Parses as a fixed length record with specified widths            |
| [Parse as HL7](wrangler-docs/directives/parse-as-hl7.md)                        | Parsing Health Level 7 Version 2 (HL7 V2) messages               |
| [Parse as JSON](wrangler-docs/directives/parse-as-json.md)                      | Parsing a JSON object                                            |
| [Parse as Log](wrangler-docs/directives/parse-as-log.md)                        | Parses access log files as from Apache HTTPD and nginx servers   |
| [Parse as Protobuf](wrangler-docs/directives/parse-as-log.md)                   | Parses an Protobuf encoded in-memory message using descriptor    |
| [Parse as Simple Date](wrangler-docs/directives/parse-as-simple-date.md)        | Parses date strings                                              |
| [Parse XML To JSON](wrangler-docs/directives/parse-xml-to-json.md)              | Parses an XML document into a JSON structure                     |
| [Parse as Currency](wrangler-docs/directives/parse-as-currency.md)              | Parses a string representation of currency into a number.        |
| [Parse as Datetime](wrangler-docs/directives/parse-as-datetime.md)              | Parses strings with datetime values to CDAP datetime type        |
| **Output Formatters**                                                  |                                                                  |
| [Write as CSV](wrangler-docs/directives/write-as-csv.md)                        | Converts a record into CSV format                                |
| [Write as JSON](wrangler-docs/directives/write-as-json-map.md)                  | Converts the record into a JSON map                              |
| [Write JSON Object](wrangler-docs/directives/write-as-json-object.md)           | Composes a JSON object based on the fields specified.            |
| [Format as Currency](wrangler-docs/directives/format-as-currency.md)            | Formats a number as currency as specified by locale.             |
| **Transformations**                                                    |                                                                  |
| [Changing Case](wrangler-docs/directives/changing-case.md)                      | Changes the case of column values                                |
| [Cut Character](wrangler-docs/directives/cut-character.md)                      | Selects parts of a string value                                  |
| [Set Column](wrangler-docs/directives/set-column.md)                            | Sets the column value to the result of an expression execution   |
| [Find and Replace](wrangler-docs/directives/find-and-replace.md)                | Transforms string column values using a "sed"-like expression    |
| [Index Split](wrangler-docs/directives/index-split.md)                          | (_Deprecated_)                                                   |
| [Invoke HTTP](wrangler-docs/directives/invoke-http.md)                          | Invokes an HTTP Service (_Experimental_, potentially slow)       |
| [Quantization](wrangler-docs/directives/quantize.md)                            | Quantizes a column based on specified ranges                     |
| [Regex Group Extractor](wrangler-docs/directives/extract-regex-groups.md)       | Extracts the data from a regex group into its own column         |
| [Setting Character Set](wrangler-docs/directives/set-charset.md)                | Sets the encoding and then converts the data to a UTF-8 String   |
| [Setting Record Delimiter](wrangler-docs/directives/set-record-delim.md)        | Sets the record delimiter                                        |
| [Split by Separator](wrangler-docs/directives/split-by-separator.md)            | Splits a column based on a separator into two columns            |
| [Split Email Address](wrangler-docs/directives/split-email.md)                  | Splits an email ID into an account and its domain                |
| [Split URL](wrangler-docs/directives/split-url.md)                              | Splits a URL into its constituents                               |
| [Text Distance (Fuzzy String Match)](wrangler-docs/directives/text-distance.md) | Measures the difference between two sequences of characters      |
| [Text Metric (Fuzzy String Match)](wrangler-docs/directives/text-metric.md)     | Measures the difference between two sequences of characters      |
| [URL Decode](wrangler-docs/directives/url-decode.md)                            | Decodes from the `application/x-www-form-urlencoded` MIME format |
| [URL Encode](wrangler-docs/directives/url-encode.md)                            | Encodes to the `application/x-www-form-urlencoded` MIME format   |
| [Trim](wrangler-docs/directives/trim.md)                                        | Functions for trimming white spaces around string data           |
| **Encoders and Decoders**                                              |                                                                  |
| [Decode](wrangler-docs/directives/decode.md)                                    | Decodes a column value as one of `base32`, `base64`, or `hex`    |
| [Encode](wrangler-docs/directives/encode.md)                                    | Encodes a column value as one of `base32`, `base64`, or `hex`    |
| **Unique ID**                                                          |                                                                  |
| [UUID Generation](wrangler-docs/directives/generate-uuid.md)                    | Generates a universally unique identifier (UUID) .Recommended to use with Wrangler version 4.4.0 and above due to an important bug fix [CDAP-17732](https://cdap.atlassian.net/browse/CDAP-17732)             |
| **Date Transformations**                                               |                                                                  |
| [Diff Date](wrangler-docs/directives/diff-date.md)                              | Calculates the difference between two dates                      |
| [Format Date](wrangler-docs/directives/format-date.md)                          | Custom patterns for date-time formatting                         |
| [Format Unix Timestamp](wrangler-docs/directives/format-unix-timestamp.md)      | Formats a UNIX timestamp as a date                               |
| **DateTime Transformations**                                                    |                                                                  |
| [Current DateTime](wrangler-docs/directives/current-datetime.md)                | Generates the current datetime using the given zone or UTC by default|
| [Datetime To Timestamp](wrangler-docs/directives/datetime-to-timestamp.md)      | Converts a datetime value to timestamp with the given zone       |
| [Format Datetime](wrangler-docs/directives/format-datetime.md)                  | Formats a datetime value to custom date time pattern strings     |
| [Timestamp To Datetime](wrangler-docs/directives/timestamp-to-datetime.md)      | Converts a timestamp value to datetime                           |
| **Lookups**                                                            |                                                                  |
| [Catalog Lookup](wrangler-docs/directives/catalog-lookup.md)                    | Static catalog lookup of ICD-9, ICD-10-2016, ICD-10-2017 codes   |
| [Table Lookup](wrangler-docs/directives/table-lookup.md)                        | Performs lookups into Table datasets                             |
| **Hashing & Masking**                                                  |                                                                  |
| [Message Digest or Hash](wrangler-docs/directives/hash.md)                      | Generates a message digest                                       |
| [Mask Number](wrangler-docs/directives/mask-number.md)                          | Applies substitution masking on the column values                |
| [Mask Shuffle](wrangler-docs/directives/mask-shuffle.md)                        | Applies shuffle masking on the column values                     |
| **Row Operations**                                                     |                                                                  |
| [Filter Row if Matched](wrangler-docs/directives/filter-row-if-matched.md)      | Filters rows that match a pattern for a column                                         |
| [Filter Row if True](wrangler-docs/directives/filter-row-if-true.md)            | Filters rows if the condition is true.                                                  |
| [Filter Row Empty of Null](wrangler-docs/directives/filter-empty-or-null.md)    | Filters rows that are empty of null.                    |
| [Flatten](wrangler-docs/directives/flatten.md)                                  | Separates the elements in a repeated field                       |
| [Fail on condition](wrangler-docs/directives/fail.md)                           | Fails processing when the condition is evaluated to true.        |
| [Send to Error](wrangler-docs/directives/send-to-error.md)                      | Filtering of records to an error collector                       |
| [Send to Error And Continue](wrangler-docs/directives/send-to-error-and-continue.md) | Filtering of records to an error collector and continues processing                      |
| [Split to Rows](wrangler-docs/directives/split-to-rows.md)                      | Splits based on a separator into multiple records                |
| **Column Operations**                                                  |                                                                  |
| [Change Column Case](wrangler-docs/directives/change-column-case.md)            | Changes column names to either lowercase or uppercase            |
| [Changing Case](wrangler-docs/directives/changing-case.md)                      | Change the case of column values                                 |
| [Cleanse Column Names](wrangler-docs/directives/cleanse-column-names.md)        | Sanatizes column names, following specific rules                 |
| [Columns Replace](wrangler-docs/directives/columns-replace.md)                  | Alters column names in bulk                                      |
| [Copy](wrangler-docs/directives/copy.md)                                        | Copies values from a source column into a destination column     |
| [Drop Column](wrangler-docs/directives/drop.md)                                 | Drops a column in a record                                       |
| [Fill Null or Empty Columns](wrangler-docs/directives/fill-null-or-empty.md)    | Fills column value with a fixed value if null or empty           |
| [Keep Columns](wrangler-docs/directives/keep.md)                                | Keeps specified columns from the record                          |
| [Merge Columns](wrangler-docs/directives/merge.md)                              | Merges two columns by inserting a third column                   |
| [Rename Column](wrangler-docs/directives/rename.md)                             | Renames an existing column in the record                         |
| [Set Column Header](wrangler-docs/directives/set-headers.md)                     | Sets the names of columns, in the order they are specified       |
| [Split to Columns](wrangler-docs/directives/split-to-columns.md)                | Splits a column based on a separator into multiple columns       |
| [Swap Columns](wrangler-docs/directives/swap.md)                                | Swaps column names of two columns                                |
| [Set Column Data Type](wrangler-docs/directives/set-type.md)                    | Convert data type of a column                                    |
| **NLP**                                                                |                                                                  |
| [Stemming Tokenized Words](wrangler-docs/directives/stemming.md)                | Applies the Porter stemmer algorithm for English words           |
| **Transient Aggregators & Setters**                                    |                                                                  |
| [Increment Variable](wrangler-docs/directives/increment-variable.md)            | Increments a transient variable with a record of processing.     |
| [Set Variable](wrangler-docs/directives/set-variable.md)                        | Sets a transient variable with a record of processing.     |
| **Functions**                                                          |                                                                  |
| [Data Quality](wrangler-docs/functions/dq-functions.md)                         | Data quality check functions. Checks for date, time, etc.        |
| [Date Manipulations](wrangler-docs/functions/date-functions.md)                 | Functions that can manipulate date                               |
| [DDL](wrangler-docs/functions/ddl-functions.md)                                 | Functions that can manipulate definition of data                 |
| [JSON](wrangler-docs/functions/json-functions.md)                               | Functions that can be useful in transforming your data           |
| [Types](wrangler-docs/functions/type-functions.md)                              | Functions for detecting the type of data                         |

## Performance

Initial performance tests show that with a set of directives of high complexity for
transforming data, *DataPrep* is able to process at about ~106K records per second. The
rates below are specified as *records/second*. 

| Directive Complexity | Column Count |    Records |           Size | Mean Rate |
| -------------------- | :----------: | ---------: | -------------: | --------: |
| High (167 Directives) |      426      | 127,946,398 |  82,677,845,324 | 106,367.27 |
| High (167 Directives) |      426      | 511,785,592 | 330,711,381,296 | 105,768.93 |


## Contact

### Mailing Lists

CDAP User Group and Development Discussions:

* [cdap-user@googlegroups.com](https://groups.google.com/d/forum/cdap-user)

The *cdap-user* mailing list is primarily for users using the product to develop
applications or building plugins for appplications. You can expect questions from
users, release announcements, and any other discussions that we think will be helpful
to the users.

### IRC Channel

CDAP IRC Channel: [#cdap on irc.freenode.net](http://webchat.freenode.net?channels=%23cdap)

### Slack Team

CDAP Users on Slack: [cdap-users team](https://cdap-users.herokuapp.com)


## License and Trademarks

Copyright © 2016-2019 Cask Data, Inc.

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except
in compliance with the License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the
License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND,
either express or implied. See the License for the specific language governing permissions
and limitations under the License.

Cask is a trademark of Cask Data, Inc. All rights reserved.

Apache, Apache HBase, and HBase are trademarks of The Apache Software Foundation. Used with
permission. No endorsement by The Apache Software Foundation is implied by the use of these marks.





PS E:\zeotap\wrangler-enhanced> mvn clean install "-DskipTests=true"
[INFO] Scanning for projects...
[INFO] ------------------------------------------------------------------------
[INFO] Reactor Build Order:
[INFO]
[INFO] Wrangler                                                           [pom]
[INFO] Wrangler API                                                       [jar]
[INFO] Wrangler REST Protocol Classes                                     [jar]
[INFO] Wrangler Core                                                      [jar]
[INFO] Wrangler Storage                                                   [jar]
[INFO] Wrangler Service                                                   [jar]
[INFO] Wrangler Testing Framework                                         [jar]
[INFO] Wrangler Transform                                                 [jar]
[INFO]
[INFO] ---------------------< io.cdap.wrangler:wrangler >----------------------
[INFO] Building Wrangler 4.12.0-SNAPSHOT                                  [1/8]
[INFO]   from pom.xml
[INFO] --------------------------------[ pom ]---------------------------------
[INFO]
[INFO] --- clean:3.2.0:clean (default-clean) @ wrangler ---
[INFO] Deleting E:\zeotap\wrangler-enhanced\target
[INFO]
[INFO] --- apache-rat:0.10:check (rat-check) @ wrangler ---
[INFO] 58 implicit excludes (use -debug for more details).
[INFO] Exclude: cov-int/**
[INFO] Exclude: *.md
[INFO] Exclude: */.md
[INFO] Exclude: */.json
[INFO] Exclude: */resources/*
[INFO] Exclude: wrangler-demos/**
[INFO] Exclude: */com/example/*
[INFO] Exclude: //icons/**
[INFO] 8 resources included (use -debug for more details)
[INFO] Rat check: Summary of files. Unapproved: 0 unknown: 0 generated: 0 approved: 6 licence.
[INFO]
[INFO] --- checkstyle:2.17:check (validate) @ wrangler ---
[WARNING]  Parameter 'sourceDirectory' is deprecated: instead use {@link #sourceDirectories}
[INFO] Starting audit...
Audit done.
[INFO]
[INFO] --- install:3.1.2:install (default-install) @ wrangler ---
[INFO] Installing E:\zeotap\wrangler-enhanced\pom.xml to C:\Users\DELL\.m2\repository\io\cdap\wrangler\wrangler\4.12.0-SNAPSHOT\wrangler-4.12.0-SNAPSHOT.pom
[INFO]
[INFO] -------------------< io.cdap.wrangler:wrangler-api >--------------------
[INFO] Building Wrangler API 4.12.0-SNAPSHOT                              [2/8]
[INFO]   from wrangler-api\pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
[INFO]
[INFO] --- clean:3.2.0:clean (default-clean) @ wrangler-api ---
[INFO] Deleting E:\zeotap\wrangler-enhanced\wrangler-api\target
[INFO]
[INFO] --- apache-rat:0.10:check (rat-check) @ wrangler-api ---
[INFO] 51 implicit excludes (use -debug for more details).
[INFO] Exclude: cov-int/**
[INFO] Exclude: *.md
[INFO] Exclude: */.md
[INFO] Exclude: */.json
[INFO] Exclude: */resources/*
[INFO] Exclude: wrangler-demos/**
[INFO] Exclude: */com/example/*
[INFO] Exclude: //icons/**
[INFO] 71 resources included (use -debug for more details)
[INFO] Rat check: Summary of files. Unapproved: 0 unknown: 0 generated: 0 approved: 71 licence.
[INFO]
[INFO] --- resources:3.3.1:resources (default-resources) @ wrangler-api ---
[INFO] skip non existing resourceDirectory E:\zeotap\wrangler-enhanced\wrangler-api\src\main\resources
[INFO]
[INFO] --- compiler:3.13.0:compile (default-compile) @ wrangler-api ---
[INFO] Recompiling the module because of changed source code.
[INFO] Compiling 69 source files with javac [debug target 1.8] to target\classes
[WARNING] bootstrap class path not set in conjunction with -source 8
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-api/src/main/java/io/cdap/wrangler/api/lineage/Mutation.java: E:\zeotap\wrangler-enhanced\wrangler-api\src\main\java\io\cdap\wrangler\api\lineage\Mutation.java uses or overrides a deprecated API.
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-api/src/main/java/io/cdap/wrangler/api/lineage/Mutation.java: Recompile with -Xlint:deprecation for details.
[INFO]
[INFO] --- resources:3.3.1:testResources (default-testResources) @ wrangler-api ---
[INFO] skip non existing resourceDirectory E:\zeotap\wrangler-enhanced\wrangler-api\src\test\resources
[INFO]
[INFO] --- compiler:3.13.0:testCompile (default-testCompile) @ wrangler-api ---
[INFO] Recompiling the module because of changed dependency.
[INFO] Compiling 1 source file with javac [debug target 1.8] to target\test-classes
[WARNING] bootstrap class path not set in conjunction with -source 8
[INFO]
[INFO] --- checkstyle:2.17:check (validate) @ wrangler-api ---
[WARNING]  Parameter 'sourceDirectory' is deprecated: instead use {@link #sourceDirectories}
[INFO] Starting audit...
Audit done.
[INFO]
[INFO] --- surefire:2.14.1:test (default-test) @ wrangler-api ---
[INFO] Tests are skipped.
[INFO]
[INFO] --- jar:3.4.1:jar (default-jar) @ wrangler-api ---
[INFO] Building jar: E:\zeotap\wrangler-enhanced\wrangler-api\target\wrangler-api-4.12.0-SNAPSHOT.jar
[INFO]
[INFO] --- install:3.1.2:install (default-install) @ wrangler-api ---
[INFO] Installing E:\zeotap\wrangler-enhanced\wrangler-api\pom.xml to C:\Users\DELL\.m2\repository\io\cdap\wrangler\wrangler-api\4.12.0-SNAPSHOT\wrangler-api-4.12.0-SNAPSHOT.pom
[INFO] Installing E:\zeotap\wrangler-enhanced\wrangler-api\target\wrangler-api-4.12.0-SNAPSHOT.jar to C:\Users\DELL\.m2\repository\io\cdap\wrangler\wrangler-api\4.12.0-SNAPSHOT\wrangler-api-4.12.0-SNAPSHOT.jar
[INFO]
[INFO] ------------------< io.cdap.wrangler:wrangler-proto >-------------------
[INFO] Building Wrangler REST Protocol Classes 4.12.0-SNAPSHOT            [3/8]
[INFO]   from wrangler-proto\pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
[INFO]
[INFO] --- clean:3.2.0:clean (default-clean) @ wrangler-proto ---
[INFO] Deleting E:\zeotap\wrangler-enhanced\wrangler-proto\target
[INFO]
[INFO] --- apache-rat:0.10:check (rat-check) @ wrangler-proto ---
[INFO] 51 implicit excludes (use -debug for more details).
[INFO] Exclude: cov-int/**
[INFO] Exclude: *.md
[INFO] Exclude: */.md
[INFO] Exclude: */.json
[INFO] Exclude: */resources/*
[INFO] Exclude: wrangler-demos/**
[INFO] Exclude: */com/example/*
[INFO] Exclude: //icons/**
[INFO] 81 resources included (use -debug for more details)
[INFO] Rat check: Summary of files. Unapproved: 0 unknown: 0 generated: 0 approved: 81 licence.
[INFO]
[INFO] --- resources:3.3.1:resources (default-resources) @ wrangler-proto ---
[INFO] skip non existing resourceDirectory E:\zeotap\wrangler-enhanced\wrangler-proto\src\main\resources
[INFO]
[INFO] --- compiler:3.13.0:compile (default-compile) @ wrangler-proto ---
[INFO] Recompiling the module because of changed dependency.
[INFO] Compiling 79 source files with javac [debug target 1.8] to target\classes
[WARNING] bootstrap class path not set in conjunction with -source 8
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-proto/src/main/java/io/cdap/wrangler/proto/connection/ConnectionMeta.java: E:\zeotap\wrangler-enhanced\wrangler-proto\src\main\java\io\cdap\wrangler\proto\connection\ConnectionMeta.java uses unchecked or unsafe operations.
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-proto/src/main/java/io/cdap/wrangler/proto/connection/ConnectionMeta.java: Recompile with -Xlint:unchecked for details.
[INFO]
[INFO] --- resources:3.3.1:testResources (default-testResources) @ wrangler-proto ---
[INFO] skip non existing resourceDirectory E:\zeotap\wrangler-enhanced\wrangler-proto\src\test\resources
[INFO]
[INFO] --- compiler:3.13.0:testCompile (default-testCompile) @ wrangler-proto ---
[INFO] Recompiling the module because of changed dependency.
[INFO] Compiling 1 source file with javac [debug target 1.8] to target\test-classes
[WARNING] bootstrap class path not set in conjunction with -source 8
[INFO]
[INFO] --- checkstyle:2.17:check (validate) @ wrangler-proto ---
[WARNING]  Parameter 'sourceDirectory' is deprecated: instead use {@link #sourceDirectories}
[INFO] Starting audit...
Audit done.
[INFO]
[INFO] --- surefire:2.14.1:test (default-test) @ wrangler-proto ---
[INFO] Tests are skipped.
[INFO]
[INFO] --- jar:3.4.1:jar (default-jar) @ wrangler-proto ---
[INFO] Building jar: E:\zeotap\wrangler-enhanced\wrangler-proto\target\wrangler-proto-4.12.0-SNAPSHOT.jar
[INFO]
[INFO] --- install:3.1.2:install (default-install) @ wrangler-proto ---
[INFO] Installing E:\zeotap\wrangler-enhanced\wrangler-proto\pom.xml to C:\Users\DELL\.m2\repository\io\cdap\wrangler\wrangler-proto\4.12.0-SNAPSHOT\wrangler-proto-4.12.0-SNAPSHOT.pom
[INFO] Installing E:\zeotap\wrangler-enhanced\wrangler-proto\target\wrangler-proto-4.12.0-SNAPSHOT.jar to C:\Users\DELL\.m2\repository\io\cdap\wrangler\wrangler-proto\4.12.0-SNAPSHOT\wrangler-proto-4.12.0-SNAPSHOT.jar
[INFO]
[INFO] -------------------< io.cdap.wrangler:wrangler-core >-------------------
[INFO] Building Wrangler Core 4.12.0-SNAPSHOT                             [4/8]
[INFO]   from wrangler-core\pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
[WARNING] 1 problem was encountered while building the effective model for org.apache.hadoop:hadoop-annotations:jar:2.6.5 during dependency collection step for project (use -X to see details)
[WARNING] 2 problems were encountered while building the effective model for org.apache.yetus:audience-annotations:jar:0.5.0 during dependency collection step for project (use -X to see details)
[WARNING] 1 problem was encountered while building the effective model for org.javassist:javassist:jar:3.18.2-GA during dependency collection step for project (use -X to see details)
[INFO]
[INFO] --- clean:3.2.0:clean (default-clean) @ wrangler-core ---
[INFO] Deleting E:\zeotap\wrangler-enhanced\wrangler-core\target
[INFO]
[INFO] --- apache-rat:0.10:check (rat-check) @ wrangler-core ---
[INFO] 51 implicit excludes (use -debug for more details).
[INFO] Exclude: cov-int/**
[INFO] Exclude: *.md
[INFO] Exclude: */.md
[INFO] Exclude: */.json
[INFO] Exclude: */resources/*
[INFO] Exclude: wrangler-demos/**
[INFO] Exclude: */com/example/*
[INFO] Exclude: //icons/**
[INFO] 304 resources included (use -debug for more details)
[INFO] Rat check: Summary of files. Unapproved: 0 unknown: 0 generated: 0 approved: 304 licence.
[INFO]
[INFO] --- antlr4:4.7:antlr4 (default) @ wrangler-core ---
[INFO] ANTLR 4: Processing source directory E:\zeotap\wrangler-enhanced\wrangler-core\src\main\antlr4
[INFO] Processing grammar: io\cdap\wrangler\parser\Directives.g4
[INFO]
[INFO] --- buildnumber:1.0:create (default) @ wrangler-core ---
[INFO] Storing buildNumber: 2025-04-12-20:31:10_DELL at timestamp: 1744470070091
[INFO] Executing: cmd.exe /X /C "git show"
[INFO] Working directory: E:\zeotap\wrangler-enhanced\wrangler-core
[INFO] Storing buildScmBranch: UNKNOWN
[INFO]
[INFO] --- resources:3.3.1:resources (default-resources) @ wrangler-core ---
[INFO] Copying 12 resources from src\main\resources to target\classes
[INFO] The encoding used to copy filtered properties files have not been set. This means that the same encoding will be used to copy filtered properties files as when copying other filtered resources. This might not be what you want! Run your build with --debug to see which files might be affected. Read more at https://maven.apache.org/plugins/maven-resources-plugin/examples/filtering-properties-files.html
[INFO]
[INFO] --- compiler:3.13.0:compile (default-compile) @ wrangler-core ---
[INFO] Recompiling the module because of changed dependency.
[INFO] Compiling 191 source files with javac [debug target 1.8] to target\classes
[WARNING] bootstrap class path not set in conjunction with -source 8
[WARNING] /E:/zeotap/wrangler-enhanced/wrangler-core/src/main/java/io/cdap/directives/column/CreateRecord.java:[100,82] non-varargs call of varargs method with inexact argument type for last parameter;
  cast to java.lang.Object for a varargs call
  cast to java.lang.Object[] for a non-varargs call and to suppress this warning
[WARNING] /E:/zeotap/wrangler-enhanced/wrangler-core/src/main/java/io/cdap/directives/row/Flatten.java:[169,98] non-varargs call of varargs method with inexact argument type for last parameter;
  cast to java.lang.Object for a varargs call
  cast to java.lang.Object[] for a non-varargs call and to suppress this warning
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-core/src/main/java/io/cdap/wrangler/parser/ConfigDirectiveContext.java: Some input files use or override a deprecated API.
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-core/src/main/java/io/cdap/wrangler/parser/ConfigDirectiveContext.java: Recompile with -Xlint:deprecation for details.
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-core/src/main/java/io/cdap/directives/aggregates/DefaultTransientStore.java: Some input files use unchecked or unsafe operations.
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-core/src/main/java/io/cdap/directives/aggregates/DefaultTransientStore.java: Recompile with -Xlint:unchecked for details.
[INFO]
[INFO] --- resources:3.3.1:testResources (default-testResources) @ wrangler-core ---
[INFO] Copying 5 resources from src\test\resources to target\test-classes
[INFO]
[INFO] --- compiler:3.13.0:testCompile (default-testCompile) @ wrangler-core ---
[INFO] Recompiling the module because of changed dependency.
[INFO] Compiling 118 source files with javac [debug target 1.8] to target\test-classes
[WARNING] bootstrap class path not set in conjunction with -source 8
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-core/src/test/java/io/cdap/wrangler/config/DirectiveConfigTest.java: Some input files use or override a deprecated API.
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-core/src/test/java/io/cdap/wrangler/config/DirectiveConfigTest.java: Recompile with -Xlint:deprecation for details.
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-core/src/test/java/io/cdap/directives/aggregates/SetTransientVariableTest.java: Some input files use unchecked or unsafe operations.
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-core/src/test/java/io/cdap/directives/aggregates/SetTransientVariableTest.java: Recompile with -Xlint:unchecked for details.
[INFO]
[INFO] --- checkstyle:2.17:check (validate) @ wrangler-core ---
[WARNING]  Parameter 'sourceDirectory' is deprecated: instead use {@link #sourceDirectories}
[INFO] Starting audit...
Audit done.
[INFO]
[INFO] --- surefire:2.14.1:test (default-test) @ wrangler-core ---
[INFO] Tests are skipped.
[INFO]
[INFO] --- jar:3.4.1:jar (default-jar) @ wrangler-core ---
[INFO] Building jar: E:\zeotap\wrangler-enhanced\wrangler-core\target\wrangler-core-4.12.0-SNAPSHOT.jar
[INFO]
[INFO] --- install:3.1.2:install (default-install) @ wrangler-core ---
[INFO] Installing E:\zeotap\wrangler-enhanced\wrangler-core\pom.xml to C:\Users\DELL\.m2\repository\io\cdap\wrangler\wrangler-core\4.12.0-SNAPSHOT\wrangler-core-4.12.0-SNAPSHOT.pom
[INFO] Installing E:\zeotap\wrangler-enhanced\wrangler-core\target\wrangler-core-4.12.0-SNAPSHOT.jar to C:\Users\DELL\.m2\repository\io\cdap\wrangler\wrangler-core\4.12.0-SNAPSHOT\wrangler-core-4.12.0-SNAPSHOT.jar
[INFO]
[INFO] -----------------< io.cdap.wrangler:wrangler-storage >------------------
[INFO] Building Wrangler Storage 4.12.0-SNAPSHOT                          [5/8]
[INFO]   from wrangler-storage\pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
[INFO]
[INFO] --- clean:3.2.0:clean (default-clean) @ wrangler-storage ---
[INFO] Deleting E:\zeotap\wrangler-enhanced\wrangler-storage\target
[INFO]
[INFO] --- apache-rat:0.10:check (rat-check) @ wrangler-storage ---
[INFO] 51 implicit excludes (use -debug for more details).
[INFO] Exclude: cov-int/**
[INFO] Exclude: *.md
[INFO] Exclude: */.md
[INFO] Exclude: */.json
[INFO] Exclude: */resources/*
[INFO] Exclude: wrangler-demos/**
[INFO] Exclude: */com/example/*
[INFO] Exclude: //icons/**
[INFO] 33 resources included (use -debug for more details)
[INFO] Rat check: Summary of files. Unapproved: 0 unknown: 0 generated: 0 approved: 33 licence.
[INFO]
[INFO] --- resources:3.3.1:resources (default-resources) @ wrangler-storage ---
[INFO] skip non existing resourceDirectory E:\zeotap\wrangler-enhanced\wrangler-storage\src\main\resources
[INFO]
[INFO] --- compiler:3.13.0:compile (default-compile) @ wrangler-storage ---
[INFO] Recompiling the module because of changed dependency.
[INFO] Compiling 25 source files with javac [debug target 1.8] to target\classes
[WARNING] bootstrap class path not set in conjunction with -source 8
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-storage/src/main/java/io/cdap/wrangler/dataset/workspace/ConfigStore.java: Some input files use or override a deprecated API.
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-storage/src/main/java/io/cdap/wrangler/dataset/workspace/ConfigStore.java: Recompile with -Xlint:deprecation for details.
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-storage/src/main/java/io/cdap/wrangler/store/workspace/WorkspaceStore.java: E:\zeotap\wrangler-enhanced\wrangler-storage\src\main\java\io\cdap\wrangler\store\workspace\WorkspaceStore.java uses unchecked or unsafe operations.
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-storage/src/main/java/io/cdap/wrangler/store/workspace/WorkspaceStore.java: Recompile with -Xlint:unchecked for details.
[INFO]
[INFO] --- resources:3.3.1:testResources (default-testResources) @ wrangler-storage ---
[INFO] skip non existing resourceDirectory E:\zeotap\wrangler-enhanced\wrangler-storage\src\test\resources
[INFO]
[INFO] --- compiler:3.13.0:testCompile (default-testCompile) @ wrangler-storage ---
[INFO] Recompiling the module because of changed dependency.
[INFO] Compiling 7 source files with javac [debug target 1.8] to target\test-classes
[WARNING] bootstrap class path not set in conjunction with -source 8
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-storage/src/test/java/io/cdap/wrangler/dataset/ConnectionStoreTest.java: Some input files use or override a deprecated API.
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-storage/src/test/java/io/cdap/wrangler/dataset/ConnectionStoreTest.java: Recompile with -Xlint:deprecation for details.
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-storage/src/test/java/io/cdap/wrangler/dataset/WorkspaceDatasetTest.java: E:\zeotap\wrangler-enhanced\wrangler-storage\src\test\java\io\cdap\wrangler\dataset\WorkspaceDatasetTest.java uses unchecked or unsafe operations.
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-storage/src/test/java/io/cdap/wrangler/dataset/WorkspaceDatasetTest.java: Recompile with -Xlint:unchecked for details.
[INFO]
[INFO] --- checkstyle:2.17:check (validate) @ wrangler-storage ---
[WARNING]  Parameter 'sourceDirectory' is deprecated: instead use {@link #sourceDirectories}
[INFO] Starting audit...
Audit done.
[INFO]
[INFO] --- surefire:2.14.1:test (default-test) @ wrangler-storage ---
[INFO] Tests are skipped.
[INFO]
[INFO] --- jar:3.4.1:jar (default-jar) @ wrangler-storage ---
[INFO] Building jar: E:\zeotap\wrangler-enhanced\wrangler-storage\target\wrangler-storage-4.12.0-SNAPSHOT.jar
[INFO]
[INFO] --- install:3.1.2:install (default-install) @ wrangler-storage ---
[INFO] Installing E:\zeotap\wrangler-enhanced\wrangler-storage\pom.xml to C:\Users\DELL\.m2\repository\io\cdap\wrangler\wrangler-storage\4.12.0-SNAPSHOT\wrangler-storage-4.12.0-SNAPSHOT.pom
[INFO] Installing E:\zeotap\wrangler-enhanced\wrangler-storage\target\wrangler-storage-4.12.0-SNAPSHOT.jar to C:\Users\DELL\.m2\repository\io\cdap\wrangler\wrangler-storage\4.12.0-SNAPSHOT\wrangler-storage-4.12.0-SNAPSHOT.jar
[INFO]
[INFO] -----------------< io.cdap.wrangler:wrangler-service >------------------
[INFO] Building Wrangler Service 4.12.0-SNAPSHOT                          [6/8]
[INFO]   from wrangler-service\pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
[INFO]
[INFO] --- clean:3.2.0:clean (default-clean) @ wrangler-service ---
[INFO] Deleting E:\zeotap\wrangler-enhanced\wrangler-service\target
[INFO]
[INFO] --- apache-rat:0.10:check (rat-check) @ wrangler-service ---
[INFO] 51 implicit excludes (use -debug for more details).
[INFO] Exclude: cov-int/**
[INFO] Exclude: *.md
[INFO] Exclude: */.md
[INFO] Exclude: */.json
[INFO] Exclude: */resources/*
[INFO] Exclude: wrangler-demos/**
[INFO] Exclude: */com/example/*
[INFO] Exclude: //icons/**
[INFO] 69 resources included (use -debug for more details)
[INFO] Rat check: Summary of files. Unapproved: 0 unknown: 0 generated: 0 approved: 69 licence.
[INFO]
[INFO] --- resources:3.3.1:resources (default-resources) @ wrangler-service ---
[INFO] Copying 2 resources from src\main\resources to target\classes
[INFO]
[INFO] --- compiler:3.13.0:compile (default-compile) @ wrangler-service ---
[INFO] Recompiling the module because of changed dependency.
[INFO] Compiling 52 source files with javac [debug target 1.8] to target\classes
[WARNING] bootstrap class path not set in conjunction with -source 8
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-service/src/main/java/io/cdap/wrangler/service/DataPrepService.java: Some input files use or override a deprecated API.
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-service/src/main/java/io/cdap/wrangler/service/DataPrepService.java: Recompile with -Xlint:deprecation for details.
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-service/src/main/java/io/cdap/wrangler/service/adls/ADLSHandler.java: Some input files use unchecked or unsafe operations.
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-service/src/main/java/io/cdap/wrangler/service/adls/ADLSHandler.java: Recompile with -Xlint:unchecked for details.
[INFO]
[INFO] --- resources:3.3.1:testResources (default-testResources) @ wrangler-service ---
[INFO] skip non existing resourceDirectory E:\zeotap\wrangler-enhanced\wrangler-service\src\test\resources
[INFO]
[INFO] --- compiler:3.13.0:testCompile (default-testCompile) @ wrangler-service ---
[INFO] Recompiling the module because of changed dependency.
[INFO] Compiling 16 source files with javac [debug target 1.8] to target\test-classes
[WARNING] bootstrap class path not set in conjunction with -source 8
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-service/src/test/java/io/cdap/wrangler/service/TableLookupTest.java: Some input files use or override a deprecated API.
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-service/src/test/java/io/cdap/wrangler/service/TableLookupTest.java: Recompile with -Xlint:deprecation for details.
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-service/src/test/java/io/cdap/wrangler/service/filesystem/TestApp.java: E:\zeotap\wrangler-enhanced\wrangler-service\src\test\java\io\cdap\wrangler\service\filesystem\TestApp.java uses unchecked or unsafe operations.
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-service/src/test/java/io/cdap/wrangler/service/filesystem/TestApp.java: Recompile with -Xlint:unchecked for details.
[INFO]
[INFO] --- checkstyle:2.17:check (validate) @ wrangler-service ---
[WARNING]  Parameter 'sourceDirectory' is deprecated: instead use {@link #sourceDirectories}
[INFO] Starting audit...
Audit done.
[INFO]
[INFO] --- surefire:2.14.1:test (default-test) @ wrangler-service ---
[INFO] Tests are skipped.
[INFO]
[INFO] --- jar:3.4.1:jar (default-jar) @ wrangler-service ---
[INFO] Building jar: E:\zeotap\wrangler-enhanced\wrangler-service\target\wrangler-service-4.12.0-SNAPSHOT.jar
[INFO]
[INFO] --- bundle:3.3.0:bundle (default) @ wrangler-service ---
[WARNING] Bundle io.cdap.wrangler:wrangler-service:jar:4.12.0-SNAPSHOT : Export io.cdap.wrangler.api,  has 4,  private references [io.cdap.cdap.api.data.schema, io.cdap.cdap.etl.api, com.google.gson, javax.annotation],
[WARNING] Bundle io.cdap.wrangler:wrangler-service:jar:4.12.0-SNAPSHOT : Export io.cdap.wrangler.api.parser,  has 1,  private references [com.google.gson],
[INFO]
[INFO] --- install:3.1.2:install (default-install) @ wrangler-service ---
[INFO] Installing E:\zeotap\wrangler-enhanced\wrangler-service\pom.xml to C:\Users\DELL\.m2\repository\io\cdap\wrangler\wrangler-service\4.12.0-SNAPSHOT\wrangler-service-4.12.0-SNAPSHOT.pom
[INFO] Installing E:\zeotap\wrangler-enhanced\wrangler-service\target\wrangler-service-4.12.0-SNAPSHOT.jar to C:\Users\DELL\.m2\repository\io\cdap\wrangler\wrangler-service\4.12.0-SNAPSHOT\wrangler-service-4.12.0-SNAPSHOT.jar
[INFO]
[INFO] -------------------< io.cdap.wrangler:wrangler-test >-------------------
[INFO] Building Wrangler Testing Framework 4.12.0-SNAPSHOT                [7/8]
[INFO]   from wrangler-test\pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
[INFO]
[INFO] --- clean:3.2.0:clean (default-clean) @ wrangler-test ---
[INFO] Deleting E:\zeotap\wrangler-enhanced\wrangler-test\target
[INFO]
[INFO] --- apache-rat:0.10:check (rat-check) @ wrangler-test ---
[INFO] 51 implicit excludes (use -debug for more details).
[INFO] Exclude: cov-int/**
[INFO] Exclude: *.md
[INFO] Exclude: */.md
[INFO] Exclude: */.json
[INFO] Exclude: */resources/*
[INFO] Exclude: wrangler-demos/**
[INFO] Exclude: */com/example/*
[INFO] Exclude: //icons/**
[INFO] 4 resources included (use -debug for more details)
[INFO] Rat check: Summary of files. Unapproved: 0 unknown: 0 generated: 0 approved: 4 licence.
[INFO]
[INFO] --- resources:3.3.1:resources (default-resources) @ wrangler-test ---
[INFO] skip non existing resourceDirectory E:\zeotap\wrangler-enhanced\wrangler-test\src\main\resources
[INFO]
[INFO] --- compiler:3.13.0:compile (default-compile) @ wrangler-test ---
[INFO] Recompiling the module because of changed dependency.
[INFO] Compiling 3 source files with javac [debug target 1.8] to target\classes
[WARNING] bootstrap class path not set in conjunction with -source 8
[INFO]
[INFO] --- resources:3.3.1:testResources (default-testResources) @ wrangler-test ---
[INFO] skip non existing resourceDirectory E:\zeotap\wrangler-enhanced\wrangler-test\src\test\resources
[INFO]
[INFO] --- compiler:3.13.0:testCompile (default-testCompile) @ wrangler-test ---
[INFO] No sources to compile
[INFO]
[INFO] --- checkstyle:2.17:check (validate) @ wrangler-test ---
[WARNING]  Parameter 'sourceDirectory' is deprecated: instead use {@link #sourceDirectories}
[INFO] Starting audit...
Audit done.
[INFO]
[INFO] --- surefire:2.14.1:test (default-test) @ wrangler-test ---
[INFO] Tests are skipped.
[INFO]
[INFO] --- jar:3.4.1:jar (default-jar) @ wrangler-test ---
[INFO] Building jar: E:\zeotap\wrangler-enhanced\wrangler-test\target\wrangler-test-4.12.0-SNAPSHOT.jar
[INFO]
[INFO] --- install:3.1.2:install (default-install) @ wrangler-test ---
[INFO] Installing E:\zeotap\wrangler-enhanced\wrangler-test\pom.xml to C:\Users\DELL\.m2\repository\io\cdap\wrangler\wrangler-test\4.12.0-SNAPSHOT\wrangler-test-4.12.0-SNAPSHOT.pom
[INFO] Installing E:\zeotap\wrangler-enhanced\wrangler-test\target\wrangler-test-4.12.0-SNAPSHOT.jar to C:\Users\DELL\.m2\repository\io\cdap\wrangler\wrangler-test\4.12.0-SNAPSHOT\wrangler-test-4.12.0-SNAPSHOT.jar
[INFO]
[INFO] ----------------< io.cdap.wrangler:wrangler-transform >-----------------
[INFO] Building Wrangler Transform 4.12.0-SNAPSHOT                        [8/8]
[INFO]   from wrangler-transform\pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
[INFO]
[INFO] --- clean:3.2.0:clean (default-clean) @ wrangler-transform ---
[INFO] Deleting E:\zeotap\wrangler-enhanced\wrangler-transform\target
[INFO]
[INFO] --- apache-rat:0.10:check (rat-check) @ wrangler-transform ---
[INFO] 51 implicit excludes (use -debug for more details).
[INFO] Exclude: cov-int/**
[INFO] Exclude: *.md
[INFO] Exclude: */.md
[INFO] Exclude: */.json
[INFO] Exclude: */resources/*
[INFO] Exclude: wrangler-demos/**
[INFO] Exclude: */com/example/*
[INFO] Exclude: //icons/**
[INFO] 36 resources included (use -debug for more details)
[INFO] Rat check: Summary of files. Unapproved: 0 unknown: 0 generated: 0 approved: 36 licence.
[INFO]
[INFO] --- resources:3.3.1:resources (default-resources) @ wrangler-transform ---
[INFO] skip non existing resourceDirectory E:\zeotap\wrangler-enhanced\wrangler-transform\src\main\resources
[INFO]
[INFO] --- compiler:3.13.0:compile (default-compile) @ wrangler-transform ---
[INFO] Recompiling the module because of changed dependency.
[INFO] Compiling 5 source files with javac [debug target 1.8] to target\classes
[WARNING] bootstrap class path not set in conjunction with -source 8
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-transform/src/main/java/io/cdap/wrangler/Wrangler.java: E:\zeotap\wrangler-enhanced\wrangler-transform\src\main\java\io\cdap\wrangler\Wrangler.java uses unchecked or unsafe operations.
[INFO] /E:/zeotap/wrangler-enhanced/wrangler-transform/src/main/java/io/cdap/wrangler/Wrangler.java: Recompile with -Xlint:unchecked for details.
[INFO]
[INFO] --- resources:3.3.1:testResources (default-testResources) @ wrangler-transform ---
[INFO] skip non existing resourceDirectory E:\zeotap\wrangler-enhanced\wrangler-transform\src\test\resources
[INFO]
[INFO] --- compiler:3.13.0:testCompile (default-testCompile) @ wrangler-transform ---
[INFO] Recompiling the module because of changed dependency.
[INFO] Compiling 1 source file with javac [debug target 1.8] to target\test-classes
[WARNING] bootstrap class path not set in conjunction with -source 8
[INFO]
[INFO] --- checkstyle:2.17:check (validate) @ wrangler-transform ---
[WARNING]  Parameter 'sourceDirectory' is deprecated: instead use {@link #sourceDirectories}
[INFO] Starting audit...
Audit done.
[INFO]
[INFO] --- surefire:2.14.1:test (default-test) @ wrangler-transform ---
[INFO] Tests are skipped.
[INFO]
[INFO] --- cdap:1.1.0:create-plugin-json (create-artifact-config) @ wrangler-transform ---
[INFO] ------------------------------------------------------------------------
[INFO] CDAP Plugin JSON
[INFO] ------------------------------------------------------------------------
[INFO] Project              : Wrangler Transform
[INFO] Group ID             : io.cdap.wrangler
[INFO] Artifact ID          : wrangler-transform
[INFO] Version              : 4.12.0-SNAPSHOT
[INFO] Base Directory       : E:\zeotap\wrangler-enhanced\wrangler-transform
[INFO] Build Directory      : E:\zeotap\wrangler-enhanced\wrangler-transform\target
[INFO] Widgets Directory    : widgets
[INFO] Icons Directory      : icons
[INFO] Docs Directory       : docs
[INFO] CDAP Artifacts
[INFO]  system:cdap-data-pipeline[6.11.0-SNAPSHOT,7.0.0-SNAPSHOT)
[INFO]  system:cdap-data-streams[6.11.0-SNAPSHOT,7.0.0-SNAPSHOT)
[INFO] ------------------------------------------------------------------------
[INFO] Successfully created  : wrangler-transform-4.12.0-SNAPSHOT.json
[INFO] ------------------------------------------------------------------------
[INFO]
[INFO] --- jar:3.4.1:jar (default-jar) @ wrangler-transform ---
[INFO] Building jar: E:\zeotap\wrangler-enhanced\wrangler-transform\target\wrangler-transform-4.12.0-SNAPSHOT.jar
[INFO]
[INFO] --- bundle:3.3.0:bundle (default) @ wrangler-transform ---
[WARNING] Bundle io.cdap.wrangler:wrangler-transform:jar:4.12.0-SNAPSHOT : Export io.cdap.wrangler.api,  has 1,  private references [javax.annotation],
[WARNING] Bundle io.cdap.wrangler:wrangler-transform:jar:4.12.0-SNAPSHOT : Export io.cdap.wrangler.codec,  has 4,  private references [org.apache.avro.io, org.apache.avro.generic, com.google.protobuf, org.apache.avro],
[WARNING] Bundle io.cdap.wrangler:wrangler-transform:jar:4.12.0-SNAPSHOT : Export io.cdap.wrangler.datamodel,  has 2,  private references [org.apache.commons.collections4, org.apache.avro],
[WARNING] Bundle io.cdap.wrangler:wrangler-transform:jar:4.12.0-SNAPSHOT : Export io.cdap.wrangler.dq,  has 1,  private references [javax.annotation],
[WARNING] Bundle io.cdap.wrangler:wrangler-transform:jar:4.12.0-SNAPSHOT : Export io.cdap.wrangler.executor,  has 2,  private references [javax.annotation, io.cdap.directives.lookup],
[WARNING] Bundle io.cdap.wrangler:wrangler-transform:jar:4.12.0-SNAPSHOT : Export io.cdap.wrangler.expression,  has 1,  private references [org.apache.commons.jexl3],
[WARNING] Bundle io.cdap.wrangler:wrangler-transform:jar:4.12.0-SNAPSHOT : Export io.cdap.wrangler.metrics,  has 1,  private references [javax.annotation],
[WARNING] Bundle io.cdap.wrangler:wrangler-transform:jar:4.12.0-SNAPSHOT : Export io.cdap.wrangler.parser,  has 5,  private references [org.antlr.v4.runtime.dfa, org.antlr.v4.runtime, javax.annotation, org.antlr.v4.runtime.tree, org.antlr.v4.runtime.atn],
[WARNING] Bundle io.cdap.wrangler:wrangler-transform:jar:4.12.0-SNAPSHOT : Export io.cdap.wrangler.proto,  has 1,  private references [io.cdap.cdap.api],
[WARNING] Bundle io.cdap.wrangler:wrangler-transform:jar:4.12.0-SNAPSHOT : Export io.cdap.wrangler.proto.connection,  has 1,  private references [javax.annotation],
[WARNING] Bundle io.cdap.wrangler:wrangler-transform:jar:4.12.0-SNAPSHOT : Export io.cdap.wrangler.proto.gcs,  has 1,  private references [javax.annotation],
[WARNING] Bundle io.cdap.wrangler:wrangler-transform:jar:4.12.0-SNAPSHOT : Export io.cdap.wrangler.proto.recipe.v2,  has 1,  private references [io.cdap.cdap.api],
[WARNING] Bundle io.cdap.wrangler:wrangler-transform:jar:4.12.0-SNAPSHOT : Export io.cdap.wrangler.proto.schema,  has 1,  private references [javax.annotation],
[WARNING] Bundle io.cdap.wrangler:wrangler-transform:jar:4.12.0-SNAPSHOT : Export io.cdap.wrangler.proto.workspace,  has 1,  private references [javax.annotation],
[WARNING] Bundle io.cdap.wrangler:wrangler-transform:jar:4.12.0-SNAPSHOT : Export io.cdap.wrangler.proto.workspace.v2,  has 2,  private references [javax.annotation, io.cdap.cdap.api],
[WARNING] Bundle io.cdap.wrangler:wrangler-transform:jar:4.12.0-SNAPSHOT : Export io.cdap.wrangler.registry,  has 3,  private references [io.cdap.cdap.api.service.http, io.cdap.cdap.api.service.worker, javax.annotation],
[WARNING] Bundle io.cdap.wrangler:wrangler-transform:jar:4.12.0-SNAPSHOT : Export io.cdap.wrangler.utils,  has 3,  private references [org.apache.avro, javax.annotation, org.apache.commons.collections4],
[INFO]
[INFO] --- install:3.1.2:install (default-install) @ wrangler-transform ---
[INFO] Installing E:\zeotap\wrangler-enhanced\wrangler-transform\pom.xml to C:\Users\DELL\.m2\repository\io\cdap\wrangler\wrangler-transform\4.12.0-SNAPSHOT\wrangler-transform-4.12.0-SNAPSHOT.pom
[INFO] Installing E:\zeotap\wrangler-enhanced\wrangler-transform\target\wrangler-transform-4.12.0-SNAPSHOT.jar to C:\Users\DELL\.m2\repository\io\cdap\wrangler\wrangler-transform\4.12.0-SNAPSHOT\wrangler-transform-4.12.0-SNAPSHOT.jar
[INFO] ------------------------------------------------------------------------
[INFO] Reactor Summary for Wrangler 4.12.0-SNAPSHOT:
[INFO]
[INFO] Wrangler ........................................... SUCCESS [  6.358 s]
[INFO] Wrangler API ....................................... SUCCESS [  8.694 s]
[INFO] Wrangler REST Protocol Classes ..................... SUCCESS [  3.335 s]
[INFO] Wrangler Core ...................................... SUCCESS [ 47.040 s]
[INFO] Wrangler Storage ................................... SUCCESS [ 12.428 s]
[INFO] Wrangler Service ................................... SUCCESS [01:25 min]
[INFO] Wrangler Testing Framework ......................... SUCCESS [  3.020 s]
[INFO] Wrangler Transform ................................. SUCCESS [ 48.591 s]
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  03:36 min
[INFO] Finished at: 2025-04-12T20:34:11+05:30
[INFO] ------------------------------------------------------------------------
PS E:\zeotap\wrangler-enhanced>
