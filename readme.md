```mermaid
classDiagram
 
 class Creator{
 +CreateProduct()
 }
 
  class Product{
  +doStuff()
 }
 <<interface>> Product
 
 Creator --> Product : implements
 
 class ConcreteProductA {}
 class ConcreteProductB {}

 
```
