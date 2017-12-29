# offset-management

- ### How to run
    - IntelliJ
        - Run the Object `org.izharahmed.consumer.Consumer` with `chunkSize` parameter set in program arguments
    - SBT
        - `cd /path/of/project`
        - Create fat jar `sbt clean compile assembly`
        - Submit Job `spark-submit --class org.izharahmed.consumer.Consumer /path/of/assembly/jar -chunkSize <some int>`

- ### Class Details
    - **ZookeeperHandler** - Manages zookeeper connection and offset set/get logic
    - **Producer** - Reads the input source and produces data from provided offset
    - **Consumer** - Consumes the data generated by the `Producer` and performs transformation. For testing purpose it also writes the transformation result as csv files.

- ### Logging
    - Important events during the execution will be logged under the logger named `OffsetManagement`