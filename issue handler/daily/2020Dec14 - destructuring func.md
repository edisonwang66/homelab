let cars = ['ferrari', 'tesla', 'cadillac'];
let [car1, car2, car3] = cars;
console.log(car1, car2, car3); // Prints: ferrari tesla cadillac


let destinations = { x: 'LA', y: 'NYC', z: 'MIA' };
let { x, y, z } = destinations;
console.log(x, y, z); // Prints LA NYC MIA


let truck = {
  model: '1977 Mustang convertible',
  maker: 'Ford',
  city: 'Detroit',
  year: '1977',
  convertible: true
};
 
const printCarInfo = ({model, maker, city}) => {
  console.log(`The ${model}, or ${maker}, is in the city ${city}.`);
};
 
printCarInfo(truck);


Status code	Meaning
200 (OK)	This is the standard response for successful HTTP requests.
201 (CREATED)	This is the standard response for an HTTP request that resulted in an item being successfully created.
204 (NO CONTENT)	This is the standard response for successful HTTP requests, where nothing is being returned in the response body.
400 (BAD REQUEST)	The request cannot be processed because of bad request syntax, excessive size, or another client error.
403 (FORBIDDEN)	The client does not have permission to access this resource.
404 (NOT FOUND)	The resource could not be found at this time. It is possible it was deleted, or does not exist yet.
500 (INTERNAL SERVER ERROR)	The generic answer for an unexpected failure if there is no more specific information available.
For each HTTP verb, there are expected status codes a server should return upon


**checklist project**
https://docs.google.com/spreadsheets/d/16yJ7rroS5oYivgVEwOLxi9stQGv9ctKkKEnQIgTcZ8o/edit#gid=0
