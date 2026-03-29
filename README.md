# Boutique Diayma
https://drive.google.com/file/d/1WB9Rz9wgRRKOzSRbeDT5EMLgJpaTcgmn/view?usp=sharing

Projet : BoutiqueDiayma2025 — TP .NET
Ce dépôt contient les travaux dirigés réalisés dans le cadre du cours .NET à l'École Supérieure Polytechnique (ESP) de l'UCAD pour l'année 2025/2026.

1. Informations Générales
Étudiant : Ousmane NDIOUR
Établissement : ESP / UCAD 
Formation : DIT 2 INFO

2. Analyse de la Solution
Projets inclus : La solution contient le projet principal Diayma (Namespace : P2FixAnAppDotNetCode).
Version du SDK .NET : Le projet utilise le framework cible .NET Core 2.0 (netcoreapp2.0).

3. Correction des Bugs Identifiés (Tâche 6)
J'ai identifié et corrigé les deux bugs suivants dans l'application:

Bug 1 : Support de la langue espagnole
Fichier : Startup.cs
Problème : L'espagnol n'était pas inclus dans la liste supportedCultures.
Correction : Ajout de new CultureInfo("es") dans la configuration des services.

Bug 2 : Calcul erroné du total du panier
Fichier : Models/Cart.cs
Méthode : GetTotalValue()
Étape,Namespace,Classe,Méthode,Ligne,Mode de débogage
1,P2FixAnAppDotNetCode,Startup,Startup(IConfiguration),20,F10 (Pas à pas principal)
2,P2FixAnAppDotNetCode.Controllers,ProductController,ProductController(...),15,F10 (Pas à pas principal)
3,P2FixAnAppDotNetCode.Components,CartSummaryViewComponent,CartSummaryViewComponent(ICart),12,Shift+F11 (Pas à pas sortant)
4,P2FixAnAppDotNetCode.Controllers,CartController,CartController(...),15,F10 (Pas à pas principal)
Problème : Le calcul ignorait la quantité (Sum(x => x.Product.Price)).

Correction : Modification de la logique pour multiplier le prix par la quantité : Sum(x => x.Product.Price * x.Quantity).
