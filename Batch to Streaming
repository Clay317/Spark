// create batch load using spark.read
val staticDataFrame = spark.read.format("csv")  
.option("header", "true")  
.option("inferSchema", "true")  
.load("<path to folder>*.csv")

staticDataFrame.createOrReplaceTempView("team_batting")
val staticSchema = staticDataFrame.schema

// adjust batch code to use streaming using spark.readStream
val streamingDataFrame = spark.readStream    
.schema(staticSchema)     
.format("csv")    
.option("header", "true")    
.load("<path to folder>*.csv")

// test if streaming, should return true
streamingDataFrame.isStreaming 



