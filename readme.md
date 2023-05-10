```mermaid
classDiagram
 
 class Creator{
 +CreateProduct()
 }
 Creator ..> Product : implements
 class Product{
  +doStuff()
 }
 <<interface>> Product
```
