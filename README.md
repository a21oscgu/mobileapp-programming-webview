
# Rapport

**En app har skapats som heter "Världens bästa app". Appen har fått tillgång till internet i "AndroidManifest.xml". En webview med id:"my_webview" skapades i "content_main.xml". En variabel skapades sedan i Java och blev kopplad med den view som har id:"my_webview". Javascript aktiverades sedan för att tillåta JavaScript. WebViewClient lades också in för att undvika användningen av Chrome vid användningen av extern webbsida (se kodsnutt 1).**
```
myWebView.getSettings().setJavaScriptEnabled(true);//Javascript is not enabled by default
myWebView.setWebViewClient(new WebViewClient());// We want to open this in the app.
```
**Efter det skapades en (intern) sida i HTML som heter "page1.html". Sidan lades in i mappen assets som jag också skapade. Efter det laddades den externa och den interna sidan in i Java-koden (se kodsnutt 2).**
```
public void showExternalWebPage(){
        myWebView.loadUrl("https://www.his.se/");
    }

    public void showInternalWebPage(){
        myWebView.loadUrl("file:///android_asset/page1.html");
    }
```
**Till slut lades kod in som kallar på dessa olika funktioner (som syns i kodsnutt 2) när användaren interagerar med dropdown-menyn.
Här är ett skärmklipp på den externa sidan i min emulator:**
![](Screenshot_external.png)
**Här är ett skärmklipp på den interna sidan i min emulator:**
![](Screenshot_internal.png)