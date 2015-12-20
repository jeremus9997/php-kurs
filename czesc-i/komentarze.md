# Drogowskazy - aby dążyć do doskonałości
 
Przyszła pora na **najważniejszą** część tego rozdziału.  Są to wskazówki, a raczej drogowskazy 
Ciężko było nam wybrać, co dać jako pierwszą wskazówkę, ale później doszliśmy do wniosku, że nieważne co będzie pierwsze, ważne aby zostało zapamiętane!  Czytaj uważnie!
 ___

## Wskazówka odnośnie pisania kodu PHP:

***Zła praktyka:***
Mieszanie kodu PHP z HTML może się skończyć dla Ciebie tragicznie, Twojego projektu i wspópracowników.  
Wyobraź sobie, że jesteś na miejscu pani Ewy, która dobrze zna się na HTML, ale z PHP nie miała zbytnio do czynienia. Dostała właśnie Twój projekt, ktoś kazał jej zmienić wygląd tabelki. Otwiera taki pomieszany plik i nie wie co tu się dzieje, zupełnie nie widzi gdzie kończy się tabelka a gdzie zaczyna. Skończyło się na tym, że zapomniała, iż przez pomyłkę usunęła jakąś zmienną z kodu i bum. 
 
**Dobra praktyka:**  
Zawsze staraj się oddzielać kod PHP od HTML w swoich skryptach. Na początku będzie ciężko, ale z czasem wejdzie to w nawyk. Odseparowanie warstwy widoku od warstwy logiki ułatwia bardzo pracę. 

Pomyśl.
PS. Złapiesz plusa u pracodawcy :-)

## Wskazówka: *piękne komentarze*

Niech komentarze wyjaśniają „*dlaczego*”, a nie „*jak*”. 

Komentarze, które wyjaśniają, **jak** coś jest wykonywane, w rzeczywistości są duplikowaniem tego, co napisaliśmy w kodzie źródłowym. Po co programista ma czytać komentarz odnośnie tego, w jaki sposób poniższy kod działa - skoro może przeczytać ten kod. 

Komentarze typu **jak** są zwykle nadmiarowe. Spójrz, czy tutaj z komentarza dowiesz się więcej niż z samego kodu?

**Przykład komentarza, który koncentruje się na _jak_:**
```php
<?php
// jeżeli wiek użytkownika jest >= 18
if ($userAge >= 18) ...
```
Nieco lepiej wyglądać będzie taki komentarz:
```php
<?php
// Sprawdzanie wieku użytkownika
if ($userAge >= 18) ...
```
Jest on w formie **dlaczego** i z tego powodu jest dużo bardziej czytelny. 
Można zrobić jeszcze lepszy komentarz, który obejmuje sobą *zachowanie* danego *bloku* metody:
```php
<?php
// Sprawdzenie warunków dostępu do strony
if ($userAge >= 18 && $userAcceptRules === true)
```
Gdy kod osiąga taki poziom czytelności, właściwe staje się kwestionowanie
wartości komentarza. W tym przypadku lepszy kod sprawił, że komentarz jest nadmiarowy i prawdopodobnie może zostać usunięty. W tym przypadku komentarz spełnia rolę **nagłówka** opisywanego kodu. Bez wgłębiania się w logikę metody możemy się dowiedzieć, że akurat ten blok weryfikuje warunki akceptacyjne.

Gdy komentarz opisuje cały blok kodu po teście if, staje się komentarzem
podsumowującym i może pozostać w programie jako nagłówek opisujący następujący po nim akapit kodu.

***
**Używaj komentarzy, aby przygotować czytającego kod na dalszy ciąg**. 

Dobre komentarze informują czytającego kod o tym, czego powinien się spodziewać. 
Osoba czytająca program powinna mieć możliwość przejrzenia samych
tylko komentarzy i uzyskania dobrego obrazu tego, co dany kod robi i gdzie
znaleźć poszczególne operacje. Wynika z tego między innymi zasada, że komentarz powinien zawsze poprzedzać to, co opisuje. 

