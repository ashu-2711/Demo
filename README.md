# You can use this file to define resource usage estimates for Infracost to use when calculating
# the cost of usage-based resource, such as AWS S3 or Lambda.
# `infracost breakdown --usage-file infracost-usage.yml [other flags]`
# See https://infracost.io/usage-file/ for docs
version: 0.1
resource_usage:
  #
  # Terraform AWS resources
  #
  aws_acmpca_certificate_authority.my_private_ca:
    monthly_requests: 20000 # Monthly private certificate requests.

  aws_api_gateway_rest_api.my_rest_api:
    monthly_requests:  100000000 # Monthly requests to the Rest API Gateway.

  aws_apigatewayv2_api.my_v2_api:
    monthly_requests: 100000000       # Monthly requests to the HTTP API Gateway.
    request_size_kb: 512              # Average request size sent to the HTTP API Gateway in KB. Requests are metered in 512KB increments, maximum size is 10MB.
    monthly_messages: 1500000000      # Monthly number of messages sent to the Websocket API Gateway.
    message_size_kb: 32               # Average size of the messages sent to the Websocket API Gateway in KB. Messages are metered in 32 KB increments, maximum size is 128KB.
    monthly_connection_mins: 10000000 # Monthly total connection minutes to Websockets.

