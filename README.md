
# Rapport

**Skriv din rapport här!**

_Du kan ta bort all text som finns sedan tidigare_.

## Följande grundsyn gäller dugga-svar:

- Ett kortfattat svar är att föredra. Svar som är längre än en sida text (skärmdumpar och programkod exkluderat) är onödigt långt.
- Svaret skall ha minst en snutt programkod.
- Svaret skall inkludera en kort övergripande förklarande text som redogör för vad respektive snutt programkod gör eller som svarar på annan teorifråga.
- Svaret skall ha minst en skärmdump. Skärmdumpar skall illustrera exekvering av relevant programkod. Eventuell text i skärmdumpar måste vara läsbar.
- I de fall detta efterfrågas, dela upp delar av ditt svar i för- och nackdelar. Dina för- respektive nackdelar skall vara i form av punktlistor med kortare stycken (3-4 meningar).

Programkod ska se ut som exemplet nedan. Koden måste vara korrekt indenterad då den blir lättare att läsa vilket gör det lättare att hitta syntaktiska fel.

```
function errorCallback(error) {
    switch(error.code) {README.mdREADME.md
        case error.PERMISSION_DENIED:
            // Geolocation API stöds inte, gör något
            break;
        case error.POSITION_UNAVAILABLE:
            // Misslyckat positionsanrop, gör något
            break;
        case error.UNKNOWN_ERROR:
            // Okänt fel, gör något
            break;
    }
}
```
Ändrat namn på appen.
```
<string name="app_name">a19clasvApp</string>
```
Gett tillstånd att använda internet.
```
<uses-permission android:name="android.permission.INTERNET"/>
```
Skapat ett WebView element med ID:et "my_webview".
```
<WebView
        android:id="@+id/my_webview"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello World!"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
```
Importerat det jag behöver för WebView och WebViewClient.
```
import android.webkit.WebView;
import android.webkit.WebViewClient;
```
Skapat en privat WebView.
```
    private WebView myWebView;
```
Satte en WebViewClient på my_webview
```
        myWebView = findViewById(R.id.my_webview);
        myWebView.setWebViewClient(new WebViewClient());
```
Aktiverade Javascript.
```
        myWebView.getSettings().setJavaScriptEnabled(true);
```
Visar den yttre hemsidan https://www.his.se/ i showExternalWebPage().
```
    public void showExternalWebPage(){
        myWebView.loadUrl("https://www.his.se/");
    }
```
Headern "This is the internal web page" i about.html.
```
<html>
<body>
<h1>This is the internal web page</h1>
</body>
</html>
```
Visar den inre hemsidan about.html i showInternalWebPage().
```
    public void showInternalWebPage(){
        myWebView.loadUrl("file:///android_asset/about.html");
    }
```
Kallar på showExternalWebPage() om du väljer "External Web Page".
```
        if (id == R.id.action_external_web) {
            showExternalWebPage();
            return true;
        }
```
Kallar på showInternalWebPage() om du väljer "Internal Web Page".
```
        if (id == R.id.action_internal_web) {
            showInternalWebPage();
            return true;
        }
```
Den yttre webbsidan:
![](Screenshot_20220408_144821.png)
Den inre webbsidan:
![](Screenshot_20220408_145119.png)
