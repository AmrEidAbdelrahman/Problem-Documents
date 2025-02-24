
need the same version of postgres ( here is 16 )
PGPASSWORD="AVNS_9U-pass" /usr/lib/postgresql/16/bin/pg_dump \
  "host=db-postgresql-nyc3-81182-do-user-10857715-0.c.db.ondigitalocean.com port=25060 dbname=kershless_prod_db user=doadmin sslmode=require" \
  -F c -f kershless_prod_db_20_2_2025.dump

download the buckup
scp root@147.182.242.35:/root/kershless_prod_db_20_2_2025.dump kershless_prod_db_20_2_2025.dump

restore
pg_restore -h db-postgresql-nyc3-81182-do-user-10857715-0.c.db.ondigitalocean.com -p 25060 -U doadmin -d kershless_prod_buckup_feb -v kershless_prod_db_20_2_2025.dump
