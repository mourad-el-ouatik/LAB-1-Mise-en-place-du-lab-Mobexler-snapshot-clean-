# ⭐ LAB-01 | Mise en place du Lab (Mobexler + Snapshot Clean)

Une mise en place complète de l'environnement de test mobile **Mobexler** dans une machine virtuelle (VMware/VirtualBox), incluant l'import de l'OVA, la configuration réseau, la connexion, et la création d'un snapshot propre — prêt pour les labs de sécurité Android.

---

## ✨ Fonctionnalités de l'environnement

- 📦 **Mobexler OVA** — machine virtuelle préconfigurée pour le pentesting mobile
- 🔐 **Vérification d'intégrité** — contrôle du hash de l'OVA téléchargée
- 🌐 **Configuration réseau dual-adapter** — NAT (Internet) + Host-Only (communication hôte/VM)
- 📱 **Cible Android embarquée** — émulateur Android intégré à Mobexler
- 💾 **Snapshot "CLEAN"** — point de restauration propre avant toute manipulation
- 🔄 **Restauration rapide** — retour à l'état initial à tout moment via le snapshot

---

## 🛠️ Stack technique

| Composant | Technologie |
|---|---|
| Machine virtuelle | VMware Workstation / VirtualBox |
| Image VM | Mobexler (format `.ova`) |
| Réseau Adapter 1 | NAT |
| Réseau Adapter 2 | Host-Only Adapter |
| Cible mobile | Android (émulateur embarqué) |
| Sauvegarde | Snapshot VM |

---

## 📁 Architecture de l'environnement

```bash
Environnement Mobexler
├── VM Mobexler
│   ├── Adapter 1 (NAT)              # Accès Internet
│   ├── Adapter 2 (Host-Only)        # Communication avec la machine hôte
│   ├── Émulateur Android            # Cible des tests de sécurité
│   └── Outils de pentest mobile     # Frida, ADB, Burp, etc.
└── Snapshot "CLEAN"                 # État propre avant manipulation
```

---

## 📊 Étapes du laboratoire

| Étape | Description |
|---|---|
| Étape 1 | Télécharger Mobexler (OVA) et vérifier l'intégrité |
| Étape 2 | Importer l'OVA dans VirtualBox / VMware |
| Étape 3 | Premier démarrage + connexion |
| Étape 4 | Vérifier le réseau (IPs, route, Internet) |
| Étape 5 | Créer le snapshot "CLEAN" |
| Étape 6 | Préparer la cible Android |

---

## 🔄 Fonctionnement détaillé

### Étape 1 — Télécharger Mobexler (OVA) et tracer le téléchargement

#### 1. Télécharger l'OVA

<img width="541" height="111" alt="image" src="https://github.com/user-attachments/assets/3d55718d-fcca-4e88-bb08-c9eb22d8b4e3" />

#### 2. Vérifier l'intégrité

<img width="878" height="179" alt="image" src="https://github.com/user-attachments/assets/8bd68c34-da6f-499e-b0ab-2c77479bdd96" />
<img width="880" height="64" alt="image" src="https://github.com/user-attachments/assets/7efa170d-6139-4f15-a2c9-6dfd701d628a" />

---

### Étape 2 — Importer l'OVA dans VirtualBox / VMware

- **VMware** → `File` → `Import Appliance`

<img width="387" height="334" alt="image" src="https://github.com/user-attachments/assets/5de61099-2c34-4187-b767-559b9029e2b5" />

- Sélectionner le fichier `.ova` → `Import`

<img width="808" height="103" alt="image" src="https://github.com/user-attachments/assets/7e794adc-fdd8-4b50-97cd-791a1c944a8b" />

- Après import : `VM` → `Settings` → `Network`
  - **Adapter 1 :** NAT
  - **Adapter 2 :** Host-Only Adapter

<img width="491" height="316" alt="image" src="https://github.com/user-attachments/assets/a9da1dfc-8d3b-4256-9379-5fe4fb8ab73f" />

---

### Étape 3 — Premier démarrage + connexion

<img width="813" height="331" alt="image" src="https://github.com/user-attachments/assets/6a55654e-788c-49b0-a484-4071c3878c67" />

---

### Étape 4 — Vérifier le réseau

#### 1. Vérifier les IPs

<img width="945" height="248" alt="image" src="https://github.com/user-attachments/assets/03a62a71-e244-4225-aa0b-3c37f5b6471d" />

#### 2. Vérifier la route par défaut

<img width="945" height="116" alt="image" src="https://github.com/user-attachments/assets/33306797-2e0d-4a05-94b4-bedbb8889de3" />

#### 3. Tester Internet

<img width="945" height="163" alt="image" src="https://github.com/user-attachments/assets/71e5edc4-9d16-4965-a480-23b073755acb" />

---

### Étape 5 — Créer le snapshot "CLEAN"

<img width="913" height="463" alt="image" src="https://github.com/user-attachments/assets/0a6ed969-f10c-498d-ab80-a0e77a0c0d0e" />

---

### Étape 6 — Préparer la cible Android

> 📸 **[IMAGE 12 — Capture : démarrage et état de la cible Android dans Mobexler]**

> 📸 **[IMAGE 13 — Capture : vérification de la connexion ADB à la cible Android]**

---

## 🎯 Objectif pédagogique

Ce laboratoire montre comment :

- Mettre en place un **environnement de pentest mobile** complet et reproductible
- Importer et configurer une **machine virtuelle OVA** dans VMware ou VirtualBox
- Configurer une **architecture réseau dual-adapter** pour isoler et connecter la VM
- Vérifier la **connectivité réseau** à chaque niveau (IP locale, route, Internet)
- Créer un **snapshot de référence "CLEAN"** pour restaurer l'environnement à tout moment
- Préparer une **cible Android** pour les labs de sécurité suivants

---

## 👨‍💻 Auteur

**Mourad EL OUATIK** | Réalisé dans le cadre du **Lab 01 — Programmation & Sécurité des Applications Mobile** | © ENSA Marrakech 2025/2026  
Encadré par : **Dr. Mohamed LACHGAR**
