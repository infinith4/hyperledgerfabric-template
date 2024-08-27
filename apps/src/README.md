npm install -g npm-check-updates


------------

cd farm



npm i  --legacy-peer-deps
npm run build
npm run start

---

ncu
ncu -u

rm -R node_modules/
rm package-lock.json

npm i 


------------

```
cd factory/
npm i  --legacy-peer-deps
npm run build
PORT=3005 react-scripts start
npm run start
```

------------


```
cd market
npm i  --legacy-peer-deps
npm run build
PORT=3005 react-scripts start
npm run start
```

------------

```
cd server
docker build ./ -t meatchain-server
docker run meatchain-server
```


-----


```
cd testing
npm i
node test-network.js
```


-----

# Apps and Meatchain server

This section contains the Javascript apps that interact with the blockchain network.
Folder structure explained below.

| Subfolder | Description                                                                                                  |
|-----------|--------------------------------------------------------------------------------------------------------------|
| testing/  | Contains a series of scripts that tests each functionality of the chaincode. It's an integration test        |
| server/   | Contains the code of the Meatchain api. It acts as a middleman between the network and the rest of the apps. |
| farm/     | Contains the code for the Farm app.                                                                          |
| factory/  | Contains the code for the Factory app.                                                                       |
| market/   | Contains the code for the supermarket app.                                                                   |