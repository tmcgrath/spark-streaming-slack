# Apache Spark Streaming from Slack

This assumes at least some previous experience with Apache Spark, but let me know if you have any questions.

## Requirements
1) Get a Slack API key

You need an OAuth token for API access to Slack and to run this Spark Streaming example.  

To get a token, go to https://api.slack.com/docs/oauth-test-tokens

If you don't have a "Create token" button option, just create a new Slack team, you'll have the option to create one.


2) Have a Spark Cluster Running and no your spark master URL

## Steps to run
To run in a Spark cluster example:
1) `sbt assembly` (and note the jar file produced because it's needed in next step)

Update the following according to your Spark master and your slack key

3) `spark-submit --conf spark.driver.userClassPathFirst=true --class com.supergloo.SlackStreamingApp --master spark://MASTER:7077 ./target/scala-2.11/spark-streaming-example-assembly-1.0.jar local[5] YOUR_SLACK_KEY`


For example:

`spark-submit  --conf spark.driver.userClassPathFirst=true --class com.supergloo.SlackStreamingApp --master spark://tmcgrath-rmbp15.local:7077 ./target/scala-2.10/spark-streaming-example-assembly-1.0.jar local[5] xoxp-28540311056-28536367895-285541`
