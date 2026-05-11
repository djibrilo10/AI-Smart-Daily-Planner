AI Smart Daily Planner (AWS Serverless Project)
- Description

AI Smart Daily Planner est une application cloud serverless qui génère automatiquement des tâches quotidiennes à partir d’un objectif utilisateur.

Le système utilise des services AWS pour créer une architecture scalable et automatisée.

- Fonctionnalités
Génération automatique de tâches quotidiennes
Priorisation des tâches (High / Medium / Low)
Stockage des données utilisateur
API REST serverless
Architecture cloud scalable
- Architecture AWS
User
 ↓
API Gateway
 ↓
AWS Lambda (TaskProcessor)
 ↓
DynamoDB (Tasks Table)
- Services AWS utilisés
Amazon Web Services API Gateway
Amazon Web Services Lambda
Amazon Web Services DynamoDB
Amazon Web Services CloudWatch (logs)
IAM (permissions)
- Fonctionnement
L’utilisateur envoie un objectif via API
API Gateway transmet la requête à Lambda
Lambda génère automatiquement des tâches
Les tâches sont stockées dans DynamoDB
L’API retourne les résultats en JSON
📡 Exemple d’appel API
Endpoint
POST https://rmus5ltdzf.execute-api.us-east-2.amazonaws.com/dev/generateTasks
Body
{
  "goal": "Become AWS Solutions Architect"
}
Réponse
{
  "message": "Tasks generated successfully",
  "tasks": [
    {
      "task": "Study AWS IAM",
      "priority": "High"
    }
  ]
}
- Comment tester
PowerShell
Invoke-RestMethod -Method POST `
-Uri "https://rmus5ltdzf.execute-api.us-east-2.amazonaws.com/dev/generateTasks" `
-ContentType "application/json" `
-Body '{"goal":"AWS Architect"}'
- Résultat
API fonctionnelle
tâches générées automatiquement
stockage dans DynamoDB
logs visibles dans CloudWatch
 -Points techniques importants
Architecture serverless (no infrastructure management)
Backend event-driven
API REST scalable
NoSQL database (DynamoDB)
Separation of concerns (API / Logic / Data)
 -Objectif du projet

Démontrer une architecture cloud AWS complète et moderne pour automatiser la génération de tâches intelligentes.