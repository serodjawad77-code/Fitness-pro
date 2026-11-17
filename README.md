# Fitness Pro

Application web progressive (PWA), mobile-first et en français, connectée au projet Supabase existant.

## Fonctionnalités
- Création de compte et connexion par e-mail.
- Catalogue des programmes publiés et consultation des exercices.
- Enregistrement des séances et historique personnel.
- Accès Premium à 2 000 FCFA par mois.
- Paiements Monerails en mode test : MTN MoMo, Moov Money et Celtiis Cash.
- Espace d'administration réservé au rôle admin.

## Publication
Le workflow GitHub Actions `.github/workflows/deploy.yml` publie le site sur GitHub Pages à chaque mise à jour de `main`. Dans les paramètres du dépôt, vérifier que Pages utilise GitHub Actions.

## Backend
Projet Supabase : `iumgcbvuikzbateldytm`. La clé présente dans `supabase-config.js` est une clé publique publishable. Aucune clé secrète ne doit être ajoutée au dépôt.

## Paiements
Les paiements restent en mode test tant que les secrets marchands ne sont pas configurés dans Supabase Edge Functions > Secrets : `MONERAIL_KEY`, `MONERAIL_WEBHOOK_SECRET` et `MONERAIL_ENV=test`.

Webhook à enregistrer chez Monerails :
`https://iumgcbvuikzbateldytm.supabase.co/functions/v1/fitness-pro-monerails-webhook`
Événements : `collection.*`.

Numéros de test : `22900000001` succès, `22900000002` en attente, `22900000003` échec. Aucun vrai portefeuille n'est débité en mode test. Ne jamais demander ni saisir de PIN Mobile Money dans l'application.

## Avant ouverture au public
- Tester l'inscription, la connexion et les séances sur appareils réels.
- Configurer les secrets marchands en privé et réaliser les tests Monerails.
- Vérifier les URL de redirection Auth Supabase et les pages légales.
- Le renouvellement Premium est manuel : pas de débit récurrent automatique.
