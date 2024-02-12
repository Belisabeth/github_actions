*Usage
docker build -t cadastre .

docker-compose down > /dev/null 2>&1 && docker-compose run --name cadastre --rm cadastre app/import-pci-edigeo.sh

docker-compose run --name cadastre --rm cadastre cadastre-builder import-pci --bundle edigeo sources-edigeo/ dist/
