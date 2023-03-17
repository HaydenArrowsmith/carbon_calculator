<template>

<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
 
 <div >
   <figure class="text-center text-success">
  <blockquote class="blockquote">
    <h1 class="display-3 ">Carbon Footprint Calculator</h1>
  </blockquote>
  </figure>

    
    <form @submit.prevent="handleSubmit">

    <div class="col d-flex justify-content-center">
      <div class="card border-success mb-3 border border-2" style="width: 50rem;">
      <div class="card-header">Travel</div>
        <div class="card-body">
          <div class="text-center">
            <i class="far fa-file-alt fa-4x mb-3 text-primary"></i>
            <h5 class="card-title">Yearly Car Mileage</h5>
            <p>
              Please enter your yearly mileage below:
            </p>
          </div>
        <div class="text-center">
        <label for="mileage">Yearly Car Mileage: </label>
          <input type="mileage" name="mileage" v-model="mileage" />
          <div v-show="submitted && !mileage">Mileage is required</div>
          <br /> <br />
        </div>

        
        </div>
      </div>
    </div>
        
        
    <br /> 

    <div class="col d-flex justify-content-center">
      <div class="card border-success mb-3 border border-2" style="width: 50rem;">
        <div class="card-header">Household</div>
        <div class="card-body">
          <div class="text-center">
            <i class="far fa-file-alt fa-4x mb-3 text-primary"></i>
            <h5 class="card-title">Monthly Electric Bill</h5>
            <p>
              Please enter your monthly electric bill below:
            </p>
          </div>
        <div class="text-center">
        <label for="electric" class="text-center">Monthly Electric Bill: </label>
          <input type="electric" name="electric" v-model="electricBill" />
          <div v-show="submitted && !electricBill">Your electric bill is required</div>
          <br /> <br />
        </div>

        
        </div>
      </div>
    </div>

    <br /> 

    <div class="col d-flex justify-content-center">
      <div class="card border-success mb-3 border border-2" style="width: 50rem;">
        <div class="card-header">Household</div>
        <div class="card-body">
          <div class="text-center">
            <i class="far fa-file-alt fa-4x mb-3 text-primary"></i>
            <h5 class="card-title">Monthly Gas Bill</h5>
            <p>
              Please enter your monthly gas bill below:
            </p>
          </div>
        <div class="text-center">
        <label for="gas">Monthly Gas Bill: </label>
        <input type="gas" name="gas" v-model="gasBill" />
        <div v-show="submitted && !gasBill">Your gas bill is required</div>
      <br /> <br />
        </div>

        
        </div>
      </div>
    </div>

    <br /> 

    <div class="col d-flex justify-content-center">
      <div class="card border-success mb-3 border border-2" style="width: 50rem;">
        <div class="card-header">Household</div>
        <div class="card-body">
          <div class="text-center">
            <i class="far fa-file-alt fa-4x mb-3 text-primary"></i>
            <h5 class="card-title">Monthly Oil Bill</h5>
            <p>
              Please enter your monthly oil bill below:
            </p>
          </div>
        <div class="text-center">
        <label for="oil">Monthly Oil Bill: </label>
        <input type="oil" name="oil" v-model="oilBill" />
        <div v-show="submitted && !oilBill">Your oil bill is required</div>
      <br /> <br />
        </div>

        
        </div>
      </div>
    </div>

    <br /> 

    <div class="col d-flex justify-content-center">
      <div class="card border-success mb-3 border border-2" style="width: 50rem;">
        <div class="card-header">Travel</div>
        <div class="card-body">
          <div class="text-center">
            <i class="far fa-file-alt fa-4x mb-3 text-primary"></i>
            <h5 class="card-title">Short Flight Number</h5>
            <p>
              Please enter the number of flights you've taken in the past year (4 hours or less):
            </p>
          </div>
        <div class="text-center">
        <label for="smallFlightNum">Number of Flights: </label>
      <input type="smallFlightNum" name="smallFlightNum" v-model="smallFlightNum" />
      <div v-show="submitted && !smallFlightNum">Flight number is required</div>
      <br /> <br />
        </div>

        
        </div>
      </div>
    </div>

    <br /> 

     <div class="col d-flex justify-content-center">
      <div class="card border-success mb-3 border border-2" style="width: 50rem;">
        <div class="card-header">Travel</div>
        <div class="card-body">
          <div class="text-center">
            <i class="far fa-file-alt fa-4x mb-3 text-primary"></i>
            <h5 class="card-title">Long Flight Number</h5>
            <p>
              Please enter the number of flights you've taken in the past year (over 4 hours):
            </p>
          </div>
        <div class="text-center">
        <label for="largeFlightNum">Number of flights taken in the past year (over 4 hours): </label>
      <input type="largeFlightNum" name="largeFlightNum" v-model="largeFlightNum" />
      <div v-show="submitted && !largeFlightNum">Flight number is required</div>
      <br /> <br />
        </div>

        
        </div>
      </div>
    </div>

    <br /> 

     <div class="col d-flex justify-content-center">
      <div class="card border-success mb-3 border border-2" style="width: 50rem;">
        <div class="card-header">Household</div>
        <div class="card-body">
          <div class="text-center">
            <i class="far fa-file-alt fa-4x mb-3 text-primary"></i>
            <h5 class="card-title">Recycling</h5>
            <p>
              Please choose whether you recycle the following materials:
            </p>
          </div>
        <div class="text-center">
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


        </div>
        
        </div>
      </div>
    </div>

      <div class="text-center">
        <button type="button" class="btn btn-success btn-lg" data-bs-toggle="modal" data-bs-target="#resultsModal" v-on:click="handleSubmit">Calculate Footprint</button>
        <br /> <br />
      </div>
    </form>


    <div class="modal fade" id="resultsModal" tabindex="-1" aria-labelledby="resultsModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel">Results</h5>
        <button type="button" class="btn-success" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        <p>Total Carbon Footprint: {{ totalFootprint }}</p>
    <br /> <br />

    <p>Total Household Carbon Footprint: {{ homeFootprint }}</p>
    <br /> <br />

    <p>Total Travel Carbon Footprint: {{ travelFootprint }}</p>
    <br /> <br />

     <p>Your Carbon Footprint Rating: {{ rating }}</p>
    <br /> <br />

    <strong> Results not what you expected?</strong>
    <br>
    <p>Just Energy have the best resources for finding out how you can improve your carbon footprint rating further.</p><a href="https://justenergy.com/blog/15-ways-reduce-carbon-footprint-greenhouse-gas/">See here</a>
      </div>

      <div class="modal-footer">
        <button type="button" class="btn btn-success" data-bs-dismiss="modal">Close</button>
      </div>
    </div>
  </div>
</div>
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
        rating : "Good",

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

        if (this.totalFootprint <= 6000){
          this.rating = "Very Low"
        }

         if (this.totalFootprint > 6000 && this.totalFootprint <= 15999){
          this.rating = "Low"
        }

        if (this.totalFootprint >= 16000 && this.totalFootprint <= 22000){
          this.rating = "Average"
        }

        if (this.totalFootprint > 22000){
          this.rating = "High"
        }


      },
      
    }
  }

</script>

<style scoped>



</style>