## El patorn factory aplicado a golang


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
  +UploadImage(
  c *gin.Context,
  file *multipart.FileHeader,
  currentUserID string,
  currentURLImage string,
  customImage customImageService.CustomImage,
  folder string) (string, customError.CustomError)
  +DeleteImage(
  currentImageURL,
		currentUserID,
		folder string) (*uploader.DestroyResult, customError.CustomError)
 }
 <<interface>> ImageUploader
 
 ImageUploaderFactory --> ImageUploader : use
 
 class Cloudinary{
 +UploadImage()
  +DeleteImage()
 }  
 
 Cloudinary ..|> ImageUploader : impelement
 ```
 
 En el diagrama de arriba `ImageUploaderFactory` puede recibir como parametro un string de tipo `AllowedImageProvider`:
 ```go
 type AllowedImageProvider string
 var CLOUDINARY AllowedImageProvider = "cloudinary"
 ```
