
---
# Podstawy baz danych

grupa: 13

dzień i godz zajęć: środa 13:15

nr zespołu: 5

**Autorzy:** Karolina Nitsch, Witold Nieć

https://github.com/kanitsch/bazy_danych


--- 

# 1.	Wymagania i funkcje systemu
Projektowany system bazodanowy ma posłużyć firmie  oferującej różnego rodzaju kursy i szkolenia w modelu hybrydowym. Usługi dzielą się na: 
- Webinary
- Kursy
- Studia
- Pojedyncze spotkania studyjne
  
Składają się z następujących jednostek szkoleniowych:
  - spotkania online asynchroniczne (kursy, studia) 
  - spotkania online synchroniczne  (webinary, kursy, studia)
  - spotkania stacjonarne (kursy, studia)
  - praktyki (studia)
  - egzaminy (studia)
  
W systemie wyróżniamy następujące role:
- Użytkownik niezalogowany
- Klient 
- Nauczyciel
- Administrator
- Dyrektor
- Księgowy
  
Użytkownicy mogą korzystać z różnych funkcji, w zależności od ich ról w systemie. Role mogą być dziedziczone.

## Funkcje


### Funkcje systemu
- Zarządzanie dostepami do obszarów funkcjonalnych w oparciu o role w systemie
- Przyznawanie i odbieranie dostępu do jednostek szkoleniowych na podstawie wykupionych usług i terminów ważności. 

- Zarzadzanie dostępnością usług na podstawie limitów miejsc
- Zarządzanie zaliczeniami jednostek szkoleniowych i produktów według zasad:
    - Studia - 80% frekwencji
    - Praktyki - 100% frekwencji
    - Kursy - zaliczenie 80% modułów
- Rejestrowanie i odnotowywanie obecności wszystkich uczestników spotkań online (z podziałem na role)
- Generowanie linków do płatności
- Rejestrownie płatności
 
### Użytkownik niezalogowany
- Przegladanie, wyszukiwanie dostępnych produktów (z informacją o ich termianch, dostepnosci cenach): 
  - Webinarów, 
  - Kursów (wraz z programem), 
  - Studiów (wraz sylabusem) 
  - Zajeć studyjnych - dostępnych bez konieczności uczestnictwa w całych studiach
- Dostęp do ogólnych informacji na temat zasad funkcjonowania szkoły, regulaminów, formularzy komunikacyjnych
  
### Klient (użytkownik zalogowany)

Dziedziczy funkcje Użytkownika niezalogowanego.

#### Ogólne 
- możliwość zgłaszania problemów technicznych do administratora

#### Zakupy i zarządzanie dostępnymi szkoleniami
- Wyświetlanie liczby zapisanych osób, dostepnych tłumaczeniach i limicie miejsc dla danego produktu
- Dokonywanie zapisów poprzez koszyk zakupowy
- Generowanie żądania linków do płatności 
  - płatność pełna za webinar - link ważny do momentu rozpoczecia webinaru
  - płatność pełna za zajecia studyjne - link ważny do 3 dni przed rozpoczeciem kursu
  - płatość pełna za kurs - link ważny do 3 dni przed rozpoczeciem kursu
  - płatność wpisowego za studia - link ważny w dniu zapisu
  - płatność za zjazd w ramach studiów - link ważny do 3 dni przed rozpoczeciem zjazdu
  - dla każdej płatnosci istnieje możliwość zawnioskowania o płatność odroczona (wymaga akceptacji Dyrektora)
- Integracja z operatorem płatności
<!-- - Rejestrownie płatności za produkty -->

- Wyświetlanie aktualnej listy zamówionych usług szkoleniowych

- Sprawdzanie kolizji


#### Webinary
- Wyswietlenie dostępnych webinarów z informacją o terminach
- Odtwarzanie darmowych webinarów 
- Odtwarzanie płatnych webinarów z wykupionym dostępem i w terminie dostępności

#### Kursy
- Wyświetlenie wykupionych kursów ze statusem zaawansowania
- Wyświetlenie zawartości kursów z informacją o terminach 
- Uruchamianie spotkan online asynchronicznych
- Dołączanie do spotkań online synchronicznych
- Sprawdzanie statusu obecności/zaliczenia 
- Oglądanie nagrań ze spotkań online


