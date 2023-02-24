<template>
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-GLhlTQ8iRABdZLl6O3oVMWSktQOp6b7In1Zl3/Jr59b6EGGoI1aFkw7cmDA6j6gD" crossorigin="anonymous">
  <div>
    
    <p>Please enter your values below:</p>

    <div class="mx-0 mx-sm-auto">
  <div class="card">
    <div class="card-body">
      <div class="text-center">
        <i class="far fa-file-alt fa-4x mb-3 text-primary"></i>

         <h1>Carbon Footprint Calculator</h1>
        <p>
          Have some ideas how to improve our product?
          <strong>Give us your feedback.</strong>
        </p>
      </div>

      <hr />

      <form class="px-4" action="">
        <p class="text-center"><strong>Your rating:</strong></p>

        <div class="form-check mb-2">
          <input class="form-check-input" type="radio" name="exampleForm" id="radio2Example1" />
          <label class="form-check-label" for="radio2Example1">
            Very good
          </label>
        </div>
        <div class="form-check mb-2">
          <input class="form-check-input" type="radio" name="exampleForm" id="radio2Example2" />
          <label class="form-check-label" for="radio2Example2">
            Good
          </label>
        </div>
        <div class="form-check mb-2">
          <input class="form-check-input" type="radio" name="exampleForm" id="radio2Example3" />
          <label class="form-check-label" for="radio2Example3">
            Medicore
          </label>
        </div>
        <div class="form-check mb-2">
          <input class="form-check-input" type="radio" name="exampleForm" id="radio2Example4" />
          <label class="form-check-label" for="radio2Example4">
            Bad
          </label>
        </div>
        <div class="form-check mb-2">
          <input class="form-check-input" type="radio" name="exampleForm" id="radio2Example5" />
          <label class="form-check-label" for="radio2Example5">
            Very bad
          </label>
        </div>

      </form>
    </div>
    

  </div>
  
</div>
    <div class="mx-0 mx-sm-auto">
  <div class="card">
    <div class="card-body">
      <div class="text-center">
        <i class="far fa-file-alt fa-4x mb-3 text-primary"></i>
        <p>
          <strong>Your opinion matters</strong>
        </p>
        <p>
          Have some ideas how to improve our product?
          <strong>Give us your feedback.</strong>
        </p>
      </div>

      <hr />

      <form class="px-4" action="">
        <p class="text-center"><strong>Your rating:</strong></p>

        <div class="form-check mb-2">
          <input class="form-check-input" type="radio" name="exampleForm" id="radio2Example1" />
          <label class="form-check-label" for="radio2Example1">
            Very good
          </label>
        </div>
        <div class="form-check mb-2">
          <input class="form-check-input" type="radio" name="exampleForm" id="radio2Example2" />
          <label class="form-check-label" for="radio2Example2">
            Good
          </label>
        </div>
        <div class="form-check mb-2">
          <input class="form-check-input" type="radio" name="exampleForm" id="radio2Example3" />
          <label class="form-check-label" for="radio2Example3">
            Medicore
          </label>
        </div>
        <div class="form-check mb-2">
          <input class="form-check-input" type="radio" name="exampleForm" id="radio2Example4" />
          <label class="form-check-label" for="radio2Example4">
            Bad
          </label>
        </div>
        <div class="form-check mb-2">
          <input class="form-check-input" type="radio" name="exampleForm" id="radio2Example5" />
          <label class="form-check-label" for="radio2Example5">
            Very bad
          </label>
        </div>

      </form>
    </div>
    
    <div class="card-footer text-end">
      <button type="button" class="btn btn-success">Submit</button>
    </div>
  </div>
  
