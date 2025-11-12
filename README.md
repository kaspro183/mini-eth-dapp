# Mini Ethereum dApp — Counter (Solidity + Frontend ethers.js)

Mini dApp **Ethereum Sepolia** prête à publier sur GitHub et à utiliser avec **MetaMask**.
- Smart contract : `Counter.sol` (incrémente/décrémente une valeur)
- Frontend simple (HTML + JS) utilisant **ethers.js** et **MetaMask**
- Déploiement possible via **Remix** ou **Hardhat** (optionnel)

> ⚠️ Pour Talent Protocol, les **commits GitHub** suffisent. Le déploiement est **optionnel**.

## Structure
```
mini-eth-dapp/
├── contracts/Counter.sol
├── scripts/deploy.js
├── hardhat.config.js
├── package.json
└── frontend/
    ├── index.html
    └── app.js
```

## Utilisation rapide (sans terminal)
1. **Déployer le contrat avec Remix** (facultatif mais nécessaire si vous voulez tester la dApp) :
   - Ouvrir https://remix.ethereum.org
   - Créer `Counter.sol` et coller le contenu du fichier `contracts/Counter.sol`
   - Compiler en 0.8.20
   - Dans **Deploy & Run**, sélectionner **Injected Provider - MetaMask** (réseau **Sepolia**)
   - Déployer → récupérer l'**adresse du contrat**
2. **Configurer le frontend :**
   - Ouvrir `frontend/app.js`
   - Remplacer `const CONTRACT_ADDRESS = "0xYourDeployedAddress"` par votre adresse déployée
3. **Lancer le frontend :**
   - Ouvrir `frontend/index.html` dans votre navigateur (MetaMask installé)
   - Se connecter avec MetaMask (réseau **Sepolia**)
   - Utiliser les boutons **get / increment / decrement**

## Déploiement via Hardhat (optionnel)
```bash
npm i
npx hardhat compile
# variables d'env requises si vous déployez : SEPOLIA_RPC_URL et PRIVATE_KEY
SEPOLIA_RPC_URL="https://sepolia.infura.io/v3/..." PRIVATE_KEY="0xabc..." npx hardhat run scripts/deploy.js --network sepolia
```

---

### Notes
- `app.js` embarque une ABI minimale du contrat `Counter`.
- Pour publier le frontend en ligne, vous pouvez utiliser **GitHub Pages** : placez le dossier `frontend/` dans un repo public et activez Pages.
