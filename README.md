## SchoolDbTasarimi
### Okul Bilgileri içeren Database Projesindeki SQL Tasarımı
Okul bünyesinde bulunan öğrenci, veli, öğretmen, okul yönetimi, sınıflar, sınavlar gibi başlıklarla detaylı verileri içeren bir tasarım olmuştur. Aşağıda diagramını paylaştığım projenin detaylarını part part açıklayacağım.


![SchoolDb](https://github.com/arifozanaktas/SchoolDb/assets/139919845/19a9ee96-6682-4849-8ac0-68028c1b55ea)

---

---

*Students table ında öğrencilere ait temel veriler yer almaktadır.
```tSQL
CREATE TABLE [dbo].[Students](
	[Id] [int] IDENTITY(1,1) NOT NULL,
	[Name] [varchar](50) NOT NULL,
	[IsActive] [bit] NOT NULL,
	[Class] [int] NOT NULL,
	[BirthdayDate] [datetime] NOT NULL,
	[Gender] [bit] NOT NULL,
	[PhoneNumber] [varchar](13) NULL,
	[StartingDate] [datetime] NOT NULL,
	[EndingDate] [datetime] NULL,
	[ParentId] [int] NOT NULL,
	[Parent2Id] [int] NULL,
	[HobbiesId] [int] NOT NULL,
	[CreatedDate] [datetime] NOT NULL,
	[UpdatedDate] [datetime] NULL,
```
![Students](https://github.com/arifozanaktas/SchoolDb/assets/139919845/1880649f-8399-4e38-90f8-be844fa6c684)

---

*Teachers table ında öğretmenlere ait temel veriler yer almaktadır.
```tSQL
CREATE TABLE [dbo].[Teachers](
	[Id] [int] IDENTITY(1,1) NOT NULL,
	[Name] [varchar](50) NOT NULL,
	[LessonId] [int] NOT NULL,
	[StartingDate] [datetime] NOT NULL,
	[EndingDate] [datetime] NULL,
	[IsActive] [bit] NOT NULL,
	[Graduated] [varchar](50) NOT NULL,
	[ResponsibleManagerId] [int] NOT NULL,
	[CreatedDate] [datetime] NOT NULL,
	[UpdatedDate] [datetime] NULL,
```

![Teachers](https://github.com/arifozanaktas/SchoolDb/assets/139919845/9999b041-8646-42ca-b503-de753a918535)

---

*Lessons table ında derslere ait temel veriler yer almaktadır.
```tSQL
CREATE TABLE [dbo].[Lessons](
	[Id] [int] IDENTITY(1,1) NOT NULL,
	[Lessons] [varchar](50) NOT NULL,
	[CreatedDate] [datetime] NOT NULL,
	[UpdatedDate] [datetime] NULL,
```

![Lessons](https://github.com/arifozanaktas/SchoolDb/assets/139919845/c8f26798-439f-4ebf-af22-36fc01926cc0)

