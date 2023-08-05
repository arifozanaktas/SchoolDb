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


---

*ExamPoints table ında sınavlara ait temel veriler yer almaktadır.
```tSQL
CREATE TABLE [dbo].[ExamPoints](
	[Id] [int] IDENTITY(1,1) NOT NULL,
	[StudentId] [int] NOT NULL,
	[LessonId] [int] NOT NULL,
	[FirstPoints] [decimal](4, 2) NULL,
	[SecondPoints] [decimal](4, 2) NULL,
	[IsAccomplished] [bit] NULL,
```
![Exams](https://github.com/arifozanaktas/SchoolDb/assets/139919845/73c72dea-219d-4ab1-b058-9795029f7c6a)

---

*Classes table ında sınıflara ait temel veriler yer almaktadır.
```tSQL
CREATE TABLE [dbo].[Classes](
	[Id] [int] IDENTITY(1,1) NOT NULL,
	[StudentId] [int] NOT NULL,
	[ClassName] [int] NOT NULL,
	[CreatedDate] [datetime] NOT NULL,
	[UpdatedDate] [datetime] NULL,
```
![Classes](https://github.com/arifozanaktas/SchoolDb/assets/139919845/cfd6443a-a7b3-4d42-8efb-ee41001ec386)

---

*Hobbies table ında hobi çeşitlerine ait temel veriler yer almaktadır.
```tSQL
CREATE TABLE [dbo].[Hobbies](
	[Id] [int] IDENTITY(1,1) NOT NULL,
	[TypesOfHobbies] [varchar](50) NOT NULL,
	[CreatedDate] [datetime] NOT NULL,
	[UpdatedDate] [datetime] NULL,
```
![hobb](https://github.com/arifozanaktas/SchoolDb/assets/139919845/20075be3-1b33-4bd5-b359-5ec96f585e8f)

---

*Managers table ında okul yöneticilerine ait temel veriler yer almaktadır.
```tSQL
CREATE TABLE [dbo].[Managers](
	[Id] [int] IDENTITY(1,1) NOT NULL,
	[Name] [varchar](50) NOT NULL,
	[Responsibility] [varchar](20) NOT NULL,
	[StartingDate] [datetime] NOT NULL,
	[EndingDate] [datetime] NULL,
	[IsActive] [bit] NOT NULL,
	[Graduated] [varchar](50) NOT NULL,
	[ResponsibileManagerId] [int] NULL,
	[CreatedDate] [datetime] NOT NULL,
	[UpdatedDate] [datetime] NULL,
```
![Managers](https://github.com/arifozanaktas/SchoolDb/assets/139919845/7431dc0d-f711-4182-b8ec-9e7a965c4589)

---

*Parents2Informations table ında 2. veli bilgilerine ait temel veriler yer almaktadır.
```tSQL
CREATE TABLE [dbo].[Parent2Informations](
	[Id] [int] IDENTITY(1,1) NOT NULL,
	[Name] [varchar](50) NOT NULL,
	[Address] [varchar](max) NOT NULL,
	[PhoneNumber] [varchar](13) NOT NULL,
	[Email] [varchar](max) NOT NULL,
	[CreatedDate] [datetime] NOT NULL,
	[UpdatedDate] [datetime] NULL,
```

![Parents](https://github.com/arifozanaktas/SchoolDb/assets/139919845/35849528-e185-47c3-9303-f0a3a1dfa85e)

---

*ParentsInformations table ında 1. veli bilgilerine ait temel veriler yer almaktadır.
```tSQL
CREATE TABLE [dbo].[ParentsInformations](
	[Id] [int] IDENTITY(1,1) NOT NULL,
	[Name] [varchar](50) NOT NULL,
	[Address] [varchar](max) NOT NULL,
	[PhoneNumber] [varchar](13) NOT NULL,
	[Email] [varchar](max) NOT NULL,
	[CreatedDate] [datetime] NOT NULL,
	[UpdatedDate] [datetime] NULL,
```
![Parents](https://github.com/arifozanaktas/SchoolDb/assets/139919845/06ee3307-dccc-4c0e-a267-1ef48b94aa46)

---

*StudentsAdditionalResponsibilities table ında öğrenci-hobi eşleştirme bilgilerine ait veriler yer almaktadır.
```tSQL
CREATE TABLE [dbo].[StudentsAdditionalResponsibilities](
	[Id] [int] IDENTITY(1,1) NOT NULL,
	[StudentsId] [int] NOT NULL,
	[Name] [varchar](50) NOT NULL,
	[TypeOfHobbiesId] [int] NOT NULL,
	[CreatedDate] [datetime] NOT NULL,
	[UpdatedDate] [datetime] NULL,
```

![StudentResponsibilty](https://github.com/arifozanaktas/SchoolDb/assets/139919845/9e647364-0d0c-4d2f-be9b-799bd8d7ad97)

---

*StudentsAdresses table ında öğrenci-adres eşleştirme bilgilerine ait veriler yer almaktadır.
```tSQL
CREATE TABLE [dbo].[StudentsAdresses](
	[Id] [int] IDENTITY(1,1) NOT NULL,
	[StudentsId] [int] NOT NULL,
	[Name] [varchar](50) NOT NULL,
	[Address] [varchar](max) NOT NULL,
	[CreatedDate] [datetime] NOT NULL,
	[UpdatedDate] [datetime] NULL,
```

![StudentAdresses](https://github.com/arifozanaktas/SchoolDb/assets/139919845/3e794267-bf3c-429f-b86f-bdf31732cc0f)

---

*StudentsPayments table ında öğrenci-adres eşleştirme bilgilerine ait veriler yer almaktadır.
```tSQL
CREATE TABLE [dbo].[StudentsPayments](
	[Id] [int] IDENTITY(1,1) NOT NULL,
	[StudentsId] [int] NOT NULL,
	[Name] [varchar](50) NOT NULL,
	[Price] [money] NOT NULL,
	[IsComplated] [bit] NOT NULL,
	[CreatedDate] [datetime] NOT NULL,
	[UpdatedDate] [datetime] NULL,
```


![StudentsPayment](https://github.com/arifozanaktas/SchoolDb/assets/139919845/af085029-a632-4c83-8f85-510dccc47c44)

