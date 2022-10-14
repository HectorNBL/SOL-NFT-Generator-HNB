# Solana-NFT-Generator
For more info on Solana NFT creation and deployment go here: [Solana NFTs: 0 to Mint](https://hackmd.io/@hnbl/solana_guide)

Generate images and json files with the current [Metaplex Metadata Standard](https://docs.metaplex.com/programs/token-metadata/token-standard)

This is originally the [Hashlips Art Generator](https://github.com/HashLips/hashlips_art_engine) and I've changed the config so that it fits with the current token standard for Solana.

Similar to the original Hashlips Generator you must have your layers folder with the name you want to give to each layer. Your system must also have yarn and node.

To use it:
1. Clone the repo. Open a terminal and enter </br> `git clone https://github.com/HectorNBL/Hector--Solana-NFT-Generator.git`
2. Open your IDE of choice. I used VSCode and open the folder containing the repo (the `Hector Solana NFTs` folder. It's nested within the Hector...Generator folder)
3. Paste you folders containing your layers into the Layers folder in the repo.
> **Note**
> The rarity is set with the name of each layer after the `#` symbol with a number. Example: Green#20.png.
4. Edit the content of the `config.js` file. Here are the parts you will want to change
```javascript
  const names = "NFT-Name"; 
  const description = "Collection-description";
  const image = "image.png";
  const animation_url = "Animation-URL";
  const external_url = "Collection-Website-URL";
```
5. Layer order and number of assets generted are set here. The first layer is placed at the back of the image and the last at the very front.
> **Warning**
> Layer names MUST match the folders' name where your layers are stored
```javascript
{
    growEditionSizeTo: 5,
    layersOrder: [
      { name: "Background" },
      { name: "Eyeball" },
      { name: "Eye color" },
      { name: "Iris" },
      { name: "Shine" },
      { name: "Bottom lid" },
      { name: "Top lid" },
    ],
  },
];
```
> **Note**
> Fields such as Symbol, Creators, and sellerFeeBasisPoints are now stored onchain
6. The image size is set in the `config.js` file.
```javascript
const format = {
  width: 512,
  height: 512,
};
```
6. Open terminal and check you're within the `Hector Solana NFTs` folder and do </br> `yarn install`
7. To generate do </br> `node index.js`
8. Check results in `Build` folder.
