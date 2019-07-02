# api-gateway-example
ASP.NET Core </br>
Microservices </br>
Api-Gateway (ocelot)</br>
vscode</br>
docker </br>
docker-compose</br>

1 - git clone https://github.com/satem02/api-gateway-example.git  </br> 
2 - cd api-gateway-example</br>
3 - docker-compose -f "docker-compose.yml" up -d --build</br>


i make to call an api gateway by creating two api at simple level.</br>

first api call:  http://localhost:7001/api/values</br>
second api call: http://localhost:7002/api/values</br>

first api call with gateway  : http://localhost:7000/first-api/values</br>
second api call with gateway : http://localhost:7000/second-api/values</br>


