# Lab_1_MobileSecurity

---

## **Étape 1 — Récupération de Mobexler (OVA)**

- L’image **Mobexler.ova** a été récupérée depuis la source officielle (Google Drive).
- *(Facultatif)* Un contrôle **SHA256** a été fait quand la valeur était disponible.
- **OK :** le fichier est bien là et prêt à être importé.

![Étape 1](pts/1.png)

![](pts/aftrStp.png)

---

## **Étape 3 — Démarrage initial + ouverture de session**

- Mobexler a été lancé pour la première fois.
- Accès effectué avec le mot de passe : **mobexler**.
- Si un identifiant était demandé : test avec **mobexler** ou l’utilisateur affiché sur l’écran.
- **OK :** arrivée sur le **bureau** ou accès au **terminal**.

---

## **Étape 4 — Contrôle réseau (vérification rapide)**

### **1) Interfaces + adresses IP**
Objectif : repérer l’interface **NAT** et l’interface **Host-Only**.

![](pts/ipA.png)

### **2) Route par défaut**
Objectif : vérifier qu’une passerelle par défaut existe (sortie Internet via NAT).

![](pts/iproute.png)

### **3) Test Internet (IP puis DNS)**
Objectif : valider la connectivité + la résolution de noms.

![](pts/Tst.png)

- **OK attendu :** ping vers une IP + ping vers un nom de domaine.

---

## **Étape 5 — Snapshot de base “CLEAN” (VirtualBox)**

- Un snapshot a été enregistré après validation du démarrage et du réseau.
- Chemin : **VirtualBox → VM → Snapshots → Take**
- Nom : **CLEAN_BASELINE_TP1**
- Description : **Import OK, NAT+HostOnly OK, boot OK, prêt ADB**
- **OK :** le snapshot apparaît dans la liste (restauration possible si besoin).

![](pts/snapShot.png)

---

## **Étape 6 — Préparation Android (USB sur VirtualBox)**

### **1) Activer le mode développeur + USB debugging**
- Paramètres → À propos → **Build number x7**
- Options développeur → **USB debugging ON**

### **2) Passer l’USB à la VM**
- VirtualBox : **Devices → USB → sélectionner le téléphone**

### **3) Vérifier la détection ADB**
![](pts/Adb1.png)

- **OK attendu :** le téléphone est listé en **device**.

### **Dépannage**
- **unauthorized** : accepter la demande RSA sur le téléphone
- si rien n’apparaît : vérifier USB puis relancer ADB :

![](pts/Adb2.png)
