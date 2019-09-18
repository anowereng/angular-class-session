### Array Use
``` 
1 .
data: any = [
    { id: 11, name: 'Dr Nice' },
    { id: 12, name: 'Narco' },
    { id: 13, name: 'Bombasto' },
    { id: 14, name: 'Celeritas' },
    { id: 15, name: 'Magneta' },
    { id: 16, name: 'RubberMan' },
    { id: 17, name: 'Dynama' },
    { id: 18, name: 'Dr IQ' },
    { id: 19, name: 'Magma' },
    { id: 20, name: 'Tornado'}
   ] ; 
   ``` 
   2 .
   
   ```
   <ul class="heroes">
    <li *ngFor="let x of data">
      <span>Id: {{x.id}}</span>
      <span>Name: {{x.name}}</span>
    </li>
</ul> 
```

### API Use Data Load

```
1 . 
export interface Employees {
  postId: number;
  id: number;
  name: number;
  email: string ;
  body: string;
}
2 .
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { Employees } from '../Models/employees';
import { Observable } from 'rxjs';

@Injectable({
  providedIn: 'root'
})
export class EmployeesService {

constructor(private Http: HttpClient) { }


getEmployees(): Observable<Employees> {
  return this.Http.get<Employees>('https://jsonplaceholder.typicode.com/comments');
}

}
3 .
import { Component, OnInit } from '@angular/core';
import { EmployeesService } from '../services/employees.service';

@Component({
  selector: 'app-employees',
  templateUrl: './employees.component.html',
  styleUrls: ['./employees.component.css']
})
export class EmployeesComponent implements OnInit {
  rowData: any = [];
 
  constructor(public empService: EmployeesService ) { }

  ngOnInit() {
    this.getDataList();
  }

   getDataList() {
    this.empService.getEmployees().subscribe(response => {
      this.rowData = response;
      console.log(response);
    }, error => {
       console.log(error);
    });
  }


}