>Nie mówi się o tym na zajęciach z programowania, ale jest to powszechnie przestrzegana reguła.

```php
<?php
// Metoda sprawdza poprawność NIP
public function verifyNIP(NIP $nip) { 
    // ...
}
```
***
**Niech każdy komentarz ma znaczenie**. 

Nadmiar komentarzy nie przynosi żadnych korzyści — zbyt duża ich liczba zmniejsza czytelność opisywanego kodu.
Zamiast pisać więcej komentarzy, lepiej włożyć dodatkowy wysiłek w zwiększenie czytelności samego programu

***

**Unikaj skrótów**. 

Komentarze powinny być jednoznaczne i czytelne bez dodatkowego wysiłku niezbędnego do rozszyfrowania znaczenia skrótów. 

Unikaj wszelkich skrótów poza najbardziej oczywistymi. Gdy nie wpisujesz komentarzy na końcu wierszy, nie jest to zazwyczaj problemem. 

**Błędne użycie komentarzy:**
```php
<?php
$foundNumber = $this->searchNumber(); // Szuka liczby
$foundDigit  = $this->searchDigit();  // Szuka cyfry
$foundChar   = $this->searchChar();   // Szuka literki
```
***
**Opisuj komentarzami wszystko, co ma związek z błędami i  nieudokumentowanymi cechami języka lub środowiska.** 

Jeżeli masz do czynienia z błędem, jest on prawdopodobnie nieudokumentowany. Nawet jeżeli został gdzieś opisany, nie zaszkodzi dodatkowy opis w kodzie. Jeżeli masz do czynienia z nieudokumentowaną cechą języka lub środowiska, to niejako z definicji brak jakiegokolwiek jej opisu i powinien on znaleźć się w programie.

***

**Zapisuj uzasadnienia odstępstw od dobrego stylu programowania.** 
Jeżeli musisz odejść od dobrego stylu programowania, wyjaśnij, dlaczego to robisz.
Pozwoli to uniknąć sytuacji, w których pełen dobrych intencji programista
dostosowuje kod do lepszego stylu, zmieniając zarazem jego działanie. Takie uzasadnienie będzie potwierdzeniem tego, że wiedziałeś, co robisz, i że zaskakująca konstrukcja nie wynika z niedbalstwa — *nie pozwól, aby ktoś oskarżał Cię o pisanie złego kodu!*

Starając się opisać kod, koncentruj się przede wszystkim na samym kodzie.
*Warto przypomnieć, że sam kod programu jest pierwszym rodzajem dokumentacji, który warto dopracować.* 

***

**Używaj stylów, które nie sprawiają kłopotu przy wprowadzaniu zmian.**

Praktycznie każdy bardziej wyszukany styl sprawia problemy przy aktualizowaniu komentarzy i kodu. Spróbuj na przykład wskazać w poniższych komentarzach część, która jest najbardziej narażona na ignorowanie przez programistów wprowadzających zmiany:
```php
<?php
/*************************************
 * Program jest pięknie udokukomentowany *
 * Nic mu nie brakuje, a jak komuś   *
 * coś nie pasi to nie musi czytać   *
 *************************************/
//--------------------------------------+
//           Piękny komentarz           |
//======================================+
// Autor: PHPKurs                       |
//--------------------------------------+
```
Istotną rzeczą jest to, aby zwracać uwagę na to, **jak wykorzystywany jest czas poświęcany na pracę z kodem**. Jeżeli spędzasz dużo czasu, wprowadzając i usuwając poziome kreski, aby dopasować długość podkreśleń do długości komentarzy, to **nie jest** to już programowanie, ale proste *marnotrawienie* czasu. Lepiej znaleźć inny, praktyczniejszy styl komentarzy. 

***
**Aby zredukować czas poświęcany na pisanie komentarzy, używaj procesu programowania w pseudokodzie.**