#### Studia
- Wyświetlenie wykupionych studiów ze statusem zaawansowania
- Wyświetlenie sylabusu studiów z informacją o terminach
- Uruchamianie spotkań online asynchronicznych
- Dołączanie do spotkań online synchronicznych
- Sprawdzanie statusu obecności/zaliczenia
- Oglądanie nagrań ze spotkań online
- Odrabianie nieobecności

  


### Nauczyciel

#### Ogólne

- Wyświetlanie kalendarza/planu zajęć
- Dołączanie do spotkań online (z odpowiednimi uprawnieniami zarządzania spotkaniem)

#### Spotkania online asynchroniczne 
- Nagrywanie spotkania i udostepnianie nagrań
<!-- - Rejestracja obecności -automatyczna -->


#### Spotkania online synchroniczne
- Nagrywanie spotkania i udostepnianie nagrań
<!-- - Rejestracja obecności -automatyczna -->



#### Spotkania stacjonarne, Praktyki
- Rejestracja obecności uczestników


### Administrator

- Wyświetlanie listy zgłoszonych problemów i możliwość odpowiadania klientom
- Dostęp do szczegółowych informacji o wszystkich użytkownikach systemu
- Dodawanie, usuwanie, modyfikowanie jednostek szkoleniowych i form kształcenia
- Dodawanie i usuwanie użytkowników (Nauczyciel, Dyrektor, Księgowy)
- Zarządzanie rolami
- "awaryjne" zarzadzanie uprawnieniami i kontami Klientów
  
### Księgowy
- Raporty finansowe – zestawienie przychodów dla każdego webinaru/kursu/studium. 
- Raport Lista „dłużników” – osoby, które skorzystały z usług, ale nie uiściły opłat. 

### Dyrektor

  Dziedziczy funkcje księgowego. Ponadto posiada dostęp do następujących funkcji:

- zarządzanie zgodami na płatność odroczoną
- zarządznie dyplomami - wydruki oraz rejestracja wydania dyplomu
- Ogólny raport dotyczący liczby zapisanych osób na przyszłe wydarzenia (z informacją, czy wydarzenie jest stacjonarnie, czy zdalnie). 
- Ogólny raport dotyczący frekwencji na zakończonych już wydarzeniach. 
- Lista obecności dla każdego szkolenia z datą, imieniem, nazwiskiem i informacją czy uczestnik był obecny, czy nie. 
- Raport bilokacji: lista osób, które są zapisane na co najmniej dwa przyszłe szkolenia, które ze sobą kolidują czasowo. 
- Dostęp do informacji o świadczonych usługach
- Dostęp do szczegółowych informacji o wszystkich użytkownikach systemu

# 2.	Baza danych

## Schemat bazy danych

![Alt text](baza.svg)

## Opis poszczególnych tabel


**1. Users**
W tabeli users znajują się informacje o wszystkich użytkownikach systemu.
Pola:
- UserID (PK) - unikalne ID użytkownika systemu
- LastName - Nazwisko użytkownika
- FirstName - Imię użytkownika
- Email - email, używany do logowania do systemu
- Address - adres użytkownika
- Password - hasło, używane do logowania do systemu
``` SQL
CREATE TABLE Users (
    UserID int IDENTITY(1,1)  NOT NULL,
    LastName nvarchar(20)  NOT NULL,
    FirstName nvarchar(20)  NOT NULL,
    Email nvarchar(40)  NOT NULL UNIQUE,
    Address nvarchar(100)  NULL,
    Password nvarchar(20) CHECK (LEN(Password) BETWEEN 8 AND 20)  NOT NULL,
    CONSTRAINT Users_pk PRIMARY KEY  (UserID)
);
```
**2. Roles**
Tablica Roles zawiera informacje o rolach w systemie
Pola:
- RoleID (PK) - ID unikalne dla każdej roli 
- RoleName - nazwa roli w postaci napisu
``` SQL
CREATE TABLE Roles (
    RoleID int IDENTITY(1,1)  NOT NULL,
    RoleName nvarchar(20)  NOT NULL,
    CONSTRAINT Roles_pk PRIMARY KEY  (RoleID)
);
```
**3. UserToRole**
Tabela UserToRole pełnii funkcje tabeli pośredniej, łączącej tabele Users i Roles. Dzięki tej tabeli realizujemy relację wiele do wiele tzn. jeden użytkownik może mieć wiele ról i wielu użytkowników może mieć tą samą rolę. 
Pola:
- UserID (FK) - ID użytkownika
- RoleID (FK) - ID roli
- StartDate - data rozpoczęcia pełnienia danej roli
- EndDate - data zakończenia pełnienia danej roli

