
- Employee.component.ts
```
import { Component, OnInit } from '@angular/core';
import { Validators, FormControl, FormGroup, FormBuilder} from '@angular/forms';
@Component({
  selector: 'app-employee-create',
  templateUrl: './employee-create.component.html',
  styleUrls: ['./employee-create.component.css']
})
export class EmployeeCreateComponent implements OnInit {
  productForm: FormGroup;
  constructor(private fb: FormBuilder) { }

  ngOnInit() {
    this.productForm = this.fb.group({
      productName: new FormControl('', Validators.required),
      category: new FormControl('', Validators.required),
      unit: new FormControl('', Validators.required),
    });
  }

  CreateProduct() {
    console.log(this.productForm.value);
  }

}
```
- employee-create.component.html

```
<form [formGroup]="productForm" (ngSubmit)="CreateProduct()">
    <div class="card">
        <div class="card-header">Product Entry </div>
        <div class="card-body">
     
    <div class="form-group row">
        <label for="example-text-input" class="col-2 col-form-label">Product Name </label>
        <div class="col-10">
          <input class="form-control" type="text" formControlName="productName" placeholder="" />
          <div *ngIf="productForm.get('productName').errors && productForm.get('productName').touched" class="invalid-status">Product Name is required</div>
        </div>
      </div>

      <div class="form-group row">
        <label for="example-text-input" class="col-2 col-form-label">Category </label>
        <div class="col-10">
          <input class="form-control" type="text" formControlName="category" placeholder="" />
          <div *ngIf="productForm.get('category').errors && productForm.get('category').touched" class="invalid-status " >Category is required</div>
        </div>
      </div>

      <div class="form-group row">
        <label for="example-text-input" class="col-2 col-form-label">Unit </label>
        <div class="col-10">
          <input class="form-control" type="text"size="30" formControlName="unit" placeholder="" />
          <div *ngIf="productForm.get('unit').errors && productForm.get('unit').touched" class="invalid-status " >unit Date is required</div>
        </div>
      </div>
      <div class="card-footer">
           <button  type="submit"  [disabled]="!productForm.valid" class="btn btn-success">Submit</button>
      </div>
    </div>
</div>
    </form>
   ```
  - Update main module
  
   ````
   import { ReactiveFormsModule } from '@angular/forms';
   
    imports: [
    ReactiveFormsModule
  ],
  
