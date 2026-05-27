# W tym Zadaniu domowym były pytania na które należało odpowiedzieć 

## 1. Dla każdego z poniższych problemów określ, jaki to typ zadania ML:
**Przewidywanie ceny samochodu na podstawie przebiegu i roku produkcji** \
Będzie to zadanie z typu regresji ponieważ na bazie jakiś danych będą szacowane wartości
numeryczne (cena) samochodu.

**Grupowanie artykułów w sklepie internetowym według podobieństwa** \
Jako że chcemy grupować coś, i nie mamy wprost podanych klas będzie to klasteryzacja

**Wykrywanie twarzy na zdjęciu z kamery**\
Detekcja, patrzy na obraz i szuka czy znajduje się tam twarz

**Klasyfikacja emaili jako spam/nie-spam**\
Będzie to klasyfikacja gdyż mamy podane końcowe klasy do których maile będą
przypisywane

**Generowanie opisów produktów na podstawie zdjęć**\
Jest to najprawdopodobniej mieszanka zadań gdyż zostanie dodatkowo użyta detekcja
albosegmentacja, ale mówiąc wprost będzie to zadanie generowania.


## 2. Określ, jakie podejście do uczenia(supervised/unsupervised/semi-supervised/reinforcement) jest najbardziej odpowiednie dla:
**Segmentacja klientów sklepu (brak danych o grupach)**\
unsupervised - nie mamy żadnych danych o grupach więc wnioski musi model sam
wyciągnąć

**Klasyfikacja zdjęć kotów vs psów (mamy 10,000 opisanych zdjęć)**\
supervised - wszystkie dane są opisane

**Nauczenie robota chodzenia**\
reinforcement - przy wykonaniu dobrych ruchów lub pełnych kroków robot jest “nagradzany”

**Rozpoznawanie twarzy (mamy 1,000 opisanych + 100,000 nieopisanych zdjęć)**\
semi-supervised - tylko część danych jest opisana


## 3. Dla każdego problemu określ, czy to regresja czy klasyfikacja:
Przewidywanie liczby sprzedanych produktów w następnym miesiącu
Regresja - przewidywana jest liczba
Określenie, czy klient zrezygnuje z usługi (tak/nie)
klasyfikacja - klient na końcu zadania jest przypisywany do jakiejś klasy
Szacowanie czasu dostawy paczki
regresja - jest przewidywana liczba oznaczająca czas dostawy
Klasyfikacja gatunku kwiatu (Iris setosa/versicolor/virginica)
klasyfikacja - są podane gatunki kwiatów, które można uznać za klasyfikacje, do których
kwiaty będą przypisywane
Przewidywanie ceny akcji za tydzień
regresja - na bazie danych historycznych zostaje przewidywana liczba oznaczająca cenę
akcji


## 4. Wyobraź sobie, że tworzysz system filtrowania spamu dla firmy email. Pytania:
### Jakie dane potrzebujesz do treningu modelu?
### Jaki typ zadania ML to jest?
### Jakie podejście do uczenia zastosujesz?
### Jakie cechy (features) emaila mogą być użyteczne?
### Jak ocenisz, czy model działa dobrze?
Aby stworzyć system filtrowania spamu dane potrzebne to zbiór maili które zawierają treść,
temat, nadawcę oraz inne informacje.
Jeśli oznaczenie spamu jest obecne to typem zadania które można użyć to klasyfikacja,
ponieważ model ma przypisać maila do jednej z 2 klas. W takim przypadku zastosował bym
supervised learning ponieważ posiadamy dane oznaczone.
Jeśli tych oznaczeń o tym czy mail jest spamem czy nie użyć można klasteryzacji oraz
unsupervised learning, aby grupować podobne wiadomości i próbować wykrywać
podejrzane wzorce.
Przykładowe cechy, które mogą być użyteczne to: temat, treść, liczba linków, adres
nadawcy.
Aby sprawdzić skuteczność modelu podzieliłbym dane na zbiór treningowy i
testowy/walidacyjny. Następnie ocenił model za pomocą metryk takich jak accuaracy.


