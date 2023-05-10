```mermaid
classDiagram
  Creator <|-- ConcreteCreator
  Creator : +factoryMethod()
  Creator --> Product
  ConcreteCreator : +factoryMethod()
  Creator : <<interface>>
  Product <|-- ConcreteProduct
  Product : +operation()
  ConcreteProduct : +operation()
  Product : <<interface>>

```
