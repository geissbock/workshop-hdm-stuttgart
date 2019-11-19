# Serverless-Workshop HdM Stuttgart

<!-- TOC depthFrom:2 depthTo:6 withLinks:1 updateOnSave:1 orderedList:1 -->

1. [Bei AWS einloggen](#bei-aws-einloggen)
2. [SQS konfigurieren](#sqs-konfigurieren)
3. [Lambda konfigurieren](#lambda-konfigurieren)
4. [Lambda testen](#lambda-testen)
5. [Nachricht in SQS abschicken](#nachricht-in-sqs-abschicken)
6. [Log-Daten in CloudWatch ansehen](#log-daten-in-cloudwatch-ansehen)

<!-- /TOC -->

## Bei AWS einloggen
* AWS-Benutzer sind bereits angelegt:
 * `hdm-workshop-01` bis `hdm-workshop-25`
 * Passwort jeweils `serverless-aws-2019-01` bis `serverless-aws-2019-25`
* Login auf https://853161928370.signin.aws.amazon.com/console

## SQS konfigurieren
* SQS-Konfiguration aufrufen: https://eu-central-1.console.aws.amazon.com/sqs/home?region=eu-central-1
* Sicherstellen, dass oben rechts `Frankfurt` ausgewählt ist
* `Create New Queue` anklicken und eigenen, eindeutigen Namen ausdenken (und merken 😉)

## Lambda konfigurieren
* Zu Lambdas wechseln: https://eu-central-1.console.aws.amazon.com/lambda/home?region=eu-central-1#/functions
* `Create function` anklicken und `Use a blueprint` auswählen
* In den Blueprints nach `sqs` suchen und den `sqs-poller` auswählen
* Eigenen, eindeutigen Namen für die Funktion und für die anzulegende Rolle angeben
* Unter `SQS Trigger` die zuvor angelegte, eigene Queue auswählen und Haken bei `Enable trigger` setzen
* `Create function` anklicken (dauert einen Moment)

## Lambda testen
* Oben rechts neben `Test` im Drop-Down `Select a test event` den Eintrag `Configure test events` auswählen
* Falls nicht automatisch passiert: `Amazon SQS` als Template auswählen und gerne z.B. den `body` editieren
* `Event name` eingeben und speichern
* Voller Zuversicht auf `Test` klicken, Augen zuhalten und das Beste hoffen

## Nachricht in SQS abschicken
* Wenn alles geklappt hat, den Reiter `Monitoring` auswählen und in einem neuen Tab nochmal zu SQS (https://eu-central-1.console.aws.amazon.com/sqs/home?region=eu-central-1) wechseln
* Eigene Queue auswählen, unter `Queue Actions` den Eintrag `Send a message` anklicken, Nachricht eingeben und abschicken

## Log-Daten in CloudWatch ansehen
* Immer mal wieder auf den Refresh-Button beim Monitoring der Lambda klicken und warten, bis ein weiterer Aufruf auftaucht
* Dann den Link in der Spalte `Log Stream` in einem neuen Tab öffnen
