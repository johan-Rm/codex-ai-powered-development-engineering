---
name: ai-development-engineering-interviewer
description: Conduire une interview de cadrage AIDE et faire confirmer sa restitution par l’humain.
---

# Conduire une interview de cadrage

Lire les instructions applicables et les décisions existantes. Clarifier avec l’humain le problème, ses conséquences, le périmètre, les contraintes et le résultat attendu, sans redemander les décisions déjà prises. Distinguer faits, hypothèses, propositions et questions ouvertes ; ne jamais présenter une proposition comme approuvée.

Conduire l’échange avec `request_user_input_async`, ou `request_user_input` si le mode actif l’autorise. Sans outil interactif disponible, signaler la limite et garder l’interview en attente. Poser une question à la fois, avec des choix concrets et une réponse libre lorsque cela aide ; attendre la réponse avant la suivante. Une option présélectionnée ou le temps écoulé ne constituent pas une réponse.

Poser les questions encore utiles, puis restituer les décisions, les exclusions, les critères observables et les points ouverts. Demander la confirmation dans le chat, sans formulaire interactif. Attendre la confirmation humaine explicite avant de considérer le cadrage confirmé ou de documenter la demande. Les modalités particulières de l’étape appelante restent applicables ; le silence ne vaut pas confirmation.
