<template>
  <div class="wrap">
    <div class="select-box">
      <div class="select-box1">
        <h2>Claim1 list</h2>
        <select v-model="claim1" multiple class="multi-box">
          <option @click = "_logic" v-for="claim1 in claims1" v-bind:key="claim1">
            {{ claim1 }}
          </option>
        </select>
        <br>
        <div class="selected-box selected-box1">
        </div>
        <span class= "littleBox" id="claim-1">{{ claim1[0] }}</span>
        <span class= "littleBox" id="evidence-1">{{ evidence1[0] }}</span>

      
        <p v-if="condition_s1 == ''" id = "wait1" class="support">waiting</p>
        <p v-if="support1 && condition_s1 != ''" id = "support1" class="support">support</p>
      </div>
      <div class="select-box2">
        <h2>Evidence1 list</h2>
        <select v-model="evidence1" multiple class="multi-box">
          <option @click = "_logic" v-for="evidence1 in evidences1" v-bind:key="evidence1">
            {{ evidence1 }}
          </option>
        </select>
        <br>
        <div class="selected-box selected-box1">
        </div>
        <span class= "littleBox" id="claim-1">{{ claim1[0] }}</span>
        <span class= "littleBox" id="evidence-1">{{ evidence1[0] }}</span>

      </div>
      <div class="select-box3">
        <h2>Claim2 list</h2>
        <select v-model="claim2" multiple class="multi-box">
          <option @click = "_logic" v-for="claim2 in claims2" v-bind:key="claim2">
            {{ claim2 }}
          </option>
        </select>
        <br>
        <div class="selected-box selected-box2">
        </div>
        <span class= "littleBox" id="claim-2">{{ claim2[0] }}</span>
        <span class= "littleBox" id="evidence-2">{{ evidence2[0] }}</span>
   
      </div>
      <div class="select-box4">
        <h2>Evidence2 list</h2>
        <select v-model="evidence2" multiple class="multi-box">
          <option @click = "_logic" v-for="evidence2 in evidences2" v-bind:key="evidence2">
            {{ evidence2 }}
          </option>
        </select>
        <br>
        <div class="selected-box selected-box2">
        </div>
        <span class= "littleBox" id="claim-2">{{ claim2[0] }}</span>
        <span class= "littleBox" id="evidence-2">{{ evidence2[0] }}</span>
        <p v-if="condition_s2 == ''" id = "wait2" class="support">waiting</p>
        <p v-if="support2 && condition_s2 != ''" id = "support2" class="support">support</p>
      </div>
      <p v-if="condition_u == ''" id="waiting" class="relation">waiting</p>
      <p v-if="attack && condition_u!= ''" id="attack" class="relation">Undercut</p>
      
    
    </div>  
  </div>
</template>

