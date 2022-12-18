![Logo](https://www.internetmatters.org/wp-content/uploads/2022/05/bereal-image.png)

# BeReal.

Dieses Paket bietet die Möglichkeit, mit BeReal. über NodeJS zu kommunizieren.

Sensible Informationen werden bereits bei jeder Anfrage herausgefiltert und nur die wichtigen
Informationen wiedergegeben.

❗Da ich dieses mal die Anfragen über meinen Server mache besteht die Möglichkeit, dass es zu zeitlichen Ausfällen kommen kann.

# Update 14.12.2022

-   Verfügbarkeit des Dienstes erhöht ✅

# Update 15.12.2022

-   Anpassung der API Endpunkte die fehlerhafte Ergebnisse zurückgeliefert haben. ✅

## Installation

Zum installieren des Paketes, nutze folgenden Befehl:

```bash
  npm install bereal
```

## Features

-   Anmelden mit SMS
-   OTP verifizieren
-   Access und Refreshtoken erneuern
-   Eigene Profilinformationen abrufen
-   Profilinformationen von anderen per ID abrufen ( Durch sensible Inhalte gefiltert )
-   Profilinformationen von anderen per Telefonnummer abrufen ( Durch sensible Inhalte gefiltert )
-   Eigene Freunde auflisten
-   Empfohlene Freunde auflisten
-   Personen anzeigen, denen Ihr eine Freundschaftsanfrage gesendet habt
-   Personen anzeigen, von denen Ihr eine Freundschaftsanfrage erhalten habt
-   Personen über Ihre ID als Freunde hinzufügen
-   Freundes Feed anzeigen ( Durch sensible Inhalte gefiltert )
-   Discovery Feed anzeigen ( Durch sensible Inhalte gefiltert )
-   Memories Feed anzeigen

## Beispiel aller Funktionen

```javascript
import BeReal from "bereal";

const beReal = new BeReal();

const phone = await beReal.loginWithSMS("<phoneNumber>");

const verify = await beReal.verifySMS("<code>", "<sessionInfo>");

const tokens = await beReal.refreshToken("<refreshToken>");

const ownProfile = await beReal.getOwnProfile("<accessToken>");

const profileByID = await beReal.getProfileByID("<accessToken>", "<profileID>");

const profileByPhoneNumber = await beReal.getProfileByPhoneNumber("<accessToken>", "<phoneNumber>");

const ownFriends = await beReal.getFriends("<accessToken>");

const suggestedFriends = await beReal.getSuggestedFriends("<accessToken>");

const sendedRequests = await beReal.getSendedFriendRequests("<accessToken>");

const receivedRequests = await beReal.getReceivedFriendRequests("<accessToken>");

const sendFriendRequest = await beReal.addFriend("<accessToken>", "<profileID>");

const friendsFeed = await beReal.getFriendsFeed("<accessToken>");

const discoverFeed = await beReal.getDiscoverFeed("<accessToken>");

const memoriesFeed = await beReal.getMemoriesFeed("<accessToken>");
```

## FAQ

#### 📱Wie muss ich die Telefonnummer angeben?

Die Telefonnummer muss mit dem Landescode beginnen, z.B. +49123456789

#### 📄 Woher bekomme ich die sessionInfo?

Die sessionInfo erhält man aus der loginWithSMS Methode

#### 📄 Woher bekomme ich den refreshToken?

Den refreshToken erhält man aus der verifySMS Methode

#### 📄 Woher bekomme ich den accessToken?

Den accessToken erhält man aus der refreshToken Methode

#### 📄 Woher bekomme ich die profileID eines anderen Benutzers?

Die profileID erhält man entweder vom freunde oder discover Feed
