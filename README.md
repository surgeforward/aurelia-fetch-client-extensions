# aurelia-fetch-client-extensions
It's a very simple set of extension methods to the robust Aurelia fetch client. The goal was simply to encapsulate common functionality. 

Example: 
```javascript
import { inject } from 'aurelia-framework';
import { HttpClient, json } from 'aurelia-fetch-client';
import "DataHandlers/aurelia-fetch-client-extensions"

@inject(HttpClient)
export class PeopleDataHandler {
  constructor(http) {
    http.configure(config => {
      config
        .useStandardConfiguration()
        .withBaseUrl('/api/people');
    });
    this.http = http;
  }

  getAll() {
    return this.http.getJson();
  }

  get(id) {
    this.http.getJson(id);
  }
  
  update(id, person) {
    this.http.put(id, person);
  }
  
  delete(id) {
    this.http.delete(id);
  }
}
```
