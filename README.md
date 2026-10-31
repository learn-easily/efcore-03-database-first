# EF Core — Code First vs Database First · ლექცია 2 / 2

Database First პრაქტიკაში: მოკლე გახსენება, შემდეგ StoreDb (SQL სკრიპტი) → `Scaffold-DbContext` → გენერირებული Entity-ები და DbContext → გამოყენება → ბაზის ცვლილება, `-Force` და `partial` კლასები. პრაქტიკა: LibraryDb (ერთად), CinemaDb (დამოუკიდებლად). Console App, .NET 10, SQL Server. ანიმაციური HTML პრეზენტაცია + ლექტორის სცენარი.

| ფაილი | რა არის |
|---|---|
| `index.html` | პრეზენტაცია (32 სლაიდი) |
| `script.html` | ლექციის სცენარი — წასაკითხად / დასაბეჭდად |
| `sql/` | ბაზების სკრიპტები: `StoreDb` (დემო), `LibraryDb` (ერთად), `CinemaDb` (დამოუკიდებლად) + `*-change.sql` (DBA-ს ცვლილებები) |
| `deck/` | წყარო: სლაიდები და შენიშვნები (`df.html`), ძრავი (`engine.*`), ბილდი (`build_df.py`) |

## Scaffold-ის ბრძანება

```powershell
Scaffold-DbContext "Server=localhost;Database=LibraryDb;Trusted_Connection=True;TrustServerCertificate=True;" Microsoft.EntityFrameworkCore.SqlServer -OutputDir Models
```

ბაზის ცვლილების შემდეგ — იგივე ბრძანება + `-Force`. საკუთარი კოდი — `partial` კლასებში, ცალკე ფოლდერში, იგივე namespace-ით.

## გამოყენება

1. გახსენი `index.html` Chrome-ში ან Edge-ში, გადაიტანე პროექტორზე, დააჭირე `F`.
2. დააჭირე `Ctrl+Shift+P` — გაიხსნება **ლექტორის ფანჯარა** სცენარით.
3. ნავიგაცია **მხოლოდ ისრებით**: `→` შემდეგი, `←` წინა.

სხვა კლავიშები: `N` შენიშვნები · `O` ყველა სლაიდი · `A` სლაიდის ყველა ნაბიჯი · `Shift+→` შემდეგი სლაიდი.

## ცვლილების შეტანა

```bash
cd deck && pip install pygments && python3 build_df.py
cp ../out/index.html ../index.html && cp ../out/script.html ../script.html
```
