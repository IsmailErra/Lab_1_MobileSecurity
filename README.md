# Lab_1_MobileSecurity

---

## **Étape 1 — Récupération de l’OVA Mobexler**

- L’image **Mobexler.ova** a été récupérée depuis la source officielle (:contentReference[oaicite:0]{index=0}).
- (Facultatif) Une vérification **SHA256** a été effectuée si la valeur de référence était disponible.
- **Validation :** fichier présent, prêt pour l’import.

![Étape 1](pts/1.png)

![](pts/aftrStp.png)

---

## **Étape 3 — Lancement et connexion**

- Démarrage de Mobexler.
- Authentification réalisée avec le mot de passe : **mobexler**.
- Si un identifiant était demandé : essai avec **mobexler** ou avec l’utilisateur affiché à l’écran.
- **Validation :** accès obtenu au **bureau** ou au **terminal**.

---

## **Étape 4 — Contrôle réseau (check rapide)**

### **Interfaces + adresses**
Objectif : vérifier que les interfaces attendues sont bien là (NAT / Host-Only).

![](pts/ipA.png)

### **Route par défaut**
Objectif : confirmer la présence d’une passerelle (sortie Internet).

![](pts/iproute.png)

### **Accès Internet (IP + nom de domaine)**
Objectif : valider la connectivité et la résolution DNS.

![](pts/Tst.png)

---

## **Étape 5 — Snapshot de référence “CLEAN” (VirtualBox)**

- Après vérification du boot et du réseau, création d’un snapshot de base.
- Menu : :contentReference[oaicite:1]{index=1} → **VM → Snapshots → Take**
- Nom : **CLEAN_BASELINE_TP1**
- Description : **Import OK, NAT+HostOnly OK, boot OK, prêt ADB**
- **Validation :** snapshot visible (restauration possible en cas de besoin).

![](pts/snapShot.png)

---

## **Étape 6 — Préparation Android (USB via VirtualBox)**

### **1) Activer USB debugging**
- Paramètres → À propos → **Build number x7**
- Options développeur → **USB debugging ON**

### **2) Connecter l’USB à la VM**
- VirtualBox : **Devices → USB → sélectionner le téléphone**

### **3) Vérifier ADB**
Contrôle de :contentReference[oaicite:2]{index=2} dans Mobexler :

![](pts/Adb1.png)

- **Attendu :** le téléphone apparaît en **device**.

### **En cas de souci**
- **unauthorized** : accepter la demande RSA sur le téléphone
- si rien n’apparaît : vérifier l’USB puis relancer ADB

![](pts/Adb2.png)
