+++
categories = ["Bezpieczeństwo"]
date = 2020-12-22T23:00:00Z
description = "Jak nie stracić dostępu do konta"

[[images]] 
src = "images/meritt-thomas-0nDC2QgBojY-unsplash.jpg"
stretch = "both"

tags = ["Bezpieczenstwo"]
title = "Bezpieczniejsze tworzenie kont"
type = "post"

+++
### Dlaczego Twoje konto powinno być Twoje?

Załóżmy, że masz firmę.

Zamówiłeś, lub po prostu rozwijasz swoje oprogramowanie przy pomocy zewnętrznej firmy.
Twój partner biznesowy, nie tylko tworzy, ale też utrzymuje Twoje oprogramowanie. Zarządza Twoją chmurą, dla Ciebie.
#### Historia pisana przez życie 
Wszystko idzie dobrze, tworzysz nowe funkcjonalności, sprint za sprintem - i nagle coś nie gra. Pojawiają się opóźnienia w dostarczaniu poprawek, nowe funkcjonalności nie pojawiają się w ustalonym czasie, lub wręcz... wcale.

Masz problem, który próbujesz rozwiązać nie płacąc za kolejne faktury. To nie działa, nagle zostajesz odcięty od kodu aplikacji, a Twoje konto deweloperskie, ba! produkcyjne, przestaje być Twoje.

#### Zaufanie

Okazuje się, że zaufanie, które miałeś do dostawcy Twojej aplikacji, straciło swoją ważność; mleko się rozlało. 

Zaufanie było tak wielkie, że wszelkie konta AWS (deweloperskie, produkcyjne), a także repozytorium kodu, były zarejestrowane na dane partnera. To on posiada dostęp do skrzynek email, których adresy zostały użyte do rejestracji kont w AWS.

Tak, faktury za usługi chmurowe były wystawione na Ciebie, ale to email konta Root na Twoim koncie AWS jest kluczowy. To właśnie w oparciu o ten adres email potwierdzasz w pewnym sensie tożsamość właściciela konta.

Być może Twoja decyzja była słuszna, podparta brakiem odpowiednio wyszkolonego personelu.

Prawda jest taka, że bez dostępu do konta email (pamiętasz, wspomniałem wyżej o koncie root), nie masz formalnie możliwości odzyskać dostępu do swojego konta AWS. Co więcej - nawet, jeśli masz dostęp do konta AWS poprzez inne, sobie znane sposoby, to nadal nie jesteś w stanie zmienić dostępu dla konta root, ponieważ nie masz dostępu do tego adresu email.

#### Jak żyć?

Kilka podstawowych zasad:

* Użyj organizacji, a konto główne (root) niech będzie zarejestrowane przy użyciu adresu email (najlepiej listy dystrybucyjnej) w Twojej domenie. Takiej, która jest Twoja, a nie należy do firm trzecich.
* Pozostałe konta również twórz z poziomu Organizacji, jako konta zależne od Organizacji, również używając DLek (list dystrybucyjnych) w tej samej, należącej do Ciebie domenie.
* Gdy masz tylko jedno, czy dwa konta, a organizacja z jakiegoś powodu nie jest Twoją bajką, nadal obowiązuje ta sama zasada. Tworzysz konta przy użyciu adresów email w **Twojej** **domenie, do których zawsze możesz uzyskać dostęp**.
* Używaj wieloskładnikowego uwierzytelniania do konta Root (innych również) i niech klucz sprzętowy, lub chociaż token, będzie w Twoim posiadaniu (tutaj są różne dostępne opcje i scenariusze, wszystko zależy od wewnętrznych regulacji).
* Klucz sprzętowy - zawsze możesz go przechowywać w bezpiecznym miejscu, szczególnie, że konta root nie powinieneś używać na co dzień.
* Niech Twoje konta AWS będą Twoje, a nie dostawcy. Tak, ostatecznie pewnie wygrasz sprawę w którejś instancji sądu, ale zanim wygrasz, Twój biznes może już nie istnieć. Stąd: niech Twoje konta będą Twoje.
* Pamiętaj, że email również powinien być zabezpieczony dodatkowym składnikiem uwierzytelniania, bowiem łańcuch pęka tam, gdzie jego najsłabsze ogniowo. Innymi słowy, ktoś może przejąć Twoje konto email, a dzięki temu uzyskać dostęp do konta AWS.