Pisanie zarysu programu w postaci komentarzy jeszcze przed rozpoczęciem budowy właściwego kodu niesie ze sobą kilka istotnych korzyści. Gdy kończy się praca z kodem, komentarze są już gotowe. Nie ma potrzeby poświęcania na nie dodatkowego czasu. Zyskujesz także wszystko to, co daje pisanie wysokopoziomowego pseudokodu przed utworzeniem niskopoziomowego kodu w języku programowania.

***

**Włączaj komentowanie do procesu programowania.**

Alternatywą dla włączenia pisania komentarzy do procesu programowania jest pozostawienie pracy nad nimi na sam koniec projektu. Ma to jednak wiele wad. Przede wszystkim, pisanie komentarzy staje się wtedy kolejnym zadaniem do wykonania, co sprawia, że wydaje się bardziej pracochłonne niż przy komentowaniu na bieżąco.
Dodatkowo późne pisanie komentarzy jest faktycznie bardziej pracochłonne, bo zmusza do przypominania sobie lub sprawdzania, co robią poszczególne fragmenty kodu, zamiast prostego zapisania tego, co można zapisać bez zastanowienia w trakcie tworzenia tych fragmentów. Takie komentarze są też mniej dokładne, bo łatwo zapomnieć o niektórych założeniach i drobnych szczegółach projektu.

Typowy argument przeciwko komentowaniu kodu na bieżąco brzmi: 
>Gdy koncentrujesz się na pracy z kodem, nie powinieneś rozpraszać się, pisząc komentarze. 

Kod, który wymaga tak mocnej koncentracji, to ważny sygnał ostrzegawczy.

Jeżeli projekt jest trudny do zapisania w postaci kodu programu, uprość taki
projekt, jeszcze zanim zaczniesz zajmować się komentarzami czy kodem. Jeżeli użyjesz do uporządkowania swoich zamysłów pseudokodu, pisanie kodu stanie się proste, a komentarze powstaną automatycznie.

***

**Wydajność nie jest dobrym powodem, by unikać komentarzy.** 

Jedną z rzeczy, które wciąż powracają z kolejnymi falami technologii, są środowiska interpretujące kod (IDE). Kiedyś komentarze powodowały w nich mierzalne obniżenie szybkości pracy. Dziś już nie jest to takim problemem. 

Dziś można tworzyć specjalną, finalną wersję kodu wykorzystywanego w codziennej pracy. Zazwyczaj wykorzystuje się do tego celu narzędzia automatycznie usuwające komentarze w trakcie procesu generowania programu docelowego.

***

**Umieszczaj komentarze blisko kodu, który opisują.** 

W trakcie konserwacji i rozbudowy programu komentarze odległe od  modyfikowanych fragmentów są często ignorowane. Gdy komentarze i kod przestają być ze sobą zgodne, komentarze *stają się* bezużyteczne. Dużo lepiej przestrzegać **Zasady Bliskości** i umieszczać komentarze jak najbliżej kodu, który opisują. 

Poniżej opisuję kilka elementów, które warto zastosować przy opisie metod za pomocą komentarzy:

>**Opisuj metody jednym – dwoma zdaniami w umieszczanym przed nimi komentarzu.**

 Jeżeli nie jesteś w stanie opisać procedury w jednym lub dwóch krótkich zdaniach, to prawdopodobnie powinieneś poświęcić nieco czasu na zastanowienie się nad jej rolą w programie. Trudności w  formułowaniu krótkiego opisu są sygnałem, że projekt nie jest w pełni dopracowany. ***Oderwij się od pisania kodu i poświęć nieco czasu na poprawienie projektu.***

>**Opisuj założenia interfejsu.** 

Dokumentowanie założeń interfejsu można traktować jako uzupełnienie innych zasad pracy z komentarzami. Jeżeli budowa procedury opiera się na jakichkolwiek założeniach dotyczących stanu przekazywanych zmiennych — wartości dopuszczalne i niedopuszczalne, kolejność elementów tablic, zainicjowanie pewnych danych składowych czy to, że zawierają tylko poprawne dane — opisuj te założenia albo w prologu procedury, albo przy deklaracjach danych. ***Takich informacji w komentarzach wymaga praktycznie każda procedura.***

