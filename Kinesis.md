# What
Kinesis is a platform for streaming data.

# Modules
1. Kinesis Data Streams
  * build application to process and analyze streaming data (real-time data process) (such as IT logs, location-tracking events, financial transactions...)
2. Kinesis Video Streams
  * build application to process and analyze streaming video (such as from smartphones, cameras, drones...)
3. Kinesis Data Firehose
  * deliver real-time data (such as application logs, website clickstreams, IoT telemetry data...) to S3, Redshift, Kinesis Analytics, Elasticsearch, database, datalake...
  * it's data sources, destinations and data transformation can be done with simple configuration
4. Kinesis Data Analytics
  * process and analyze streaming data with SQL

# Kinesis Video Streams
* Usage

  Use Producer API to sent data to a stream; API will sends stream of media fragments. Each fragment will be assigned a number, producer-side and server-side time stamps for each fragment also stroed.

  GetMedia API return fragment in order.  GetMediaFromFragmentList API used in batch processing applications.

![Diagram showing data flow for fragments and chucks during API calls](https://docs.aws.amazon.com/kinesisvideostreams/latest/dg/images/arch-20.png)

* Step to use

  Create a stream; Use api to send data to stream; 

# Kinesis Data Stream
Kinesis Data Streams ingests a large amount of data in real time, durably stores the data, and makes the data available for consumption. 

A Kinesis data stream is a set of shards. Each shard has a sequence of data records. Each data record has a sequence number that is assigned by Kinesis Data Streams. Data records are composed of a sequence number, a partition key, and a data blob. Shard capacity can be dynamically scaled. Each shard can support up to 5 transactions per second for reads, up to a maximum total data read rate of 2 MB per second and up to 1,000 records per second for writes, up to a maximum total data write rate of 1 MB per second (including partition keys).

Retention period is data store time in Kinesis Data Stream. (1 day <= retention <= 7 days)

  number_of_shards = max(incoming_write_bandwidth_in_KiB/1024, outgoing_read_bandwidth_in_KiB/2048)

![](https://docs.aws.amazon.com/streams/latest/dev/images/architecture.png)




# Data Firehose
  It's a fully managed service for delivering real-time streaming data.

  Data producer send record (data) to  and 
  Kinesis Data Firehose delivery stream received record which sent from data producer, and buffer it to a certain size or a certain period time then delivery it to destinations.

  Destination can be S3, Redshift, ES, Splunk. S3 always be used to store backup data for above application.

  ![](https://docs.aws.amazon.com/firehose/latest/dev/images/fh-flow-s3.png)
  ![](https://docs.aws.amazon.com/firehose/latest/dev/images/fh-flow-rs.png)
  ![](https://docs.aws.amazon.com/firehose/latest/dev/images/fh-flow-es.png)
  ![](https://docs.aws.amazon.com/firehose/latest/dev/images/fh-flow-splunk.png)

  Data source can be a producer application or a Kinesis stream. It can use Glue to covert the record format.

# Kinesis Data Analytics
With Amazon Kinesis Data Analytics for SQL Applications, you can process and analyze streaming data using standard SQL. 
Data sources can be Kinesis data stream, Kinesis Data Firehose delivery stream. Destination can be Amazon Kinesis Data Firehose (Amazon S3, Amazon Redshift, Amazon Elasticsearch Service, and Splunk), AWS Lambda, and Amazon Kinesis Data Streams as destinations. 

