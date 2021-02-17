# Documentation

## stations.service

Each station is an object served by a [public
API](https://geoportalgasolineras.es/#/Descargas).  The way that the station
data is structured is very unwieldy, therefore this service will fulfill two
roles: 

    1. Request an array of stations - `GET /stations`
    2. Parse the raw station objects into useful data - `rawStation => station`

It is not clear at the time of development whether handling this through the
client or by the server would be the best choice (server takes a while to
wake up, and station data is lightweight).

Because of this, it is important that this task is handled as a microservice,
which will accept a `query` object and will return an array of `stations`. This
way we can avoid having a monolithic codebase and therefore it will be possible
to change application responsibilities in the future should we find a better
solution

