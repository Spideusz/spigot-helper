# Spigot-Helper

Jak tworzyć nowy plik?

Aby to działało musisz stworzyć konfig domyślny w pluginie aby to zrobić poprostu dopisz w głownej klasie pluginu w voidzie
onEnable() taką linijke:

```java

saveDefaultConfig();

```

Pierwsze zainicjuj klase FileHelper, stwórz konstruktor aby przywołać ścieżkę do pliku i jego nazwę [Example]:

```java

// FileHelper fileHelper = new FileHelper(glowna_klasa_pluginu, "sciezka do pliku", "nazwa pliku");

FileHelper fileHelper = new FileHelper(main, "stajnia", "owca");

```
1. Stwórzmy plik:

```java

fileHelper.createFile();

```


Teraz zapiszmy coś w pliku:

2. Najpierw trzeba stworzyć konfiguracje pliku :)

```java

YamlConfiguration yamlConfiguration = YamlConfiguration.loadConfiguration(fileHelper.getFile());

```

3. Zabierzmy się do zapisania wieku owcy:

```java

yamlConfiguration.set("wiek", 10);

```

4. Na koncu zapiszmy konfig:

```java

fileHelper.saveFile(yamlConfiguration);

```

5. Powinnismy miec stworzony plik o nazwie 'owca' w folderze stajnia w katalogu plugins/[NaszPlugin] z zawartością:

```yaml

wiek: 10

```
