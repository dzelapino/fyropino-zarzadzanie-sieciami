# Sprawozdanie

## Wstęp i uzasadnienie wyboru topologii

Firma XYZ, średniej wielkości przedsiębiorstwo, działające w branży IT, zdecydowała się na topologię gwiazdy jako odpowiednią dla swoich potrzeb. Topologia gwiazdy oznacza, że każde urządzenie w sieci jest połączone z centralnym punktem, czyli switchem lub routerem. Jest to rozwiązanie powszechnie stosowane w środowiskach biznesowych ze względu na jego elastyczność, łatwość zarządzania oraz możliwość szybkiego wykrywania i rozwiązywania problemów.

Ta topologia jest idealna dla firmy XYZ ze względu na jej strukturę działów i zespołów. Każdy zespół (Developers, Helpdesk, Sales, Biuro) może być reprezentowany jako jeden "promień" gwiazdy, a centralny switch lub router pełni rolę "centrum" sieci, które pozwala na komunikację między różnymi częściami organizacji.

Topologia sieci została zaprojektowana tak, aby umożliwić łatwe zarządzanie oraz monitorowanie ruchu sieciowego. Dodatkowo, zwrócono uwagę na możliwość rozbudowy i adaptacji sieci w przyszłości, aby sprostać ewentualnym zmianom w strukturze firmy oraz wzrostowi liczby użytkowników i danych przesyłanych w sieci.

Ostateczny wybór topologii uwzględniał również dostępność technologii oraz dostępność sprzętu sieciowego na rynku, aby zapewnić efektywną realizację projektu modernizacji sieci. Dzięki temu firma może być pewna, że nowa topologia sieci będzie spełniać jej obecne i przyszłe potrzeby.

## Topologia sieci
Poniżej przedstawino rozkład urządzień w firmie. Wszystkie urządzienia połączone są za pomocą routerów i switchy do centralnego urządzenia.

1. Zespół Developers
- Liczba użytkowników: 18
- Sieć bezprzewodowa dla zespołu Dev1 (6 komputerów)
- Sieć przewodowa dla zespołu Dev2 (6 komputerów) i Dev3 (6 komputerów)
2. Zespół Helpdesk
- Liczba użytkowników: 12
- Sieć przewodowa dla 12 komputerów
3. Zespół Sales
- Liczba użytkowników: 10
- Sieć przewodowa dla 10 komputerów
4. Biuro
- Liczba użytkowników: 5
- Sieć przewodowa dla 5 komputerów

Każdy zespół ma swoją osobną sieć w celu izolacji danych i zwiększenia bezpieczeństwa. Wszystkie połączenia między zespołami oraz z biurem są kontrolowane i monitorowane w celu zapobiegania nieautoryzowanemu dostępowi.

## Plan modernizacji sieci
Powyższa topologia zostanie wdrożona do firmy na podstawie szczegółwoego planu modernizacji sieci. Został on podzielony na poszczgólne kroki. 

1. Segmentacja sieci
 W pierwszym kroku planu modernizacji sieci firma XYZ przeprowadzi segmentację sieci, dzieląc ją na osobne podsieci dla poszczególnych zespołów, tj. Developers, Helpdesk, Sales i Biuro. 
 Biuro będzie mogło komunikować się z każdym z zespołów (każdy zespół zna ścieżkę do biura i biuro do każdego). Zespoły nie będą mogły się ze sobą komunikować. Jedynym wyjątkiem będą zespoły dev1, dev2 i dev3. Dev1 zostanie podpięty do routera bezprzewodowego, który będzie należał do sieci routera dev2.
 Taka segmentacja pozwoli na izolację danych i zwiększenie bezpieczeństwa sieci poprzez kontrolę dostępu. Segmentacja sieci pozwoli również ograniczyć ryzyko ataków z zewnątrz oraz zapobiec rozprzestrzenianiu się ewentualnych zagrożeń między różnymi częściami sieci. Każda podsieć będzie miała osobny zakres adresów IP, co ułatwi zarządzanie ruchem sieciowym i identyfikację urządzeń w sieci. 
 Dzięki podziałowi na osobne podsieci możliwe będzie wprowadzenie bardziej precyzyjnych zasad kontroli dostępu oraz zabezpieczeń, co zwiększy ogólne bezpieczeństwo sieci.

 2. Aktualizacja urządzień
 Firma zakupi nowe urządzenia, takie jak routery i switche o wyższej przepustowości oraz nowoczesnych funkcjach, które będą mogły obsłużyć rosnącą liczbę użytkowników i zapewnić stabilność oraz szybkość transferu danych. Nowe urządzenia będą również wyposażone w nowoczesne funkcje, takie jak zaawansowane protokoły routingu, co umożliwi bardziej elastyczne zarządzanie siecią i dostosowanie jej do potrzeb firmy. Nowy sprzęt sieciowy, choć początkowo wymaga inwestycji, z czasem przyniesie korzyści w postaci obniżonych kosztów utrzymania, dzięki mniejszej awaryjności oraz większej efektywności działania.

 3. Implementacja VPN
 Implementacja VPN jest niestety niemożliwa w wersji Packet Tracer 8.2.x. Jest jednak niezbędna, pownieważ umożliwi pracownikom firmowym bezpieczny zdalny dostęp do zasobów sieciowych, nawet spoza biura, poprzez szyfrowane połączenia. Będzie wymagała odpowiedniej konfiguracji zarówno na poziomie serwerów VPN, jak i klientów, w celu zapewnienia bezpieczeństwa transmisji danych oraz uwierzytelnienia użytkowników. Po wdrożeniu VPN firma będzie mogła monitorować ruch sieciowy związany z połączeniami VPN oraz zarządzać nimi w sposób efektywny, np. poprzez ograniczenie dostępu do określonych zasobów tylko dla uprawnionych użytkowników.

 ## Podsumowanie
 Projekt modernizacji sieci firmy XYZ ma na celu usprawnienie infrastruktury sieciowej i zwiększenie bezpieczeństwa dostępu do zasobów. 
 
 Poprzez segmentację sieci na podsieci dla różnych zespołów oraz wybór topologii gwiazdy, firma zyskuje elastyczność, łatwiejsze zarządzanie i szybsze rozwiązywanie problemów.Aktualizacja sprzętu sieciowego, w tym routerów i przełączników o większej przepustowości, zwiększa wydajność sieci i obsługę rosnącej liczby użytkowników. Wdrożenie usługi VPN umożliwia bezpieczny zdalny dostęp do zasobów sieciowych. Zabezpieczenia sieci, takie jak zapory sieciowe, systemy antywirusowe oraz monitoring ruchu, poprawiają bezpieczeństwo i umożliwiają bieżące wykrywanie zagrożeń.

Dzięki tym działaniom firma zyskuje lepszą efektywność pracy, zwiększa bezpieczeństwo danych i jest gotowa na przyszłe zmiany i rozwój biznesu.