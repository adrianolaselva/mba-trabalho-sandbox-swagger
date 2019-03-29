
# Apis para controle de frota


### Filtragem de veículos

Esta api permite filtrar veículos mais próximos das coordenadas do passageiro e que esteja com status de "WAITING_FOR_RACE" (Aguardando corrida)

```sh
curl -X GET \
  "https://editor.swagger.io/v1/fleet/vehicles?lat=-23.5740998&lng=-46.6254214&status=WAITING_FOR_RACE&category=BASIC" \
  -H "accept: application/json"
```

### Iniciar uma viagem

Um dos veículos retornados deve ser selecionado para criar uma viagem

```sh
curl -X POST "https://editor.swagger.io/v1/fleet/vehicles/da39a3ee5e6b4b0d3255bfef95601890afd80709/travels" \
  -H "accept: application/json" \
  -H "Content-Type: application/json" \
  -d "{ \
    \"customer\": { \
      \"uuid\": \"da39a3ee5e6b4b0d3255bfef95601890afd80709\", \
    }, \
    \"startingLocation\": { \
      \"lat\": -23.5740998, \
      \"lng\": -46.6254214 \
    }, \
    \"destinationLocation\": { \
      \"lat\": -23.5740998, \
      \"lng\": -46.6254214 \
    }, \
    \"currentLocation\": { \
      \"lat\": -23.5740998, \
      \"lng\": -46.6254214 \
      }, \
      \"status\": \"IN_PROGRESS\", \
      \"evaluation\": 0 \
    }"
```

### Altera informações da viagem, quando esta próxima de ser concluída

Atualiza informaçes da viagem, tal como geolocalização e ao se aproximar do destino muda status para "RUN_TO_BE_COMPLETED"

```sh
curl -X PUT "https://editor.swagger.io/v1/fleet/vehicles/da39a3ee5e6b4b0d3255bfef95601890afd80709/travels/da39a3ee5e6b4b0d3255bfef95601890afd80709" \
  -H "accept: application/json" \
  -H "Content-Type: application/json" \
  -d "{ \
    \"customer\": { \
      \"uuid\": \"da39a3ee5e6b4b0d3255bfef95601890afd80709\", \
    }, \
    \"startingLocation\": { \
      \"lat\": -23.5740998, \
      \"lng\": -46.6254214 \
    }, \
    \"destinationLocation\": { \
      \"lat\": -23.5740998, \
      \"lng\": -46.6254214 \
    }, \
    \"currentLocation\": { \
      \"lat\": -23.5740998, \
      \"lng\": -46.6254214 \
      }, \
      \"status\": \"RUN_TO_BE_COMPLETED\", \
      \"evaluation\": 0 \
    }"
```

### Altera informações da viagem, altera status da viagem para concluída

Atualiza informaçes da viagem, tal como geolocalização e ao se aproximar do destino muda status para "RUN_TO_BE_COMPLETED"

```sh
curl -X PUT "https://editor.swagger.io/v1/fleet/vehicles/da39a3ee5e6b4b0d3255bfef95601890afd80709/travels/da39a3ee5e6b4b0d3255bfef95601890afd80709" \
  -H "accept: application/json" \
  -H "Content-Type: application/json" \
  -d "{ \
    \"customer\": { \
      \"uuid\": \"da39a3ee5e6b4b0d3255bfef95601890afd80709\", \
    }, \
    \"startingLocation\": { \
      \"lat\": -23.5740998, \
      \"lng\": -46.6254214 \
    }, \
    \"destinationLocation\": { \
      \"lat\": -23.5740998, \
      \"lng\": -46.6254214 \
    }, \
    \"currentLocation\": { \
      \"lat\": -23.5740998, \
      \"lng\": -46.6254214 \
      }, \
      \"status\": \"FINISHING_RACE\", \
      \"evaluation\": 5 \
    }"
```



