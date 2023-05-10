```mermaid
classDiagram
  Creator <|-- ConcreteCreatorA
  Creator <|-- ConcreteCreatorB
  Creator : +createProduct():IProduct
  Creator --> Product
  ConcreteCreatorA : +factoryMethod():IProduct
  ConcreteCreatoB : +factoryMethod():IProduct
  Creator : <<interface>>
  IProduct <|-- ConcreteProduct
  IProduct : +doSTuff()
  ConcreteProducA : +doSTuff()
  ConcreteProducB : +doSTuff()
  IProduct : <<interface>>

```
