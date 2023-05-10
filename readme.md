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
  ConcreteProductA : +doSTuff()
  ConcreteProductB : +doSTuff()
  IProduct : <<interface>>

```
