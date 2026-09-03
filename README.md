# microsoft-365-entra-id-support-lab
Praktisk Microsoft 365- og Entra ID-lab med brukere, grupper, lisenser, MFA, Conditional Access, adminroller, onboarding/offboarding og Exchange shared mailbox.

## Om prosjektet

Dette er et praktisk homelab-prosjekt bygget for å utvikle ferdigheter innen Microsoft 365, Microsoft Entra ID og moderne IT-support.

Labmiljøet simulerer vanlige administrative oppgaver og supportsaker i et Microsoft 365-miljø, blant annet brukeradministrasjon, lisensiering, grupper, MFA, Conditional Access, delegerte administratorroller, onboarding/offboarding og Exchange Online.

## Teknologier og tjenester

- Microsoft 365 Business Premium
- Microsoft Entra ID
- Microsoft 365 Admin Center
- Conditional Access
- Microsoft Authenticator / MFA
- Entra Security Groups
- Microsoft Exchange Online
- Outlook on the web
- Shared Mailboxes

## Labmiljø

- Tenant: `CloudSupportLab`
- Standarddomene: `CloudSupportLab.onmicrosoft.com`
- Microsoft 365 Business Premium testmiljø
- Microsoft Entra ID
- Separate vanlige bruker- og administratorkontoer

## Brukere og lisenser

Det ble opprettet testbrukere for flere avdelinger:

| Bruker | Avdeling |
|---|---|
| Anna Hansen | HR |
| Martin Berg | IT |
| Sara Ali | Finance |
| Jonas Larsen | Sales |

Brukerne ble tildelt Microsoft 365 Business Premium-lisenser og konfigurert uten administratorrettigheter.

## Microsoft Entra Security Groups

Følgende Security Groups ble opprettet:

| Gruppe | Formål |
|---|---|
| `SG-HR` | HR-brukere |
| `SG-IT` | IT-brukere |
| `SG-Finance` | Finance-brukere |
| `SG-Sales` | Sales-brukere |
| `SG-MFA-Pilot` | Pilotgruppe for MFA-testing |

Gruppene bruker `Assigned` membership og kan brukes til tilgangsstyring og policy-targeting.

## MFA og Conditional Access

En Conditional Access-policy ble konfigurert:

`CA-Require-MFA-Pilot`

Policyen:

- gjelder `SG-MFA-Pilot`
- gjelder alle ressurser
- krever multifaktorautentisering
- ble testet i `Report-only`
- ble validert med Conditional Access `What If`

Microsoft Authenticator ble brukt som MFA-metode.

Det ble også testet hvordan IT-support kan kreve at en bruker registrerer MFA på nytt etter for eksempel bytte av telefon.

## Adminroller og Least Privilege

En separat administratorkonto ble opprettet:

`martin.berg.admin@CloudSupportLab.onmicrosoft.com`

Kontoen ble tildelt:

- Helpdesk Administrator
- Authentication Administrator

Kontoen ble ikke tildelt Global Administrator.

Dette demonstrerer prinsippet om least privilege, der administratorer kun får rettighetene som er nødvendige for arbeidsoppgavene.

## Onboarding og Offboarding

Det ble simulert en komplett bruker-livssyklus.

### Onboarding

En ny HR-bruker ble:

- opprettet i Microsoft 365
- tildelt Business Premium-lisens
- konfigurert med riktig profilinformasjon
- lagt til i `SG-HR`
- konfigurert med passordbytte ved første innlogging
- testet med vellykket Microsoft 365-innlogging

### Offboarding

Ved avslutning ble:

- brukerens innlogging blokkert
- eksisterende sessions tilbakekalt
- Security Group-medlemskap fjernet
- Microsoft 365-lisensen fjernet
- innlogging testet og bekreftet blokkert

## Exchange Online – Shared Mailbox

En delt postboks ble opprettet:

`HR Support`

Adresse:

`hrsupport@CloudSupportLab.onmicrosoft.com`

Anna Hansen fikk:

- Read and manage / Full Access
- Send As

Tilgangen ble testet i Outlook på web.

En testmelding ble sendt med `HR Support` som avsender for å verifisere `Send As`.

## IT-supporttickets

Tre realistiske supportsaker ble dokumentert:

### Ticket 01 – MFA / ny telefon

Brukeren kunne ikke lenger bruke eksisterende Microsoft Authenticator etter bytte av telefon.

MFA ble registrert på nytt og innlogging ble verifisert.

### Ticket 02 – Onboarding av ny ansatt

En ny ansatt ble opprettet, lisensiert, lagt i riktig Security Group og testet med vellykket innlogging.

### Ticket 03 – Offboarding av bruker

Tilgang ble blokkert, sessions tilbakekalt, grupper og lisens fjernet, og det ble verifisert at brukeren ikke lenger kunne logge inn.

## Dokumentasjon

Mer detaljert dokumentasjon finnes i:

- [`docs/`](docs/) – konfigurasjon og teknisk dokumentasjon
- [`tickets/`](tickets/) – realistiske IT-supportscenarier
- [`screenshots/`](screenshots/) – skjermbilder fra labmiljøet

## Hva jeg har lært

Gjennom prosjektet har jeg fått praktisk erfaring med:

- Microsoft 365 brukeradministrasjon
- Microsoft Entra ID
- opprettelse og administrasjon av brukere
- lisensadministrasjon
- Security Groups
- multifaktorautentisering
- Microsoft Authenticator
- Conditional Access
- What If-testing
- Authentication methods
- delegerte administratorroller
- least privilege
- onboarding
- offboarding
- blokkering av brukerinnlogging
- session revocation
- Exchange Online
- Shared Mailboxes
- Full Access og Send As
- dokumentasjon av IT-supportsaker

## Sikkerhet

Prosjektet bruker kun fiktive testbrukere og labdata.

Passord, MFA-QR-koder, recovery codes, betalingsinformasjon og andre autentiseringshemmeligheter er ikke publisert.
