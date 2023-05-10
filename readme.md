```mermaid
classDiagram
  
  Creator : +createProduct():IProduct
  Creator --> IProduct
  Creator <|-- ConcreteCreatorA
  Creator <|-- ConcreteCreatorB
  
 

```
