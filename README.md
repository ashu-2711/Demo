version: 0.1
resource_usage:
  aws_lambda_function.hello_world:
    monthly_requests: 100000000
    request_duration_ms: 250  # Try changing this to 100 (milliseconds) to compare costs
