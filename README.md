<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CT Express - Boutique Premium</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;800&display=swap" rel="stylesheet">
    <style>
        * { box-sizing: border-box; margin: 0; padding: 0; }
        body { background-color: #0a0a0a; color: #ffffff; font-family: 'Poppins', sans-serif; padding-bottom: 50px; }
           .header { background: rgba(20, 20, 20, 0.8); backdrop-filter: blur(15px); text-align: center; padding: 25px 20px; border-bottom: 1px solid rgba(255, 102, 0, 0.2); position: sticky; top: 0; z-index: 100; }
        .header h1 { font-size: 32px; font-weight: 800; background: linear-gradient(90deg, #FF6600, #FFaa00); -webkit-background-clip: text; -webkit-text-fill-color: transparent; margin-bottom: 5px; }
        .header p { font-size: 13px; color: #888; text-transform: uppercase; letter-spacing: 2px; }
        
   .container { padding: 20px; max-width: 500px; margin: auto; }
        
  .pro-section { background: #141414; border-radius: 20px; padding: 25px; margin-bottom: 30px; border: 1px solid #222; }
        .pro-section h2 { font-size: 18px; margin-bottom: 15px; color: #FF6600; }
        
  .track-input { width: 100%; padding: 15px; background: #0a0a0a; border: 1px solid #333; color: white; border-radius: 10px; font-family: 'Poppins', sans-serif; margin-bottom: 15px; font-size: 16px; }
        
  .product-card { background: #141414; border-radius: 24px; overflow: hidden; margin-bottom: 30px; box-shadow: 0 15px 35px rgba(0,0,0,0.6); border: 1px solid #222; }
        .product-image { width: 100%; height: 280px; object-fit: cover; border-bottom: 1px solid #222; }
        .product-info { padding: 25px; }
        .product-title { font-size: 22px; font-weight: 600; margin-bottom: 12px; }
        .badge { display: inline-block; background: rgba(255, 255, 255, 0.05); padding: 6px 12px; border-radius: 20px; font-size: 12px; color: #bbb; margin-bottom: 15px; border: 1px solid rgba(255, 255, 255, 0.1); }
        .price-promo { color: #FF6600; font-size: 24px; font-weight: 800; margin-bottom: 20px; }
        
   .button { background: linear-gradient(90deg, #FF6600, #e65c00); color: white; padding: 16px; border: none; width: 100%; border-radius: 14px; font-size: 16px; font-weight: 600; text-transform: uppercase; letter-spacing: 1px; cursor: pointer; }
    </style>
</head>
<body>
    <div class="header">
        <h1>CT EXPRESS</h1>
        <p>Tech & Lifestyle</p>
    </div>
      <div class="container">
        <!-- Service Coursier -->
        <div class="pro-section" style="border: 1px solid #FFaa00;">
            <h2 style="color: #FFaa00;">🛵 Service Coursier Rapide</h2>
            <p style="color: #ccc; font-size: 13px; margin-bottom: 15px;">Besoin d'un livreur pour une course personnelle ? Réservez notre service indépendant.</p>
            <input type="text" id="quartierDepart" class="track-input" placeholder="Départ (ex: Ouaga 2000)">
            <input type="text" id="quartierArrivee" class="track-input" placeholder="Arrivée (ex: Kalgondé)">
            <button class="button" style="background: #222; color: #FFaa00; border: 1px solid #FFaa00;" onclick="reserverLivreur()">Commander un coursier</button>
        </div><!-- Section Suivi -->
        <div class="pro-section">
            <h2>📦 Suivi de Commande</h2>
            <input type="text" id="codeSuivi" class="track-input" placeholder="Entrez votre numéro de suivi">
            <button class="button" onclick="verifierColis()">Suivre mon colis</button>
        </div> <!-- Section Produits -->     <div class="product-card">
            <img src="https://images.unsplash.com/photo-1616348436168-de43ad0db179?auto=format&fit=crop&w=600&q=80" alt="iPhone" class="product-image">
            <div class="product-info">
                <div class="product-title">iPhone 14 Pro Max 256Go</div>
                <div class="badge">📦 Précommande Asie</div>
                <div class="price-promo">239 000 FCFA</div>
                <button class="button" onclick="ajouterAuPanier('iPhone 14 Pro Max 256Go à 239000 FCFA')">Précommander</button>
            </div>
        </div>
    </div>
  <script>
        function ajouterAuPanier(nomDuProduit) {
            var numeroWhatsApp = "22657863237"; 
            var message = "Salut CT Express ! 🚀 Je souhaite commander : " + nomDuProduit;
            window.open("https://wa.me/" + numeroWhatsApp + "?text=" + encodeURIComponent(message), "_blank");
        }
        function reserverLivreur() {
            var depart = document.getElementById("quartierDepart").value;
            var arrivee = document.getElementById("quartierArrivee").value;
            if(depart === "" || arrivee === "") {
                alert("Veuillez préciser les quartiers de départ et d'arrivée.");
                return;
            }
            var numeroWhatsApp = "22657863237"; 
            var message = "Salut CT Express ! 🛵 J'ai besoin d'un livreur.\n📍 Départ : " + depart + "\n🎯 Arrivée : " + arrivee + "\nQuel est le tarif ?";
            window.open("https://wa.me/" + numeroWhatsApp + "?text=" + encodeURIComponent(message), "_blank");
        }
        function verifierColis() {
            var code = document.getElementById("codeSuivi").value;
            if(code === "") { alert("Entrez un numéro de suivi."); }
            else { alert("Suivi " + code + " : Votre article est en transit international."); }
        }
    </script>
</body>
</html>
