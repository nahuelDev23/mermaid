## El patorn factory aplicado a golang

No es asi nomas mira!

```mermaid
---
title: Factory Pattern
---
classDiagram

 note for Creator "var some Product = CreatePoduct()\n some.doStuff()"
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

## Patron Factory para subir imagenes con imageUploader.go


```mermaid
---
title: Simple Factory Pattern
---
classDiagram

 note for ImageUploaderFactory "uploaderImageService, error := uploaderImage.CreateImageUploaderFactory(uploaderImage.CLOUDINARY)"
  note for ImageUploaderFactory "return new Cloudinary()"
 class ImageUploaderFactory{
 +CreateImageUploaderFactory(provider AllowedImageProvider) (ImageUploader, customError.CustomError)
 }
 
  class ImageUploader{
  +UploadImage()
  +DeleteImage()
 }
 <<interface>> ImageUploader
 
 ImageUploaderFactory --> ImageUploader : use
 
 class Cloudinary{
 +UploadImage()
  +DeleteImage()
 }  
 
 Cloudinary ..|> ImageUploader : impelement
 ```
