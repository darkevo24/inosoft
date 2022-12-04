<template>
    <head>
        <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
    </head>
    <body>
        <div style="padding:20px">
        <div>
            <p style="color:#04bcbc;font: bolder;">Cost Detail</p>
        </div>
        <table class="table">
  <thead style="background:#f8f4fc">
    <tr>
      <th scope="col">Description</th>
      <th scope="col">Qty</th>
      <th scope="col">UOM</th>
      <th scope="col">Unit Price</th>
      <th scope="col">Discount (%)</th>
      <th scope="col">VAT (%)</th>
      <th></th>
      <th scope="col">Currency</th>
      <th scope="col">VAT Amount</th>
      <th scope="col">Sub Total</th>
      <th scope="col">Total</th>
      <th scope="col">Charge To</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="item in data">
        <th scope="col"><input type="text" placeholder="Description" class="form-control"></th>
      <th scope="col"><input style="width:100px" type="number" placeholder="Qty" class="form-control"></th>
      <th scope="col">  
        <select style="width:70px" class="custom-select">
            <option selected>{{ item.UOM }}</option>
        </select>
    </th>
      <th scope="col"><input style="width:100px" type="number" placeholder="unit Price" class="form-control"></th>
      <th scope="col"><input style="width:100px" placeholder="0" type="number" class="form-control"></th>
      <th scope="col"><input style="width:100px" placeholder="0" type="number" class="form-control"></th>
      <th><img style="width:20px;height:20px" src="../../images/arrow.png"></th>
      <th scope="col">        
        <select class="custom-select">
            <option selected>{{ item.currency }}</option>
        </select>
    </th>
      <th scope="col">0.00</th>
      <th scope="col">0.00</th>
      <th scope="col">0.00</th>
      <th scope="col">        
        <select style="width:100px" class="custom-select">
            <option selected>{{ item.charge }}</option>
        </select>
    </th>
    <th>
        <div style="width:40px;height:40px;background-color:lightgrey;display: flex;justify-content: center;align-items: center;">
            <div style="width:20px;height:1px;background:grey">
            </div>
        </div>
    </th>
    </tr>
  </tbody>
</table>
<div style="display:flex;position: relative;">
    <div style="width:800px">
        <p>Exhange Rate 1 USD = 3.6725 AED</p>
    </div>
    <div>
    <div style="display: flex;background-color:#f8f4fc ;">
        <p style="margin:0 30px 0 30px;width:100px;">AED in Total</p>
        <p style="margin:0 30px 0 30px">0.00</p>
        <p style="margin:0 30px 0 30px">0.00</p>
        <p style="margin:0 30px 0 30px">0.00</p>
    </div>
    <div style="display: flex;background-color:#f8f4fc ;">
        <p style="margin:0 30px 0 30px;width:100px;">USD in Total</p>
        <p style="margin:0 30px 0 30px">0.00</p>
        <p style="margin:0 30px 0 30px">0.00</p>
        <p style="margin:0 30px 0 30px">0.00</p>
    </div>
    </div>
    <div style="width:100px">
    <div style="margin-right:10px;position:absolute;right:0;width:40px;height:40px;background-color:#04bcbc;display: flex;justify-content: center;align-items: center;">
        <p style="font-size:30px;color : white;margin-top:10px;">+</p>
    </div>
</div>
</div>
</div>
    </body>
</template>

<script>
import axios from "axios";
import right_arrow from "../../images/arrow.png"

export default {
    data(){
        return {
            data : null
        }
    },
    mounted() {
    axios.get("http://127.0.0.1:8000/api/user")
     .then(function (response) {
        this.data = response.data;
        console.log(this.data[0].UOM);
     }.bind(this))
}
}

</script>