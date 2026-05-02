Bronze bucket name-yt-data-pipeline-bronze-ap-south-dev
silver bucket name-yt-data-pipeline-silver-ap-south-dev
gold bucket name-yt-data-pipeline-gold-ap-south-dev
script bucket name-yt-data-pipeline-script-ap-south-dev
SNS ARN-arn:aws:sns:ap-south-1:346720668814:yt-data-pipeline-alearts-dev
arn:aws:sns:ap-south-1:346720668814:yt-data-pipeline-alearts-dev:ada177a1-8325-4743-b439-b5ad17972816
youtube api key -AIzaSyBWO9ML7YtUtcAwyNvXuI01FlvwbfZJIxE
glue db
bronze-yt-pipeline-bronze-dev-db
silver-yt-pipeline-silver-dev-db
gold-yt-pipeline-gold-dev-db

--bronze_database->bronze-yt-pipeline-bronze-dev-db
--bronze_table ->raw_statistics            
--silver_bucket->yt-data-pipeline-silver-ap-south-dev        
--silver_database ->yt-pipeline-silver-dev-db          
--silver_table ->clean_statistics 

--JOB_NAME  yt-data-pipeline-silver-to-gold-dev
--silver_database  yt-pipeline-silver-dev-db
--gold_bucket-yt-data-pipeline-gold-ap-south-dev       
--gold_database  -yt-pipeline-gold-dev-db  

for lambda function -yt-data-pipeline-data-quality-dev
env variable
Key
Value
ATHENA_OUTPUT
s3://yt-data-pipeline-glue-athena-query-result-bucket/output/
SNS_ALERT_TOPIC_ARN
arn:aws:sns:ap-south-1:346720668814:yt-data-pipeline-alearts-dev

for lambda function -yt-data-pipeline-json-to-parquet-dev
env variable
GLUE_DB_SILVER
yt-pipeline-silver-dev-db
S3_BUCKET_SILVER
yt-data-pipeline-silver-ap-south-dev
SNS_ALERT_TOPIC_ARN
arn:aws:sns:ap-south-1:346720668814:yt-data-pipeline-alearts-dev
for lambda function 
yt-data-pipeline-youtube-ingestion-dev

env variable


S3_BUCKET_BRONZE
yt-data-pipeline-bronze-ap-south-dev
SNS_ALERT_TOPIC_ARN
arn:aws:sns:ap-south-1:346720668814:yt-data-pipeline-alearts-dev
YOUTUBE_API_KEY
AIzaSyBWO9ML7YtUtcAwyNvXuI01FlvwbfZJIxE
YOUTUBE_REGIONS
US,GB,CA,DE,FR,IN,JP,KR,MX,RU

