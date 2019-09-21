 

=============================

## GET
```
[HttpGet("GetProductList")]
http://202.86.220.134:5196/api/ProductDemo/GetProductList
input: empty
output: 
[{"ProductId":"P0001","ProductName":"233 SELEEVE YOUK L/L 370","Qty":15,"Brand":"=N/A=","UnitName":"PCS","SellPrice":900.0,"CostPrice":0.0,"ROL":10.0},{"ProductId":"P0002","ProductName":"234 SELEEVE YOUK L/L 370","Qty":20,"Brand":"=N/A=","UnitName":"PCS","SellPrice":1400.0,"CostPrice":0.0,"ROL":15.0},{"ProductId":"P0003","ProductName":"235 SELEEVE YOUK L/L 370","Qty":12,"Brand":"=N/A=","UnitName":"PCS","SellPrice":1600.0,"CostPrice":0.0,"ROL":7.0},{"ProductId":"P0004","ProductName":"236 SELEEVE YOUK L/L 370","Qty":20,"Brand":"=N/A=","UnitName":"PCS","SellPrice":2300.0,"CostPrice":0.0,"ROL":15.0}
```
## POST
```
[HttpPost("ProductSave")]
api: http://202.86.220.134:5196/api/ProductDemo/ProductSave
input : 
    {
      "ProductId":0 ,
      "ProductName": "Tissue-paper2",
      "OPQty": 0,
      "SupplierId": "0",
      "UnitId": "2",
      "Currency": "85",
      "Weight": 50.0,
      "BrandId": "1",
      "ROL": 1.0,
      "SellPrice": 25.0,
      "CostPrice": 22.0
    }
output : Successfully Save
```
## GET USE ID
```
[HttpGet("GetProductData/{id:int}")]
api: http://202.86.220.134:5196/api/ProductDemo/GetProductData/956
input: empty
output: 
    {
      "ProductId":950 ,
      "ProductName": "Tissue-paper2",
      "OPQty": 0,
      "SupplierId": "0",
      "UnitId": "2",
      "Currency": "85",
      "Weight": 50.0,
      "BrandId": "1",
      "ROL": 1.0,
      "SellPrice": 25.0,
      "CostPrice": 22.0
    }
 ```
 ## HTTPPUT 
 ```
[HttpPut("ProductUpdate/{id:int}")]
api: http://202.86.220.134:5196/api/ProductDemo/ProductUpdate/956
input: 
    {
      "ProductId":950 ,
      "ProductName": "Tissue-paper2",
      "OPQty": 0,
      "SupplierId": "0",
      "UnitId": "2",
      "Currency": "85",
      "Weight": 50.0,
      "BrandId": "1",
      "ROL": 1.0,
      "SellPrice": 25.0,
      "CostPrice": 22.0
    }
output: Successfully Update
 ```
 ## HttpDelete
  ```
[HttpDelete("ProductDelete/{id:int}")]
api: http://202.86.220.134:5196/api/ProductDemo/ProductDelete/956
input: empty
output : Successfully delete
```
