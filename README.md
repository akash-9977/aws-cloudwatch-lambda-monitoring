# AWS CloudWatch Lambda Monitoring

## Project Overview

This project demonstrates how to monitor an AWS Lambda function using **Amazon CloudWatch**.

The goal was to create a monitoring setup for a Lambda-based application, track important usage metrics, configure a CloudWatch alarm, and receive alert notifications using Amazon SNS.

## Services Used

- AWS CloudWatch
- AWS Lambda
- Amazon SNS
- AWS Console

## What I Configured

- Created a custom CloudWatch dashboard
- Added Lambda metric widgets to the dashboard
- Monitored Lambda usage and performance
- Created a CloudWatch alarm for Lambda errors
- Configured an SNS topic for alert notifications
- Added and confirmed an email subscription
- Tested the alarm by generating a temporary Lambda error

## Monitored Metrics

The dashboard was configured to monitor these Lambda metrics:

```text
Invocations
Duration
Errors
Throttles
```

## Dashboard Details

The CloudWatch dashboard provides a visual view of Lambda activity and performance.

It helps track:

- How many times the Lambda function is invoked
- How long the function takes to run
- Whether the function is producing errors
- Whether requests are being throttled

## Alarm Configuration

A CloudWatch alarm was created for the Lambda `Errors` metric.

Alarm rule:

```text
Metric: Errors
Statistic: Sum
Period: 1 minute
Condition: Errors >= 1
Action: Send notification using Amazon SNS
```

This means the alarm is triggered when the Lambda function records one or more errors within one minute.

## SNS Notification Setup

Amazon SNS was used to send email notifications when the CloudWatch alarm enters the alarm state.

Steps completed:

1. Created an SNS topic
2. Added an email subscription
3. Confirmed the subscription from email
4. Connected the SNS topic with the CloudWatch alarm

## Testing

To test the alarm, a temporary error was added to the Lambda function:

```python
raise Exception("Testing CloudWatch alarm")
```

After deploying and running the Lambda function, CloudWatch recorded the error and the alarm moved toward the alarm state.

After testing, the temporary error line was removed and the Lambda function was deployed again to restore normal behavior.

## Why Monitoring Is Important

Cloud monitoring helps detect problems early. Instead of manually checking every service, CloudWatch alarms can automatically notify users when a metric crosses a defined threshold.

This setup is useful for identifying:

- Lambda failures
- Performance issues
- Unexpected errors
- Throttling problems
- Application health changes

## What I Learned

- How to create a CloudWatch dashboard
- How to monitor AWS Lambda metrics
- How to configure CloudWatch alarms
- How to use Amazon SNS for email alerts
- How alert thresholds work
- Why observability is important in cloud applications

## Conclusion

This project helped me understand how AWS CloudWatch can be used to monitor cloud resources and configure alerts. It shows how dashboards, alarms, and SNS notifications work together to improve visibility and reliability in cloud applications.