``` SQL
CREATE TABLE UserToRole (
    UserID int  NOT NULL,
    RoleID int  NOT NULL,
    StartDate date  NOT NULL DEFAULT cast(getdate() as date),
    EndDate date  NULL,
    CONSTRAINT UserToRole_pk PRIMARY KEY  (UserID,RoleID)
);

ALTER TABLE UserToRole ADD CONSTRAINT User_To_Role_Role
    FOREIGN KEY (RoleID)
    REFERENCES Roles (RoleID);

ALTER TABLE UserToRole ADD CONSTRAINT User_To_Role_User
    FOREIGN KEY (UserID)
    REFERENCES Users (UserID);
```

**4. Subscriptions**
Zawiera informacje o wykupionych dostępach do produktów. 
Pola:
- SubID (PK) - unikalne ID danej subskrypcji
- UserID (FK) - ID użytkownika
- ProductID (FK) - ID produktu
- AccessAllowed - czy użytkownik posiada dostęp do spotkań w ramach subskrypcji (przykładowo, jeżeli użytkownik nie zapłacił za zjazd i nie ma zgody na płatność odroczoną, to nie ma dostępu do spotkań w ramach tego zjazdu, pomimo że subskrypcja istnieje od czasu wpłaty zaliczki za studia)
- StartDate - data przyznania dostępu do produktu
- EndDate - data zabrania dostępu do produktu
- IsPassed - stan zaliczenia danego produktu (jeżeli nie dotyczny null)
- PaymentDate - Informacja do kiedy użytkownik musi zapłacić. Dyrektor może przedłużyć datę w ramach zgody na płatność odroczoną.
- RecivedDiploma - stan odebrania dyplomu

<!-- 5. Products
Zawiera informacje o produktach oferowanych przez firmę. Produkty to webinary, studia, kursy, moduły, spotkania studyjne, praktyki.
Pola:
 -->
``` SQL
CREATE TABLE Subscriptions (
    SubID int IDENTITY(1,1)  NOT NULL,
    UserID int  NOT NULL,
    ProductID int  NOT NULL,
    AccessAllowed bit  NOT NULL,
    StartDate datetime  NOT NULL DEFAULT getdate(),
    EndDate datetime  NULL,
    IsPassed bit  NOT NULL DEFAULT 0,
    PaymentDeadline datetime  NULL,
    ReceivedDiploma bit  NOT NULL DEFAULT 0,
    CONSTRAINT Subscriptions_pk PRIMARY KEY  (SubID)
);

ALTER TABLE Subscriptions ADD CONSTRAINT Participants_Products
    FOREIGN KEY (ProductID)
    REFERENCES Products (ProductID);

ALTER TABLE Subscriptions ADD CONSTRAINT Participants_Users
    FOREIGN KEY (UserID)
    REFERENCES Users (UserID);

```


**5. Products**

Zawiera informacje o produktach oferowanych przez firmę. Produkty mogą obejmować webinary, studia, kursy, semestry, zjazdy i spotkania studyjne. Struktura jest hierarchiczna - np. semestry są podproduktami studiów, a zjazdy podproduktami semestrów. Spotkania w tabelach Meetings i MeetingsAssingments należą do produktów znajdujących się najniżej w hierarchii.
Pola:

- ProductID (PK) - unikalne ID produktu.
- ProductTypeID - ID typu produktu. Szczegółowe informacje w tabeli ProductTypes.
- ProductName - nazwa produktu.
- Description - szczegółowy opis produktu.
- FullPrice - pełna cena produktu.
- EntryFee - opłata wstępna (jeśli obowiązuje).
- MaxSeats - maksymalna liczba miejsc dostępnych dla danego produktu.
- IsActive - informacja, czy produkt jest aktywny (bit).
- SuperID (FK) - ID nadrzędnego produktu (np. zjazd jest częścią studiów).
  
