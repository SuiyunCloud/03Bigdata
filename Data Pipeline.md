[AWS Data Pipeline](https://docs.aws.amazon.com/datapipeline/latest/DeveloperGuide/what-is-datapipeline.html)


# Usage
A pipeline definition used to define a pipeline to relize business logic. Components includes:

    * Data Nodes: name, location, format of your data; types: DynamoDBDataNode, SqlDataNode, RedshiftDataNode, S3DataNode
    * Activities: work that transform data; types: CopyActivity, EmrActivity, HiveActivity, HiveCopyActivity(support for S3DataNode, DynamoDBDataNode), PigActivity, RedshiftCopyActivity, ShellCommandActivity, SqlActivity
    * Scheduling Pipelines: schedule for activities
    * Resources: resources to run whole task; types: Ec2Resource, EmrCluster
    * Preconditions: must be satisfied before the activities can be scheduled
        # System-Managed Preconditions: DynamoDBDataExists, DynamoDBTableExists, S3KeyExists, S3PrefixNotEmpty
        # User-Managed Preconditions: Exists, ShellCommandPrecondition; They only run on computational resource
    * Actions: ways to alter you when there is something happen; types:SnsAlarm, Terminate

