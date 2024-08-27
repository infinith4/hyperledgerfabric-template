```
docker rm `docker ps -a -q`
docker rmi $(docker images -q) -f
docker container prune -f
docker image rm $(docker images -q)
docker volume prune -f
docker network prune -f
docker builder prune -f
sudo rm -R /src/fabric-testnetwork
```

```
mkdir -p /src/fabric-testnetwork
cd /src/fabric-testnetwork
curl -sSLO https://raw.githubusercontent.com/hyperledger/fabric/main/scripts/install-fabric.sh && chmod +x install-fabric.sh
./install-fabric.sh --fabric-version 2.4.3 docker binary
sudo rm -R /src/fabric-testnetwork/config
docker images
```

cd /src
git clone -b main https://github.com/aaronmbdev/porkchain.git porkchain01
cp -R /src/porkchain01/network /src/fabric-testnetwork/
cp -R /src//porkchain01/config /src/fabric-testnetwork/
cd /src/fabric-testnetwork/network
./network.sh up
./network.sh createChannel
```

カレントディレクトリは/src/fabric-testnetwork/network とする。

```
cd: /src/fabric-testnetwork/network export PATH=${PWD}/../bin: $PATH
export FABRIC_CFG_PATH=$PWD/../config/
peer version
```

cp -R /src/porkchain01/chaincode /src/fabric-testnetwork/
cd /src/fabric-testnetwork/chaincode/pig
go mod tidy
go mod vendor

cd /src/fabric-testnetwork/network
peer lifecycle chaincode package pigManagement.tar-gz --path ../chaincode/pig --lang golang --label pigManagement_1.4
