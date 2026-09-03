# MFA og Conditional Access

## Formål

Formålet var å konfigurere og teste multifaktorautentisering i Microsoft Entra ID, samt bruke Conditional Access for å forstå hvordan MFA kan håndheves.

## MFA-pilotgruppe

En Security Group kalt `SG-MFA-Pilot` ble opprettet.

Testbruker:

- Anna Hansen

## Conditional Access

En Conditional Access-policy ble opprettet:

`CA-Require-MFA-Pilot`

Policyen ble konfigurert med:

- Users: `SG-MFA-Pilot`
- Target resources: All resources
- Grant control: Require multifactor authentication
- Policy state: Report-only

Policyen ble validert med Conditional Access-verktøyet `What If`.

Testen bekreftet at policyen ville gjelde for Anna Hansen.

## Microsoft Authenticator

Anna Hansen registrerte Microsoft Authenticator som MFA-metode.

Authenticator ble brukt som andre faktor ved innlogging.

## MFA support scenario

Det ble simulert at brukeren hadde fått ny telefon og måtte registrere MFA på nytt.

I Entra ID ble funksjonen:

`Require re-register multifactor authentication`

brukt.

Eksisterende økt ble avsluttet, og brukeren registrerte Microsoft Authenticator på nytt ved neste innlogging.

## Verifisering

Etter nyregistrering kunne brukeren logge inn med:

1. Brukernavn og passord
2. Microsoft Authenticator

MFA fungerte som forventet.

## Sikkerhet

QR-koder, passord, recovery codes og andre autentiseringshemmeligheter ble ikke lagret i prosjektets dokumentasjon.
