```mermaid
classDiagram
 
 class Creator{
 +CreateProduct()
 }
 
  class Product{
  +doStuff()
 }
 
 Creator --> Product : implements
 

 <<interface>> Product
```