``` SQL
CREATE TABLE Products (
    ProductID int IDENTITY(1,1)  NOT NULL,
    ProductTypeID int  NOT NULL,
    ProductName nvarchar(40)  NOT NULL,
    Description text  NULL,
    FullPrice money  NULL,
    EntryFee money  NULL,
    MaxSeats int  NULL,
    IsActive bit  NOT NULL,
    SuperID int  NULL,
    CONSTRAINT Products_pk PRIMARY KEY  (ProductID)
);

ALTER TABLE Products ADD CONSTRAINT Products_ProductTypes
    FOREIGN KEY (ProductTypeID)
    REFERENCES ProductTypes (ProductTypeID);

ALTER TABLE Products ADD CONSTRAINT Products_Products
    FOREIGN KEY (SuperID)
    REFERENCES Products (ProductID);
```

**6. Product Types**
Zawiera szczegółowe informacje o poszczególnych typach produktów (webinary, studia, kursy, zjazdy, spotkania studyjne, egzaminy i praktyki). 
Pola:
- ProductTypeID (PK) - unikalne ID typu
- ProductTypeName - nazwa typu produktu (np. webinar, studia, itd.)
- EndsWithDiploma - informacja czy dany typ produktu kończy się uzyskaniem dyplomu
- IsForSale - informacja czy dany typ można kupić/zasubskrybować (np. dla webinarów płatnych i darmowych IsForSale będzie oznaczone jako True, ale nie można zapisać się na pojedynczy semestr na studia - wtedy IsForSale jest False)  

```SQL
CREATE TABLE ProductTypes (
    ProductTypeID int  NOT NULL,
    ProductTypeName nvarchar(40)  NOT NULL,
    EndsWithDiploma bit  NOT NULL,
    IsForSale bit  NOT NULL,
    CONSTRAINT ProductTypes_pk PRIMARY KEY  (ProductTypeID)
);
```

**7. Basket**
Zawiera produkty znajdujące się w koszykach poszczególnych klientów. wraz z informacją czy klient chce zapłacić pełną cenę czy tylko zaliczkę (jeżeli dotyczy).
Pola:
- UserID - ID użytkownika
- ProductID - ID Produktu
- OnlyAdvance - Informacja czy klient chce zapłacić pełną kwotę za produkt czy tylko zaliczkę (jeżeli dotyczy). Wartość domyślna wynosi 0. Klient może zmienić na 1 tylko dla produktów, które mają możliwość wpłaty zaliczki.

```SQL
CREATE TABLE Basket (
    UserID int  NOT NULL,
    ProductID int  NOT NULL,
    OnlyAdvance bit  NOT NULL DEFAULT 0,
    CONSTRAINT Basket_pk PRIMARY KEY  (UserID,ProductID)
);

ALTER TABLE Basket ADD CONSTRAINT Basket_Products
    FOREIGN KEY (ProductID)
    REFERENCES Products (ProductID);

ALTER TABLE Basket ADD CONSTRAINT Basket_Users
    FOREIGN KEY (UserID)
    REFERENCES Users (UserID);
```
**8. Payments**

Zawiera dane dotyczące płatności realizowanych w systemie.
Pola:

- PaymentID (PK) - unikalne ID płatności.
- IsPaid - informacja o statusie płatności - czy zapłacono
- Link - odnośnik do potwierdzenia płatności (np. URL faktury).
``` SQL
CREATE TABLE Payments (
    PaymentID int IDENTITY(1,1)  NOT NULL,
    IsPaid bit  NOT NULL,
    Link nvarchar(64)  NOT NULL,
    CONSTRAINT Payments_pk PRIMARY KEY  (PaymentID)
);
```

**9. PaymentDetails**

Łączy płatności z subskrypcjami, przechowując szczegóły dotyczące wartości płatności.
Pola:

- PaymentID (FK) - ID płatności.
- SubID (FK) - ID subskrypcji, której dotyczy płatność.
- Value - kwota płatności.
``` SQL
CREATE TABLE PaymentDetails (
    PaymentID int  NOT NULL,
    SubID int  NOT NULL,
    Value money  NOT NULL,
    CONSTRAINT PaymentDetails_pk PRIMARY KEY  (PaymentID,SubID)
);

ALTER TABLE PaymentDetails ADD CONSTRAINT Payment_Recon_Payments
    FOREIGN KEY (PaymentID)
    REFERENCES Payments (PaymentID);

ALTER TABLE PaymentDetails ADD CONSTRAINT Payment_Recon_Subscriptions
    FOREIGN KEY (SubID)
    REFERENCES Subscriptions (SubID);

```

**10. Meetings**

Zawiera informacje o spotkaniach (np. wykładach, zajęciach, egzaminach).
Pola:

