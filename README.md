# data-engineering-bootcamp
data-engineer


uv run python ingest_data.py \
  --pg-user=root \
  --pg-pass=root \
  --pg-host=localhost \
  --pg-port=5432 \
  --pg-db=ny_taxi \
  --target-table=yellow_taxi_trips_2021_1 \
  --year=2021 \
  --month=1 \
  --chunksize=100000



  docker run -it --rm\
  --network=pg-network \
  taxi_ingest:v001 \
    --pg-user=root \
    --pg-pass=root \
    --pg-host=pgdatabase \
    --pg-port=5432 \
    --pg-db=ny_taxi \
    --target-table=yellow_taxi_trips_2021_1 \
    --year=2021 \
    --month=1 \
    --chunksize=100000


  docker run -it --rm\
  taxi_ingest:v001 \
    --pg-user=root \
    --pg-pass=root \
    --pg-host=pgdatabase \
    --pg-port=5432 \
    --pg-db=ny_taxi \
    --target-table=yellow_taxi_trips_2021_1 \
    --year=2021 \
    --month=1 \
    --chunksize=100000


  docker run -it --rm\
  --network=pipeline_default \
  taxi_ingest:v001\
  --pg-user=root \
  --pg-pass=root \
  --pg-host=pgdatabase \
  --pg-port=5432 \
  --pg-db=ny_taxi \
  --target-table=yellow_taxi_trips_2021_1 \
  --year=2021 \
  --month=1 \
  --chunksize=100000




  docker run -it --rm \
  --pg-user=root \
  --pg-pass=root \
  --pg-host=localhost \
  --pg-port=5432 \
  --pg-db=ny_taxi \
  --target-table=yellow_taxi_trips \
  --year=2021 \
  --month=1 \
  --chunksize=100000


docker run -it \
  -e POSTGRES_USER="root" \
  -e POSTGRES_PASSWORD="root" \
  -e POSTGRES_DB="ny_taxi" \
  -v ny_taxi_postgres_data:/var/lib/postgresql \
  -p 5432:5432 \
  --network=pg-network \
  --name pgdatabase \
  postgres:18





✅ THE REAL FIX (works 100%)

You must disable pgAdmin’s secure cookie & enhanced protection when running behind a proxy.

🔧 Stop and remove pgAdmin

'''bash
docker stop pgadmin
docker rm pgadmin

'''

🔧 Run pgAdmin with REQUIRED env fixes

'''bash
docker run -it \
  --name pgadmin \
  --network pg-network \
  -p 8085:80 \
  -e PGADMIN_DEFAULT_EMAIL=admin@admin.com \
  -e PGADMIN_DEFAULT_PASSWORD=root \
  -e PGADMIN_CONFIG_SERVER_MODE=False \
  -e PGADMIN_CONFIG_MASTER_PASSWORD_REQUIRED=False \
  -e PGADMIN_CONFIG_ENHANCED_COOKIE_PROTECTION=False \
  -e PGADMIN_CONFIG_SESSION_COOKIE_SECURE=False \
  -e PGADMIN_CONFIG_WTF_CSRF_ENABLED=False \
  dpage/pgadmin4


'''

docker run -it \
  --name pgadmin \
  --network pg-network \
  -p 8085:80 \
  -e PGADMIN_DEFAULT_EMAIL=admin@admin.com \
  -e PGADMIN_DEFAULT_PASSWORD=root \
  -e PGADMIN_CONFIG_SERVER_MODE=False \
  -e PGADMIN_CONFIG_MASTER_PASSWORD_REQUIRED=False \
  -e PGADMIN_CONFIG_ENHANCED_COOKIE_PROTECTION=False \
  -e PGADMIN_CONFIG_SESSION_COOKIE_SECURE=False \
  -e PGADMIN_CONFIG_WTF_CSRF_ENABLED=False \
  dpage/pgadmin4


docker run -it \
  -e POSTGRES_USER="root" \
  -e POSTGRES_PASSWORD="root" \
  -e POSTGRES_DB="ny_taxi" \
  -v ny_taxi_postgres_data:/var/lib/postgresql \
  -p 5432:5432 \
  --network=pg-network \
  --name pgdatabase \
  postgres:18