# Vikunja Env Vars


[Vikunja Env Vars Docs Source](https://vikunja.io/docs/full-docker-example/)

### Optionally add Redis

VIKUNJA_REDIS_ENABLED: 1

VIKUNJA_REDIS_HOST: 'redis:6379'

VIKUNJA_CACHE_ENABLED: 1

VIKUNJA_CACHE_TYPE: redis

	  
## Vikunja Env Vars


### Optionally use postgres 

 
POSTGRES_PASSWORD: secret

POSTGRES_USER: vikunja



### Vikunja basic vars


VIKUNJA_SERVICE_JWTSECRET: <a super secure random secret>
  
VIKUNJA_SERVICE_FRONTENDURL: http://<your public frontend url with slash>/
  
VIKUNJA_DATABASE_HOST: db
  
VIKUNJA_DATABASE_PASSWORD: secret
  
VIKUNJA_DATABASE_TYPE: mysql
  
VIKUNJA_DATABASE_USER: vikunja
  
VIKUNJA_DATABASE_DATABASE: vikunja
  
VIKUNJA_SERVICE_JWTSECRET: <a super secure random secret>
  
VIKUNJA_SERVICE_FRONTENDURL: http://<your public frontend url with slash>/
  

#### Note the default path is /app/vikunja/vikunja.db This moves to a different folder so you can use a volume and store this outside of the container so state is persisted even if container destroyed.
  
VIKUNJA_DATABASE_PATH: /db/vikunja.db
