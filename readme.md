```mermaid
---
title: Factory Pattern
---
classDiagram
 
 class Creator{
 +CreateProduct() Product
 }
 
  class Product{
  +doStuff()
 }
 <<interface>> Product
 
 Creator --> Product : use
 
 class ConcreteProductA 
 class ConcreteProductB 
 
 ConcreteProductA ..|> Product : impelement
 ConcreteProductB ..|> Product : impelement
 
 class ConcreteCreatorA{
 +CreateProduct()
 }
 
  class ConcreteCreatorB{
 +CreateProduct()
 }
 
 note for ConcreteCreatorA "return new ConcreteProductA()"
 ConcreteCreatorA --|> Creator :instance of
 ConcreteCreatorB --|> Creator :instance of

 
```
