# Kafka Go Test

This is a Kafka test written in Go. 

To run this test, you need to run the Kafka broker with Docker Compose:

`docker-compose up -d`

The `docker-compose` file will automatically create a topic named `orders`.

After that, you can run the producer by changing into the producer directory and running `go run main.go`. The consumer can be run in the same way, but use a separate terminal window.

To send a message, you have to send a POST request to the producer with the message in the body. The message will be sent to the Kafka topic and the consumer will receive it:

`curl -X POST http://localhost:8181/order -H "Content-Type: application/json" -d '{"customer_name": "Philipp", "product_type": "item"}'`.

You should now see the message in the consumer's output.
