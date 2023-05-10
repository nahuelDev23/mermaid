```mermaid
classDiagram
  Creator <|-- ConcreteCreator
  Creator : +factoryMethod()
  ConcreteCreator : +factoryMethod()
  Creator : <<interface>>
  Product <|-- ConcreteProduct
  Product : +operation()
  ConcreteProduct : +operation()
  Product : <<interface>>

```
