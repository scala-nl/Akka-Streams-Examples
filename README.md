# Akka-Streams-Example
This is Proof-of-Concept project for Akka Streams. Akka Stream handle back-pressure which is one of the core featue offered by Akka-Streams. Back-pressure is the ability to slow down the producers if the consumers are slow and unable to consume at the rate at which the producers are producing. Akka Streams are high performance fully asynchronous highly efficient pipelines. The three main components of Streams are Source, Sink and Flow.

The Source class represents the origin of the data, from here the various events will flow downstream; the Flow gets data from upstream, possibly applies transformations and emits the result to the next stage; finally the Sink is the last part of the stream, the final destination of your data. This stages are characterized by the kind of ports they expose: Source has a single output port, Flow has input and output port and Sink has just the input port. For this reason, when you append a Flow to a Source, what you get in return is a new Source, and so on. You can compose as many stages as needed, given that you respect the kind of ports they expose (e.g. you can’t connect two Sources together).

Akka Streams implicitly implement pervasive flow control, all combinators respect back-pressure. The combinators signal all its upstream sources of data that it can only accept elements at a certain rate—when the incoming rate is higher than the threshold, the combinators assert back-pressure upstream. This is basically all there is to Akka Streams in a nutshell—glossing over the fact that there are dozens of sources and sinks and many more stream transformation combinators to choose from. [Read more!](http://doc.akka.io/docs/akka/2.4.12/scala/stream/stream-quickstart.html)

Akka Streams can be either linear stream structures or can be non-linear branching ones (Graphs). [Example-1](https://github.com/archit47/Akka-Streams-Examples/tree/master/Example-1) provides several linear stream structures.

I'll list out some resources and referrences on Akka Streams which I personally find useful, as and when I find them and shall append them here.

I found a nice blog explaining [Akka Streams](http://www.measurence.com/tech-blog/2016/06/01/a-dive-into-akka-streams.html) on Measurence. Do read it.