- MeetingID (PK) - unikalne ID spotkania.
- StartDate - data rozpoczęcia spotkania.
- EndDate - data zakończenia spotkania.
- ComponentID (FK) - ID komponentu edukacyjnego, do którego należy spotkanie.
- Location - miejsce, w którym odbywa się spotkanie. Może to być adres lub link do platformy chmurowej w przypadku spotkań online.
- MeetingType - typ spotkania (np. online, stacjonarne).
- LinkToVideo - odnośnik do nagrania spotkania (jeśli istnieje).
- TeacherID (FK) - ID nauczyciela prowadzącego spotkanie.
- LanguageID (FK) - język, w jakim odbywa się spotkanie.
- MaxSeats - maksymalna liczba uczestników.
``` SQL
CREATE TABLE Meetings (
    MeetingID int  NOT NULL,
    StartDate datetime  NOT NULL,
    EndDate datetime  NOT NULL,
    ComponentID int NULL,
    MeetingType nvarchar(60)  NOT NULL 
        CHECK (MeetingType in ('Egzamin', 'Spotkanie online asynchroniczne', 'Spotkanie online synchroniczne','Praktyka','Spotkanie stacjonarne')),
    Location nvarchar(100)  NULL,
    TeacherID int  NOT NULL,
    LinkToVideo nvarchar(100)  NULL,
    LanguageID int  NOT NULL,
    MaxSeats int  NULL,
    CONSTRAINT Meetings_pk PRIMARY KEY  (MeetingID)
);

ALTER TABLE Meetings ADD CONSTRAINT Meetings_Languages
    FOREIGN KEY (LanguageID)
    REFERENCES Languages (LanguageID);

ALTER TABLE Meetings ADD CONSTRAINT FK_Meetings_Products
    FOREIGN KEY (ProductID)
    REFERENCES Products (ProductID);

ALTER TABLE Meetings ADD CONSTRAINT Meetings_Teachers
    FOREIGN KEY (TeacherID)
    REFERENCES Users (UserID);

ALTER TABLE Meetings ADD CONSTRAINT Meetings_edu_units
    FOREIGN KEY (ComponentID)
    REFERENCES EduComponents (ComponentID);
```

**11. Attendance**

Zawiera informacje o obecności użytkowników na spotkaniach.
Pola:

- MeetingID (FK) - ID spotkania.
- SubID (FK) - ID subskrypcji użytkownika.
- Presence - informacja o obecności użytkownika na spotkaniu (bit).
- Grade - ocena uzyskana na spotkaniu. Dotyczy egzaminów - oprócz 100% frekwencji trzeba uzyskać ocenę pozytywną.
``` SQL
CREATE TABLE Attendance (
    MeetingID int  NOT NULL,
    Presence bit  NOT NULL,
    SubID int  NOT NULL,
    Grade decimal(2,1)  NULL CHECK (Grade in (2.0,3.0,3.5,4.0,4.5,5.0)),
    CONSTRAINT Attendance_pk PRIMARY KEY  (MeetingID,SubID)
);

ALTER TABLE Attendance ADD CONSTRAINT Presence_Meetings
    FOREIGN KEY (MeetingID)
    REFERENCES Meetings (MeetingID);

ALTER TABLE Attendance ADD CONSTRAINT Presence_Subscriptions
    FOREIGN KEY (SubID)
    REFERENCES Subscriptions (SubID);
```

**12. EduComponents**

Zawiera dane o komponentach edukacyjnych, które są częścią produktów. Przykładowo komponentem jest przedmiot na studiach, który należy do semestru i może pojawiać się na wielu zjazdach, lub moduł, który należy do kursu. Komponentami mogą być również egzaminy i praktyki. Komponenty grupują spotkania tematycznie i dodatkowo mają osobne zasady zaliczenia na podstawie obecności. Są potrzebne do wyświetlania sylabusa.

Pola:

- ComponentID (PK) - unikalne ID komponentu edukacyjnego.
- ProductID (FK) - ID produktu, do którego należy komponent
- Name - nazwa komponentu edukacyjnego.
- Description - szczegółowy opis komponentu.
- FreqToPass - wymagane minimum zaliczeń (np. liczba spotkań do zaliczenia).
``` SQL
CREATE TABLE EduComponents (
    ComponentID int IDENTITY(1,1)  NOT NULL,
    ProductID int  NOT NULL,
    Name nvarchar(40)  NOT NULL,
    Description text  NULL,
    FreqToPass decimal(3,2)  NULL,
    CONSTRAINT EduComponents_pk PRIMARY KEY  (ComponentID)
);

ALTER TABLE EduComponents ADD CONSTRAINT EduComponents_Products
    FOREIGN KEY (ProductID)
    REFERENCES Products (ProductID);
```

