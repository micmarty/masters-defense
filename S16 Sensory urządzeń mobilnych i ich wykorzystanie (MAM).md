 # S16 Sensory urządzeń mobilnych i ich wykorzystanie (MAM)
 
Sensory i ich działanie uzależnione jest od współpracy producentów sprzętu i
oprogramowania
Część sensorów ma charakter programowy, ale najczęściej są uzależnione
(wywiedzione) od sprzętowych

### Podstawowe sensory

- Akcelerometr - mierzy przyspieszenie liniowe, pozwala na określenie odchyleń w 3 osiach
- Żyroskop - mierzy położenie kątowe (orientację)
- Magentometr - działa jak kompas, mierzy siłę, kierunek i zwrot pola magnetycznego. Zastosowanie: Google Maps - w którym kierunku jesteśmy skierowani
- GPS - mierzy aktualną pozyzję urządzenia (pozycję na mapie)

### Czujniki (część dalsza)
- biometryczny - pozwala na identyfikowanie właściciela (odcisk palca - teraz nawet pod ekranem, wzór siatkówki oka, cechy twarzy - iPhone X)

- zliżeniowy - wykrywa obecność styczności z powierzchnią (policzek w trakcie rozmowy, ekranem do biurka), odpowiedzialny zazwyczaj za blokowanie i wygaszanie ekranu - oszczędza baterię

- nacisku - 3D touch z iPhone 7

- światła - reaguje na natężenie światła, tak żeby móc regulować jasność ekranu - oszczędzanie energii

- temperatury - dodatkowo może pełnić funkcję zabezpieczającą przegrzaniu (wyłączenie telefonu)

- wilgotności - często jest ukryty przez użytkownikiem. W przypadku choćby jednego zalania obnaża winę właściciela przy serwisowaniu

- barometr - ciśnienie, przydatne do określenia wysokości (altitude)

- mikrofon - oczywiste rzeczy: prowadzenie rozmów, dyktafon, mierzenie poziomu hałasu. Poza tym można wykorzystywać drugi mikrofon w telefonie (np. umieszczony na górze obudowy) tak, żeby zbierał odgłosy otoczenia, generując profil szumu i oczyszczał ostatecznie przekazywany głos rozmówcy

### Wirtualne, programowe - wywiedzione) od sprzętowych:
- kroków (wirtualny) - pedometr bazujący na akcelerometrze
- kodów QR
...


### Android
Do oczytywania danych z sensorów wykorzystuje się API zawarte w SDK.
Najpierw należy zarejestrować nasłuchiwacza `registerListener` z klasy `SensorManager`.
Potem możemy zdefiniować co ma się dziać po nadejściu `SensorEvent`'a przy pomocy `onSensorChanged()`.

Metody dla `SensorEventListener`'a
`onSensorChanged(SensorEvent event)` - wywoływana automatycznie gdy wartość mierzona przez sensor uległa zmianie. Obiekt zawiera informacje o śledzonym sensorze + tablicę float z danymi. To ile tych danych jest zależy od sensora, ale na ogół są 3 wartości (np. akcelerometr, magnetometr)

`onAccuracyChanged(Sensor sensor, int accuracy)` - wywołana gdy dokładność pomiarów sensora ulegnie zmianie.
