# Lern-Bericht
Elia Ritzmann

## Einleitung
🧐 Der sogenannte "Open Redirect" beschreibt eine Sicherheitslücke, bei der URLs für Weiterleitungen nicht darauf überprüft werde, ob sie dabei die Webseite verlasse. So kann man zum Beispiel nach dem Anmelden auf eine Seite gelange, deren URl nahezu identisch aussieht (1 Zeichen unterschied) und dessen Design gleich aussieht, um übers Ohr gezogen zu werde. 



## Was habe ich gelernt?

📝 Bei diesem Projekt habe ich gelernt, wie man eine Redirect URL überprüfen kann und somit wie man einen "Open Redirect" verhindert.

## Beschreibung

⚠️ In der InsecureApp wird auf der Profilseite die redirect URL in der URL für den User sichtbar weitergegeben. 

![image](https://user-images.githubusercontent.com/69593308/206909349-3c5daf84-e1e8-4259-9feb-437b8cebd42b.png)

Dadurch kann er sie verändern und könnte so die Weiterleitung auf eine externe Seite ändern.

✔️ Dies kann man jedoch leit beheben. indem man im Server die Redirect URL zuerst überprüft, bevor er sie dem Browser übergibt.

```java
public void back() {
        FacesContext context = FacesContext.getCurrentInstance();
        HttpServletResponse response = (HttpServletResponse) context.getExternalContext().getResponse();
        try {
        
        //check if redirectUrl is to this website
            if(redirectionUrl.startsWith("http://localhost:8080/")){
                
                response.sendRedirect(redirectionUrl);
            }

        } catch (IOException ex) {
            Logger.getLogger(NewsController.class.getName()).log(Level.SEVERE, null, ex);
        }
        return;

    }
    
```


## Verifikation

🤠 Der Codeausschnitt zeigt, dass ich nur mit wenig Code das Problem lösen konnte und ich somit das Problem verstanden habe, wie auch wie ich es lösen kann.

# Reflektion zum Arbeitsprozess

👍 Das lief gut im projekt:

* geringer aufwand
* die überprüfung geschiet sicher auf dem Server

👎 Das lief nicht gut:

*Bei meiner lösung muss man immer wenn sich die Domain ändert, den Code auch ändern

🤗 verbessern kann ich beim nächsten mal, dass sich der Code immer der aktuellen Domain anpasst.