Dbaj też o informacje o wykorzystywanych danych globalnych. Zmienna globalna jest w równym stopniu elementem interfejsu procedury, co każda inna. Gdy w trakcie pisania procedury zauważasz, że kod wykorzystuje pewne założenia dotyczące jej interfejsu, nie zwlekaj z zapisaniem tych założeń w komentarzach.

>**Opisuj globalne skutki wykonania procedury.** 

Jeżeli procedura modyfikuje dane globalne, opisuj dokładnie, na czym polegają te modyfikacje. 

**Pamiętaj:** modyfikowanie danych globalnych jest przynajmniej o rząd wielkości bardziej niebezpieczne niż ich odczytywanie.
Zmiany takie należy więc wprowadzać **bardzo ostrożnie**, a częścią tej ostrożności jest zapewnienie odpowiedniego opisu. Podobnie jak w innych sytuacjach, gdy pisanie takich opisów staje się uciążliwe, przepisz kod od postaw, redukując użycie zmiennych globalnych.

>**Informuj o źródłach stosowanych algorytmów.** 

Jeżeli używasz algorytmu opisanego w książce lub artykule, podaj tytuł książki lub artykułu i numer strony.
Jeżeli napisałeś algorytm sam, zapewnij informację o tym, gdzie można znaleźć notatki dotyczące tego algorytmu.

### Opisy klas
Dla każdej klasy utwórz blok komentarza opisujący jej podstawowe atrybuty:

**Opisuj sposób projektowania klasy.** 

Bardzo pomocne są komentarze ogólne, dostarczające informacji, których nie można w prosty sposób odtworzyć na podstawie kodu. Opisuj podejście przyjęte przy projektowaniu klasy, ogólną filozofię tego podejścia oraz rozważone i odrzucone alternatywy.

**Opisuj ograniczenia, założenia i inne podobne aspekty.** 

Podobnie jak w przypadku procedur dbaj o opisy ograniczeń wynikających z projektu klasy. Opisuj też założenia dotyczące danych wejściowych i wyjściowych, schemat obsługi błędów, globalne skutki wykonywanych operacji, źródła algorytmów itd.

**Opisuj interfejs klasy.** 

Czy inny programista będzie w stanie określić, jak używać klasy bez przeglądania jej implementacji? Jeżeli nie, hermetyzacja klasy jest zagrożona. Interfejs klasy powinien zawierać całość informacji niezbędnych do korzystania z tej klasy. 

**Nie opisuj w interfejsie klasy szczegółów implementacji.** 

Podstawową zasadą hermetyzacji jest udostępnianie wyłącznie tych informacji, których udostępnienie jest konieczne. Jeżeli kwestia potrzeby ujawnienia pewnej informacji budzi wątpliwości, ogólną zasadą jest jej nieujawnianie. Pliki interfejsu klasy powinny zawierać informacje niezbędne do korzystania z tej klasy, ale nie informacje potrzebne do pracy z jej kodem.

###Pliki *.php
**Opisuj przeznaczenie i zawartość pliku.** 

Komentarz nagłówkowy pliku powinien opisywać klasy lub procedury zawarte w tym pliku. Jeżeli w pliku znajdują się wszystkie procedury programu, przeznaczenie pliku jest dość oczywiste — jest to plik zawierający cały program. Jeżeli rolą pliku jest przechowywanie
kodu klasy, jego przeznaczenie jest także oczywiste — jest to plik zawierający klasę o nazwie podobnej do nazwy pliku.

**Zapisuj w bloku komentarza notę copyright.** 

Wiele firm dba o to, aby w programach znajdowały się informacje o prawach autorskich, klauzule poufności plików i inne elementy natury prawnej. Jeżeli pracujesz w takiej firmie, umieść w pliku notę podobną do przedstawionej poniżej. Możesz też spytać doradcę prawnego firmy, jakie informacje powinny znaleźć się w plikach.