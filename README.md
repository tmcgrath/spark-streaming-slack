# Apache Spark Streaming from Slack

## Requirements
1) Get a Slack API key

You need an OAuth token for API access to Slack and to run this Spark Streaming example.  

To get a token, go to https://api.slack.com/docs/oauth-test-tokens

If you don't have a "Create token" button option, just create a new Slack team, you'll have the option to create one. 

To run in a Spark cluster example:
1) sbt assembly (and note the jar file produced because it's needed in next step)
2) spark-submit --conf spark.driver.userClassPathFirst=true --class com.supergloo.SlackStreamingApp --master spark://MASTER:7077 ./target/scala-2.11/spark-streaming-example-assembly-1.0.jar local[5] YOUR_SLACK_KEY output
