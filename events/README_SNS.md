
# Sample Function

The following is a sample class and Lambda function that receives Amazon SNS event record data as input, writes some of the record data to CloudWatch Logs, and responds with a 200 status and the same body as the request. (Note that by default anything written to Console will be logged as CloudWatch Logs events.)

```go

import (
    "strings"
    "github.com/aws/aws-lambda-go/events")

func handler(ctx context.Context, events.SnsEvent snsEvent) {
    for _, record := range snsEvent.Records {
        snsRecord := record.Sns

        fmt.Printf("[%s %s] Message = %s \n", record.EventSource, snsRecord.Timestamp, snsRecord.Message) 
    }
}

```
