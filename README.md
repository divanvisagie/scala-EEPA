# scala-EEPA
Scala implementation of EEPA


![](https://rawgithub.com/divanvisagie/scala-EEPA/master/diagram/EEPA.svg)

## Publish Local

In `./eepa` run:

`sbt publish-local`

#### Running
Start by running the fibonacci service in `./fibonacci` using `./activator run`

To call the service you can either run the web server in `./example`  and call `localhost:9000` or simply run the tests for `./example`

Client
```scala
Client("fibonacci").client.call[MathAnswer](Fibonacci(n)).answer
```

Consumer:
```scala
Listener().listen[InDomainMessage]("fibonacci", inMessage => {
  val fibAnswer = recursiveMath.fibonacci(inMessage.number)
  OutDomainMessage(fibAnswer)
})
```
