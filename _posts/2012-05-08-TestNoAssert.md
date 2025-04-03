---
layout: post
title:  Ein Test ohne Assert
date:   2012-05-08 23:23 +0200
categories: testing german
---
[Daniel Minigshofer](http://danielminigshofer.blogspot.de/) von [it-agile](http://www.it-agile.de/) schreibt über [Test-Antipatterns](http://danielminigshofer.blogspot.de/2012/05/4-der-habgierige-fanger-10-anti.html) und macht Vorschläge zum besseren Umgang mit Exceptions. Dabei schreibt er:  
> Es wäre auch möglich ohne eine Assert-Anweisung diesen Test zu schreiben. Jedoch einen Test ohne Assert ist kein wirklicher Test. Außerdem ist es für andere Entwickler nicht ersichtlich was hier eigentlich getestet wird.

Leider geht er nicht weiter darauf ein, und lässt mich allein mit dem Sesamstraßen-Dreiklang: "Wieso? Weshalb? Warum?"

**Science to the rescue!**

1. Definiere "wirklicher Test"
2. Finde Gegenbeispiele, die der Definition genügen, aber kein Assert haben.

Der erste Teil scheint einfach: "Given" - "When" - "Then" sollte völlig ausreichen.
Im ersten Schritt bereite ich die Elemente vor, die ich brauche, um das gewünschte Verhalten bestimmen, im zweiten Schritt löse ich das Verhalten aus, im dritten Schritt formuliere ich eine Annahme, der die Wirklichkeit standhalten soll.

Augenscheinlich ist nach Daniels Definition die Verständlichkeit für Dritte nicht Teil der Eigenschaften eines wirklichen Tests, aber ich denke, dass ein Test ohne erklärende Zusammenfassung langfristig nicht sehr wertvoll ist. Laden wir das noch dazu, und fassen zusammen:  
_Ein Test besteht aus Vorbereitung, Durchführung und Überprüfung und einer erklärenden Beschreibung._

Trommelwirbel, Tusch, Gegenbeispiel: **Objektkonstruktion**.
Gegeben sei ein schlecht strukturiertes komplexes Objekt, zum Beispiel ein SSH-Klient.  
Er kann sich auf verschiedene Arten gegenüber dem Server authentisieren, etwa über Benutzernamen und Passwort oder über ein Schlüsselpaar.  
Leider kann er nicht beides gleichzeitig, und wenn ich den Konstruktor überfordere, indem ich Schlüssel und Passwort angebe, schmeißts Exceptions, natürlich ebenso, wenn ich einen öffentlichen, aber keinen privaten Schlüssel benenne.  

Das fiktionale Ganze sieht also etwa so aus:

    public SSHClient(String host, int port, String username, String password, String pathToPublicKey, String pathToPrivateKey)

Mein Test soll zeigen, welche Argumente ich gemeinsam verwenden darf, um das System anzusprechen.

    @Test
    public void canBeConstructedWithUsernameAndPasswordAlone(){
        String host = "myhost.example.com";
        int port = 22;
        String user = "urs";
        String pass = "asecret"
        new SSHClient(host, port, user, pass, null, null);
    }


Beschreibung? Check.  
Vorbereitung? Check.  
Durchführung? Check.  
Zusicherung? Check - denn die Konstruktion ist erfolgreich und schmeißt keine Exception.  

Ich sage "wirklicher Test".  

Die Sinnhaftigkeit des ganzen ergibt sich aus dem Kontext, etwa wenn weitere Tests zeigen, dass andere Parameterkombinationen Exceptions mit sinnvollen Texten werfen, die den Klienten schnell und direkt auf seinen Fehler hinweisen.  

Warum sollte ich mehr schreiben, als nötig ist? Schreibt mir eure Gedanken.