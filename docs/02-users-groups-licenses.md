# Brukere, grupper og lisenser

## Brukere

Følgende testbrukere ble opprettet i Microsoft 365 og Microsoft Entra ID:

- Anna Hansen – HR
- Martin Berg – IT
- Sara Ali – Finance
- Jonas Larsen – Sales

Alle brukerne ble tildelt Microsoft 365 Business Premium-lisens og konfigurert som vanlige brukere uten administratorrettigheter.

## Security Groups

Følgende Microsoft Entra Security Groups ble opprettet:

| Gruppe     | Avdeling | Medlem       |
| ---------- | -------- | ------------ |
| SG-HR      | HR       | Anna Hansen  |
| SG-IT      | IT       | Martin Berg  |
| SG-Finance | Finance  | Sara Ali     |
| SG-Sales   | Sales    | Jonas Larsen |

Gruppene bruker medlemskapstypen `Assigned`.

Security Groups skal senere brukes til tilgangsstyring, policy-targeting og Intune.

## Forskjell fra Microsoft 365 Groups

Security Groups brukes hovedsakelig til tilgang og administrasjon.

Microsoft 365 Groups brukes mer til samarbeid og kan være knyttet til tjenester som Teams, SharePoint, felles mailbox og kalender.
