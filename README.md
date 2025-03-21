Para ver el resultado verdadero de todos los requests usamos una tecnología de Postman llamada scripts donde el resultado pedido se puede ver en la pestaña de Tests.

# Omdb api
### 2. Identificar peliculas que tienen titulo CARS
Hacemos un request a: https://www.omdbapi.com/?apikey=[APIKEY]&s=Cars donde ponemos como parametro una query de busqueda (con key 's') y valor Cars.<br>
Con un script nos devuelve los resultados totales: 376
```javascript
let response = pm.response.json();

pm.test("La cantidad de peliculas que coinciden con el titulo Cars son " + response.totalResults);
```
### 3. Buscar "Hunger" y devolver el nombre de la última pelicula que retorna OMDb API.
Hacemos un resquest a:  https://www.omdbapi.com/?apikey=[APIKEY]&s=Hunger&page=41 donde ponemos como parametro una query de busqueda (con key 's') y valor Hunger. Como página le pasamos el número 41 ya que probando de a poco descubrimos que es la ultima página. <br>
Utilizando el siguiente script nos da como resultado: *"Hunger Is Real: The Voices of Western North Carolina"*
```javascript
let response = pm.response.json()

pm.test("El nombre de la ultima pelicula es : " + response.Search[0].Title)
```
### 4. Obtener información de la película "Monsters Inc."
Hacemos un resquest a:  https://www.omdbapi.com/?apikey=[APIKEY]=Monsters Inc donde ponemos como parametro una query de busqueda (con key 't') y valor Monsters Inc. <br>
Utilizando el siguiente script nos da los siguientes resultados: *"Hay 1,017,055 votos"*
*"Actuaron los siguientes actores: Pete Docter, David Silverman, Lee Unkrich"*
```javascript
let responseJson = pm.response.json();

pm.test(`Hay ${responseJson.imdbVotes} votos`);
pm.test("Actuaron los siguientes actores: " + responseJson.Director);
```
### 5. Obtener de la película "Rocky IV" algunos datos
Hacemos un resquest a:  https://www.omdbapi.com/?apikey=[APIKEY]&t=Rocky IV  donde ponemos como parametro una query de busqueda (con key 't') y valor MRocky IV. <br>
Utilizando el siguiente script nos da los siguientes resultados: *"El/los genero/s es: Drama, Sport"*
*"El director es: Sylvester Stallone"*
*"La pelicula dura: 91 min"*
```javascript
let responseJson = pm.response.json();

pm.test("El/los genero/s es: " + responseJson.Genre);
pm.test("El director es: " + responseJson.Director);
pm.test("La pelicula dura: " + responseJson.Runtime);
```
### 6. Obtener información con un ID de base
Hacemos un resquest a:  https://www.omdbapi.com/?apikey=[APIKEY]&i=tt0067992 donde ponemos como parametro una query de busqueda (con key 't') y valor MRocky IV. <br>
Utilizando el siguiente script nos da los siguientes resultados: *"El/los genero/s es: Drama, Sport"*
*"El director es: Sylvester Stallone"*
*"La pelicula dura: 91 min"*
```javascript
let responseJson = pm.response.json();

pm.test("El/los genero/s es: " + responseJson.Genre);
pm.test("El director es: " + responseJson.Director);
pm.test("La pelicula dura: " + responseJson.Runtime);
```
# Poke api
