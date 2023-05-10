```mermaid
classDiagram
  Creator <|-- ConcreteCreatorA
  Creator <|-- ConcreteCreatorB
  Creator : +createProduct():IProduct
  Creator --> IProduct
  ConcreteCreatorA : +factoryMethod():IProduct
  ConcreteCreatorB : +factoryMethod():IProduct
  Creator : <<interface>>
  IProduct <|-- ConcreteProduct
  IProduct : +doSTuff()
  ConcreteProducA : +doSTuff()
  ConcreteProducB : +doSTuff()
  IProduct : <<interface>>

```
