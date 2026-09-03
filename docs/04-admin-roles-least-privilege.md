# Adminroller og Least Privilege

## Formål

Formålet var å opprette en separat administratorkonto for IT-support og gi kontoen kun de administrative rettighetene som er nødvendige for vanlige supportoppgaver.

## Administratorkonto

Følgende separat administratorkonto ble opprettet:

`martin.berg.admin@CloudSupportLab.onmicrosoft.com`

Martin Berg beholder samtidig sin vanlige brukerkonto:

`martin.berg@CloudSupportLab.onmicrosoft.com`

## Tildelte roller

Administratorkontoen ble tildelt:

- Authentication Administrator
- Helpdesk Administrator

Kontoen ble ikke tildelt Global Administrator.

## Least Privilege

Prinsippet om least privilege innebærer at en bruker kun skal ha de rettighetene som er nødvendige for arbeidsoppgavene.

Supportkontoen kan derfor utføre relevante bruker- og autentiseringsoppgaver uten å ha full kontroll over hele Microsoft 365- og Entra-miljøet.

## Verifisering

Administratorkontoen `martin.berg.admin@CloudSupportLab.onmicrosoft.com`
ble brukt til å logge inn i Microsoft Entra admin center.

Kontoen kunne åpne autentiseringsinnstillingene til en vanlig bruker og hadde tilgang til relevante supportfunksjoner som:

- Reset password
- Require re-register multifactor authentication
- Revoke sessions

Dette bekreftet at de delegerte rollene ga nødvendige supportrettigheter uten å gi Global Administrator-tilgang.
