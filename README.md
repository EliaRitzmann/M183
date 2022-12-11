# Lern-Bericht
Elia Ritzmann

## Einleitung
🧐 Der sogenannte "Open Redirect" beschreibt eine Sicherheitslücke, bei der URLs für Weiterleitungen nicht darauf überprüft werde, ob sie dabei die Webseite verlasse. So kann man zum Beispiel nach dem Anmelden auf eine Seite gelange, deren URl nahezu identisch aussieht (1 Zeichen unterschied) und dessen Design gleich aussieht, um übers Ohr gezogen zu werde. 



## Was habe ich gelernt?

📝 Bei diesem Projekt habe ich gelernt, wie man eine Redirect URL überprüfen kann und somit wie man einen "Open Redirect" verhindert.

## Beschreibung

```java
public void back() {
        FacesContext context = FacesContext.getCurrentInstance();
        HttpServletResponse response = (HttpServletResponse) context.getExternalContext().getResponse();
        try {
            if(redirectionUrl.startsWith("http://localhost:8080/")){
                
                response.sendRedirect(redirectionUrl);
            }

        } catch (IOException ex) {
            Logger.getLogger(NewsController.class.getName()).log(Level.SEVERE, null, ex);
        }
        return;

    }
    
```

✍️ Verwenden Sie drei verschiedene Medien, um zu zeigen, was Sie gelernt haben. Zum Beispiel:

* Eine textliche Beschreibung
* Ein deutliches, aussagekräftiges Bild oder eine kommentierte Bildschirm-Aufnahme
* Ein gut dokumentierter Code-Fetzen
* Ein Link zu einem *selbst aufgenommenen* youtube-Video oder `.gif`.

## Verifikation

✍️ Erklären Sie kurz und bündig, inwiefern die von Ihnen verwendeten Medien zeigen, was Sie gelernt haben.

# Reflektion zum Arbeitsprozess

👍 Überlegen Sie sich jeweils etwas, was gut an Ihrer Arbeit lief; 

👎 und etwas, was nicht gut lief.

**VBV**: ✍️ Formulieren Sie davon ausgehend einen *handelbaren* Verbesserungsvorschlag.