## 5. Masz do wyboru dwa modele: 
### Model A: accuracy 92%, czas treningu 10 minut na CPU 
### Model B: accuracy 94%, czas treningu 12 godzin na GPU 
### Pytania: Który model wybierzesz i dlaczego? W jakich sytuacjach warto wybrać Model B mimo większego zużycia energii? Jakie czynniki poza accuracy i energią warto rozważyć?
Obydwa modele mają swoje miejsce, model A mimo mniejszego accuracy trenowany jest na
CPU w bardzo krótkim czasie. Oznacza to że niezależnie od sprzętu który mamy można go
szybko wytrenować i szybko użyć. Myślę że jest to bardzo dobry model dla mniejszych
biznesów oraz dla prywatnego użytku.
Natomiast model B wymaga znacznie dłuższego czasu trenowania na GPU do którego nie
wszystkie komputery mają dostęp. Różnica 2% może nie wydawać się duża ale dla prac
krytycznych, na przykład w medycynie, każdy punkt procentowy który zwiększy szanse na
uratowanie komuś życia jest opłacalny.
Poza accuracy i energii warto rozważyć wielkość modelu, ilość potrzebnych danych
treningowych, koszt infrastruktury, łatwość aktualizacji i utrzymania.
W normalnym użytku w nie krytycznej dziedzinie zawsze wybrałbym model A ponieważ
accuracy jest stosunkowo wysokie jak na wymagany czas treningu i potrzebnej infrastruktury
co pozwala na szybsze dotrenowanie modelu i prostsze utrzymanie.


## 6. Masz bazę 100,000 klientów sklepu. Chcesz ich podzielić na grupy w celu personalizacji ofert. 
### Scenariusz A: Masz dane o klientach (wiek, dochód, historia zakupów), ale NIE masz gotowych kategorii.
### Scenariusz B: Masz dane o klientach I ręcznie sklasyfikowałeś 10,000 z nich do 5 kategorii.
Scenariusz A to unsupervised learning ponieważ nie mamy gotowych kategorii klientów.
Można tutaj użyć klasteryzacji, żeby grupować klientów na podstawie podobnych cech takich
jak wiek, dochód czy historia zakupów. Zaletą jest brak potrzeby ręcznego oznaczania
danych, ale wadą jest to, że grupy mogą nie być zbyt dokładne albo biznesowo przydatne.
Scenariusz B to supervised learning ponieważ mamy już 10 000 klientów przypisanych do 5
kategorii. Model może nauczyć się tych kategorii i przypisać do nich resztę klientów. Zaletą
jest zwykle większa dokładność i lepsze dopasowanie do potrzeb biznesowych, ale wadą
jest konieczność ręcznego przygotowania danych treningowych.
Najlepsze wyniki najczęściej da scenariusz B, ponieważ model uczy się już na gotowych
przykładach i wie, czego dokładnie oczekujemy


## 7. Transfer Learning Firma farmaceutyczna chce klasyfikować zdjęcia komórek (zdrowe/chore). Ma 2,000 opisanych zdjęć. 
### Opcja A: Trenuj model od zera na 2,000 zdjęciach 
### Opcja B: Użyj gotowego modelu wytrenowanego na milionach zdjęć medycznych i dostosuj do swojego problemu.
Opcja B, czyli transfer learning, zużyje mniej energii, ponieważ model jest już wcześniej
wytrenowany i trzeba go tylko dostosować do naszego problemu. Dzięki temu trening trwa
dużo krócej i wymaga mniej mocy obliczeniowej.
Najprawdopodobniej również opcja B da lepsze wyniki, ponieważ 2 000 zdjęć to raczej mały
zbiór danych do trenowania dużego modelu od zera. Gotowy model nauczył się już
rozpoznawania różnych wzorców na milionach zdjęć medycznych.
Transfer learning jest podejściem „Green AI”, ponieważ pozwala ponownie wykorzystać już
wytrenowane modele zamiast za każdym razem trenować nowe od początku. Dzięki temu
zużywa się mniej energii, czasu i zasobów sprzętowych.


## 8. Wymyśl 3 przykłady projektów Data Science, które mogą pozytywnie wpłynąć na środowisko.
1. System przewidywania zużycia energii w budynkach
Problem: zbyt duże zużycie energii i marnowanie prądu.
Typ ML: regresja
Dane: temperatura, godziny pracy budynku, zużycie energii z poprzednich dni, liczba osób w
budynku.
Wpływ: zmniejszenie zużycia energii i emisji CO₂ dzięki lepszemu zarządzaniu ogrzewaniem
i prądem.
2. System wykrywania nielegalnych wysypisk śmieci ze zdjęć dronów
Problem: nielegalne wysypiska i zanieczyszczenie środowiska.
Typ ML: klasyfikacja/detekcja.
Dane: zdjęcia z dronów lub satelitów oznaczone jako „wysypisko” lub „brak wysypiska”.
Wpływ: szybsze wykrywanie odpadów i łatwiejsze sprzątanie terenów zanieczyszczonych.
3. System optymalizacji tras śmieciarek
Problem: zbyt długie trasy powodujące większe spalanie paliwa.
Typ ML: optymalizacja lub uczenie ze wzmocnieniem.
Dane: lokalizacje pojemników, poziom ich zapełnienia, dane GPS i ruch drogowy.
Wpływ: mniejsze zużycie paliwa, mniej spalin i bardziej efektywny odbiór odpadów.