<script>
export default {
  name: 'Index',
  props: {
    msg: String
  },
  data() {
    return {
      attack: true,
      claims1: [
                "c124",
        "c154",
        "c18",
        "c20",
        "c20",
        "c22",
        "c221",
        "c226",
        "c234",
        "c246",
        "c281",
        "c299",
        "c31",
        "c311",
        "c326",
        "c356",
        "c374",
        "c390",
        "c397",
        "c411",
        "c437",
        "c445",
        "c497",
        "c520",
        "c54",
        "c549",
        "c575",
        "c575",
        "c577",
        "c590",
        "c598",
        "c611",
        "c623",
        "c623",
        "c631",
        "c678",
        "c690",
        "c702",
        "c710",
        "c75",
        "c769",
        "c771",
        "c773",
        "c777",
        "c807",
        "c812",
        "c830",
        "c835",
        "c838",
        "c846",
        "c857",
        "c863",
        "c92",
        "c951",
        "c967",
        "c991",
        "c992",

      ],
      evidences1: [
        "e10",
        "e107",
        "e108",
        "e111",
        "e129",
        "e131",
        "e133",
        "e135",
        "e137",
        "e14",
        "e142",
        "e146",
        "e148",
        "e148",
        "e149",
        "e151",
        "e153",
        "e157",
        "e161",
        "e166",
        "e167",
        "e170",
        "e175",
        "e175",
        "e179",
        "e180",
        "e180",
        "e185",
        "e187",
        "e187",
        "e19",
        "e193",
        "e20",
        "e21",
        "e27",
        "e27",
        "e27",
        "e28",
        "e29",
        "e31",
        "e35",
        "e36",
        "e36",
        "e37",
        "e39",
        "e41",
        "e44",
        "e45",
        "e45",
        "e48",
        "e5",
        "e56",
        "e6",
        "e6",
        "e62",
        "e63",
        "e71",
        "e74",
        "e77",
        "e83",
        "e83",
        "e86",
        "e88",
        "e88",
        "e91",
        "e91",
        "e91",
        "e92"

      ],
      claims2: [
        "c124",
        "c154",
        "c18",
        "c20",
        "c20",
        "c22",
        "c221",
        "c226",
        "c234",
        "c246",
        "c281",
        "c299",
        "c31",
        "c311",
        "c326",
        "c356",
        "c374",
        "c390",
        "c397",
        "c411",
        "c437",
        "c445",
        "c497",
        "c520",
        "c54",
        "c549",
        "c575",
        "c575",
        "c577",
        "c590",
        "c598",
        "c611",
        "c623",
        "c623",
        "c631",
        "c678",
        "c690",
        "c702",
        "c710",
        "c75",
        "c769",
        "c771",
        "c773",
        "c777",
        "c807",
        "c812",
        "c830",
        "c835",
        "c838",
        "c846",
        "c857",
        "c863",
        "c92",
        "c951",
        "c967",
        "c991",
        "c992",

      ],
      evidences2: [
         "e10",
        "e107",
        "e108",
        "e111",
        "e129",
        "e131",
        "e133",
        "e135",
        "e137",
        "e14",
        "e142",
        "e146",
        "e148",
        "e148",
        "e149",
        "e151",
        "e153",
        "e157",
        "e161",
        "e166",
        "e167",
        "e170",
        "e175",
        "e175",
        "e179",
        "e180",
        "e180",
        "e185",
        "e187",
        "e187",
        "e19",
        "e193",
        "e20",
        "e21",
        "e27",
        "e27",
        "e27",
        "e28",
        "e29",
        "e31",
        "e35",
        "e36",
        "e36",
        "e37",
        "e39",
        "e41",
        "e44",
        "e45",
        "e45",
        "e48",
        "e5",
        "e56",
        "e6",
        "e6",
        "e62",
        "e63",
        "e71",
        "e74",
        "e77",
        "e83",
        "e83",
        "e86",
        "e88",
        "e91",
        "e92"
      ],
      claim1: ["claim1"],
      evidence1: ["evidence1"],
      claim2: ["claim2"],
      evidence2: ["evidence2"],
      condition_u: "",
      condition_s1: "",
      condition_s2: ""
    }
  },
  methods: {
    _logic() {
      for (let i = 0; i < this.claim2.length; ++i){
        for(let j=0; j < this.evidence1.length; ++j){

          switch(true){
            case this.evidence1[j] == "e27" && this.claim2[i] == "c20":
            this.condition_u = "attack";
            break;
            case this.evidence1[j] == "e41" && this.claim2[i] == "c20":
            this.condition_u = "attack";
            break;
            case this.evidence1[j] == "e157" && this.claim2[i] == "c20":
            this.condition_u = "attack";
            break;
            case this.evidence1[j] == "e167" && this.claim2[i] == "c20":
            this.condition_u = "attack";
            break;
            case this.evidence1[j] == "e45" && this.claim2[i] == "c281":
            this.condition_u = "attack";
            break;
            default:
            this.condition_u = "waiting"
          }
        }
      }
      for(let i =0; i< this.claim1.length; ++i){
       for(let j=0; j < this.evidence1.length; ++j){


          switch(true){
            case this.claim1[i] == "c20" && this.evidence1[j] == "e62":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c221" && this.evidence1[j] == "e151":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c445" && this.evidence1[j] == "e133":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c18" && this.evidence1[j] == "e133":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c124" && this.evidence1[j] == "e20":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c411" && this.evidence1[j] == "e21":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c863" && this.evidence1[j] == "e39":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c577" && this.evidence1[j] == "e48":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c623" && this.evidence1[j] == "e135":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c771" && this.evidence1[j] == "e74":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c281" && this.evidence1[j] == "e129":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c326" && this.evidence1[j] == "e83":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c22" && this.evidence1[j] == "e44":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c773" && this.evidence1[j] == "e773":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c835" && this.evidence1[j] == "e88":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c769" && this.evidence1[j] == "e88":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c702" && this.evidence1[j] == "e91":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c812" && this.evidence1[j] == "e92":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c31" && this.evidence1[j] == "e10":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c590" && this.evidence1[j] == "e107":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c598" && this.evidence1[j] == "e108":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c54"&& this.evidence1[j] == "e185":
            this.condition_s1 ="support1";
            break;
            
            case this.claim1[i] == "c520" && this.evidence1[j] == "e137":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c777" && this.evidence1[j] == "e35":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c807" && this.evidence1[j] == "e56":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c234" && this.evidence1[j] == "e142":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c299" && this.evidence1[j] == "e146":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c830" && this.evidence1[j] == "e153":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c690" && this.evidence1[j] == "e37":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c991" && this.evidence1[j] == "e175":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c311" && this.evidence1[j] == "e180":
            this.condition_s1 ="support1";
            break;
            case this.claim1[i] == "c92" && this.evidence1[j] == "e193":
            this.condition_s1 ="support1";
            break;
            default:
            this.condition_s1 = "wait1";
          }
        }
      }
      for(let i =0; i< this.claim2.length; ++i){
        for(let j=0; j < this.evidence2.length; ++j){

         switch(true){
            case this.claim2[i] == "c20" && this.evidence2[j] == "e62":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c221" && this.evidence2[j] == "e151":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c445" && this.evidence2[j] == "e133":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c18" && this.evidence2[j] == "e133":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c124" && this.evidence2[j] == "e20":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c411" && this.evidence2[j] == "e21":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c863" && this.evidence2[j] == "e39":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c577" && this.evidence2[j] == "e48":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c623" && this.evidence2[j] == "e149":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c771" && this.evidence2[j] == "e74":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c281" && this.evidence2[j] == "e129":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c326" && this.evidence2[j] == "e83":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c22" && this.evidence2[j] == "e44":
            this.condition_s2="support2";
            break;
            case this.claim2[i] == "c773" && this.evidence2[j] == "e86":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c835" && this.evidence2[j] == "e88":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c769" && this.evidence2[j] == "e88":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c702" && this.evidence2[j] == "e91":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c812" && this.evidence2[j] == "e92":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c31" && this.evidence2[j] == "e10":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c590" && this.evidence2[j] == "e107":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c598" && this.evidence2[j] == "e108":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c54" && this.evidence2[j] == "e185":
            this.condition_s2 ="support2";
            break;
            
            case this.claim2[i] == "c520" && this.evidence2[j] == "e137":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c777"&& this.evidence2[j] == "e35":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c807" && this.evidence2[j] == "e56":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c234" && this.evidence2[j] == "e142":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c299" && this.evidence2[j] == "e146":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c830" && this.evidence2[j] == "e153":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c690" && this.evidence2[j] == "e37":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c991" && this.evidence2[j] == "e175":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c311" && this.evidence2[j] == "e180":
            this.condition_s2 ="support2";
            break;
            case this.claim2[i] == "c92" && this.evidence2[j] == "e193":
            this.condition_s2 ="support2";
            break;
            default:
            this.condition_s2 = "wait2";
          }
        }
      }
      this._relation()
    },
    _relation() {
      if (this.condition_u == "attack") {
        this.attack = true
      } else{
        this.attack = false
      }
      if (this.condition_s1 == "support1"){
         this.support1 = true
      } else{
        this.support1 = false
      }
      if (this.condition_s2 == "support2"){
         this.support2 = true
      } else{
        this.support2 = false
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .select-box {
    margin: 0;
    position: absolute;
    width: 100%;
    top: 5%;
    /* left: 50%;                          */
    /* transform: translate(0, -50%)  */
  }
    .select-box1 {
      width: 25%;
      float: left;
    }
    .select-box2 {
      width: 25%;
      float: left;
    }
    .select-box3 {
      width: 25%;
      float: right;
    }
    .select-box4 {
      width: 25%;
      float: right;
    }
    

  .multi-box {
    width: 90%;
    border-radius: 30px;
    border-color: salmon;
    border-width: 3px;
    font-size: 19px;
  }
  option {
    padding-top: 20px;
    padding-bottom: 20px;
    text-align: center;
    background: white;
    outline: none;
  }
  select {
    appearance: none;
  }
  .selected-box {
    display: inline-block;
    border:2px solid;
    border-color: black;
    width: 300px;
    height: 300px;
    text-align: center;
    line-height: 300px;
    border-radius: 300px;
    font-size: 19px;
    word-wrap:break-word;
    text-overflow: ellipsis;
    overflow: hidden;
  }
    .selected-box1 {
      position: absolute;
      top: 105%;
      left: 16%;
    }
    .selected-box2 {
      position: absolute;
      top: 105%;
      right: 16%;
    }
    .relation {
      position: absolute;
      top: 125%;
      left: 45%;
      font-size: 50px;
      color: red;
    }
    #support {
      color: blue !important;
    }
    #attack {
      color: red;
    }
    #waiting {
      color: black;
    }
    .littleBox {
      display: block;
      width: 80px;
      height: 20px;
      border: 2px solid;
    }
    #claim-1 {
      position: absolute;
      top: 120%;
      left: 24%;
    }

    #claim-2 {
      position: absolute;
      top: 120%;
      right: 24%;
    }

    #evidence-1 {
      position: absolute;
      top: 180%;
      left: 24%
    }

    #evidence-2 {
      position: absolute;
      top: 180%;
      right: 24%;
    }

    .support {
      font-size: 19px;
      font-weight: 700;
      color: blue
    }

    #support1 {
      position: absolute;
      top: 145%;
      left: 25%;
    }

    #support2 {
      position: absolute;
      top: 145%;
      right: 25%;
    }
    #wait1{
      position: absolute;
      top: 145%;
      left: 25%;
    }
    #wait2{
      position: absolute;
      top: 145%;
      right: 25%;
    }
</style>