</div>

     <form @submit.prevent="handleSubmit">
      <label for="mileage">Yearly Car Mileage: </label>
      <input type="mileage" name="mileage" v-model="mileage" />
      <div v-show="submitted && !mileage">Mileage is required</div>
      <br /> <br />

      <label for="electric">Monthly Electric Bill: </label>
      <input type="electric" name="electric" v-model="electricBill" />
      <div v-show="submitted && !electricBill">Your electric bill is required</div>
      <br /> <br />

      <label for="gas">Monthly Gas Bill: </label>
      <input type="gas" name="gas" v-model="gasBill" />
      <div v-show="submitted && !gasBill">Your gas bill is required</div>
      <br /> <br />

      <label for="oil">Monthly Oil Bill: </label>
      <input type="oil" name="oil" v-model="oilBill" />
      <div v-show="submitted && !oilBill">Your oil bill is required</div>
      <br /> <br />

      <label for="smallFlightNum">Number of flights taken in the past year (4 hours or less): </label>
      <input type="smallFlightNum" name="smallFlightNum" v-model="smallFlightNum" />
      <div v-show="submitted && !smallFlightNum">Flight number is required</div>
      <br /> <br />

      <label for="largeFlightNum">Number of flights taken in the past year (over 4 hours): </label>
      <input type="largeFlightNum" name="largeFlightNum" v-model="largeFlightNum" />
      <div v-show="submitted && !largeFlightNum">Flight number is required</div>
      <br /> <br />

      <p>Do you recycle paper?</p>
      <input type="radio" id="recyclePaper" value="Yes" v-model="recyclePaper" />
      <label for="recyclePaper">Yes</label>

      <input type="radio" id="recyclePaper" value="No" v-model="recyclePaper" />
      <label for="recyclePaper">No</label>
      <br /> <br />

       <p>Do you recycle tin and aluminum?</p>
      <input type="radio" id="recycleTin" value="Yes" v-model="recycleTin" />
      <label for="recyclePaper">Yes</label>

      <input type="radio" id="recycleTin" value="No" v-model="recycleTin" />
      <label for="recycleTin">No</label>
      <br /> <br />


      <button v-on:click="handleSubmit">Calculate Footprint</button>
      <br /> <br />
    </form>

    <p>Total Carbon Footprint: {{ totalFootprint }}</p>
    <br /> <br />

    <p>Total Household Carbon Footprint: {{ homeFootprint }}</p>
    <br /> <br />

    <p>Total Travel Carbon Footprint: {{ travelFootprint }}</p>
    <br /> <br />

     <p>You're Carbon Footprint Rating: {{ rating }}</p>
    <br /> <br />
  </div>

   
</template>

<script>
  export default {
    data(){
      return {
        mileage: 0,
        electricBill: 0,
        gasBill: 0,
        oilBill: 0,
        carbonMileage: 0,
        smallFlightNum: 0,
        largeFlightNum: 0,
        recyclePaper: "No",
        recycleTin: "No",
        carbonElectricBill: 0,
        carbonGasBill: 0,
        carbonOilBill: 0,
        carbonSmallFlightNum: 0,
        carbonLargeFlightNum: 0,
        carbonRecyclePaper: 184,
        carbonRecycleTin: 166,
        totalFootprint: 0,
        homeFootprint: 0,
        travelFootprint: 0,
        rating : "Neutral.",

      }
    },
    methods: {
      handleSubmit(e){
        this.submitted = true
        this.carbonMileage = this.mileage * 0.79;
        this.carbonElectricBill = this.electricBill * 105;
        this.carbonGasBill = this.gasBill * 105;
        this.carbonOilBill = this.oilBill * 113;
        this.carbonSmallFlightNum = this.smallFlightNum * 1100;
        this.carbonLargeFlightNum = this.largeFlightNum * 4400;

        this.totalFootprint = this.carbonMileage + this.carbonElectricBill + this.carbonGasBill + this.carbonOilBill + this.carbonSmallFlightNum + this.carbonLargeFlightNum;

        this.homeFootprint = this.carbonElectricBill + this.carbonGasBill + this.carbonOilBill;

        this.travelFootprint = this.carbonMileage + this.carbonSmallFlightNum + this.carbonLargeFlightNum;

         if (this.recyclePaper == "No"){
          this.totalFootprint = this.totalFootprint + this.carbonRecyclePaper;
          this.homeFootprint = this.homeFootprint + this.carbonRecyclePaper;
        }

        if (this.recycleTin == "No"){
          this.totalFootprint = this.totalFootprint + this.carbonRecycleTin;
          this.homeFootprint = this.homeFootprint + this.carbonRecycleTin;
        }


      },
    }
  }

</script>

<style scoped>


</style>