**13. Languages**

Przechowuje listę dostępnych języków w systemie.
Pola:

- LanguageID (PK) - unikalne ID języka.
- LanguageName - nazwa języka (np. angielski, polski).
``` SQL
CREATE TABLE Languages (
    LanguageID int IDENTITY(1,1)  NOT NULL,
    LanguageName nvarchar(20)  NOT NULL,
    CONSTRAINT Languages_pk PRIMARY KEY  (LanguageID)
);
```

**14. Translations**

Przechowuje informacje o dostępnych tłumaczeniach dla spotkań.
Pola:

- MeetingID (FK) - ID spotkania.
- TranslatorID (FK) - ID tłumacza.
- TargetLanguageID (FK) - ID języka docelowego tłumaczenia.
``` SQL
CREATE TABLE Translations (
    MeetingID int  NOT NULL,
    TranslatorID int  NOT NULL,
    TargetLanguageID int  NOT NULL,
    CONSTRAINT Translations_pk PRIMARY KEY  (MeetingID,TranslatorID)
);

ALTER TABLE Translations ADD CONSTRAINT Translations_Languages
    FOREIGN KEY (TargetLanguageID)
    REFERENCES Languages (LanguageID);

ALTER TABLE Translations ADD CONSTRAINT Translations_Meetings
    FOREIGN KEY (MeetingID)
    REFERENCES Meetings (MeetingID);

ALTER TABLE Translations ADD CONSTRAINT Translations_Users
    FOREIGN KEY (TranslatorID)
    REFERENCES Users (UserID);
```

## Widoki

**vProductFreeSeats** - pokazuje wszystkie produkty wraz z aktualną liczbą wolnych miejsc
``` SQL
SET ANSI_NULLS ON
GO

SET QUOTED_IDENTIFIER ON
GO

CREATE or alter VIEW [dbo].[vProductFreeSeats]
AS
SELECT    p.Description, p.EntryFee, p.FullPrice, p.ProductName, pt.ProductTypeName, dbo.freeseats(p.productid) 
FROM       Products p
         , ProductTypes pt
where p.ProductTypeID = pt.ProductTypeID
and p.IsActive = 1
GO
```
**vTeachers** - wypisuje wszystkich nauczycieli
``` SQL
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE or alter FUNCTION dbo.freeseats
(	
	@p_productid as int
)
RETURNS int 
AS
begin
	return (SELECT max(p.MaxSeats) -count(s.productid)  from Subscriptions s, Products p
	where s.ProductID = p.ProductID and
	s.ProductID = @p_productid)
end
```
**v_users_roles** - wypisuje użytkowników i ich role w systemie (id użytkownika, imię, nazwisko, rola)
```SQL
create view v_users_roles
as
select u.userid, FirstName, LastName, RoleName
from Users u join UserToRole utr
on utr.UserID=u.UserID
join Roles r
on r.RoleID=utr.RoleID
```

## Funkcje
**freeseats** - pokazuje liczbę wolnych miejsc dla produktu o podanym ID
``` SQL
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO

ALTER   FUNCTION [dbo].[freeseats]
(	
	@p_productid as int
)
RETURNS int 
AS
begin
	return (SELECT max(p.MaxSeats) -count(s.productid)  from Subscriptions s, Products p
	where s.ProductID = p.ProductID and
	s.ProductID = @p_productid)
end
```
**getProfits** - pokazuje zyski ze sprzedaży produktów dla podanego okresu
``` SQL
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO

ALTER   FUNCTION [dbo].[getProfits]
(
	@entryDate as date,
	@closeDate as date
)
RETURNS money
AS
BEGIN
	RETURN(select sum(p.value)
	from PaymentDetails p join Subscriptions s on p.SubID = s.SubID 
	where s.StartDate between @entryDate and @closeDate)

END

```
## Triggery

