# Monitoring Summary

## Resource Monitored

```text
AWS Lambda function
```

## Metrics Used

```text
Invocations
Duration
Errors
Throttles
```

## Alarm Name

```text
lambda-error-alarm
```

## Alarm Condition

```text
Trigger alarm when Lambda Errors are greater than or equal to 1 within 1 minute.
```

## Notification Method

```text
Amazon SNS email notification
```

## Demo Checklist

- CloudWatch dashboard created
- Lambda metrics widgets added
- CloudWatch alarm created
- SNS topic created
- Email subscription confirmed
- Alarm tested using temporary Lambda error
- Lambda code restored after testing