**validateMeetingProduct** - uniemożliwia wpisanie spotkania przypisanego do produktu, który nie należy do produktu z tabeli EduComponents dla danego ComponentID.
Przykładowo, można wpisać spotkanie w ramach kursu, tylko jeżeli komponent również należy do tego kursu.
W przypadku studiów produkt może być zjazdem, a komponent może należeć do semestru, w ramach którego odbywa się ten zjazd.
```SQL
ALTER TRIGGER [dbo].[validateMeetingProduct]
ON [dbo].[Meetings]
AFTER INSERT, UPDATE
AS
BEGIN
    IF EXISTS (
        SELECT 1
        FROM inserted i
		join Products p on p.ProductID=i.ProductID
		join EduComponents ec on ec.ComponentID=i.ComponentID
		where i.ComponentID is not null
		and (p.ProductID!=ec.ProductID and p.SuperID is not null and p.SuperID!=ec.ProductID)
		or (p.SuperID is null and p.ProductID!=ec.ProductID)
    )
    BEGIN
        RAISERROR ('ProductID w tabeli Meetings nie należy do ProductID z EduComponents dla danego ComponentID', 16, 1);
        ROLLBACK TRANSACTION;
    END
END;

```

**accesAllowed** - Po zmianie pola AccessAllowed na 1, tworzy rekordy w tabeli Attendance, aby umożliwić uczestnictwo i rejestrowanie obecności na spotkaniach w ramach danej subskrypcji. 
``` SQL
ALTER TRIGGER [dbo].[access_allowed] 
   ON  [dbo].[Subscriptions]
   AFTER  UPDATE 
AS 
IF ( UPDATE (Accessallowed) and (select accessallowed from inserted)=1 and (select accessallowed from deleted)=0 )  
BEGIN
	SET NOCOUNT ON
	insert into Attendance (MeetingId, SubID)
	(select m.MeetingID, SubID
	from Products p 
	join Meetings m
	on p.ProductID=m.ProductID
	join inserted i
	on i.ProductID=p.ProductID
	and not exists(select 1 from Attendance a where (a.SubID=i.SubID and a.MeetingID=m.MeetingID)) 
	) 
END

```

**checkPass** - po każdym wprowadzeniu obecności dla studiów sprawdzany jest stan zaliczenia
``` SQL
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
ALTER   TRIGGER [dbo].[Check_pass] 
   ON  [dbo].[Attendance]
   AFTER INSERT
AS 
BEGIN

begin
declare
@v_producttypename2   nvarchar(20)
	 select pt.producttypename
	  into v_producttypename2
	   from ProductTypes pt
		  , Products p
		  , Subscriptions s
		  , inserted i
	  where s.SubID = i.SubID
	    and s.ProductID = p.ProductID
		and p.ProductTypeID = pt.ProductTypeID
		--and pt.ProductTypeName = 'Studia'

		if @v_producttypename2 = 'Studia' 
		Begin
		declare
		@v_count int, 
		@v_attendancecount int
	
		 select count(1) as meetingscount 
		   into v_count
		   from Subscriptions s
			  , MeetingsAssignments ma
			  , Meetings m
			  , inserted i
		  where s.SubID = i.SubID
	        and s.ProductID = ma.ProductID
		    and ma.MeetingID = m.MeetingID;

		select count(1) as attendancecount
		  into v_attendancecount
		  from Subscriptions s
			  , MeetingsAssignments ma
			  , Meetings m
			  , inserted i
			  , Attendance a
		  where s.SubID = i.SubID
	        and s.ProductID = ma.ProductID
		    and ma.MeetingID = m.MeetingID
			and m.MeetingID = a.MeetingID
			and a.Presence = 1;

		if @v_attendancecount/@v_count >=0.7 
		begin 
		 update Subscriptions set IsPassed = 1
		 where SubID = (select SubID from inserted)
		end

	end 

end
END
```

**paymentcheck** - po opłaceniu zamówienia przyznawany jest dostęp do danej subskrybcji
``` SQL
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
ALTER   TRIGGER [dbo].[paymentcheck]
   ON  [dbo].[Payments]
   AFTER UPDATE
AS 
IF (UPDATE (IsPaid) and (select IsPaid from inserted)=1 and (select ispaid from deleted)=0)
BEGIN
	SET NOCOUNT ON
	update Subscriptions set AccessAllowed = 1
	where SubID = (select pd.SubID from 
	                  PaymentDetails pd, 
					  inserted i
					where i.PaymentID = pd.PaymentID)
					
	
	SET NOCOUNT ON;

END
```