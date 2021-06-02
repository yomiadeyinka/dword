<template>

<div id="button"> 
    <b-button id="show-btn" @click="showModal" class="button" style="vertical-align:middle"><span>PLAY NOW </span></b-button>

    <b-modal ref="my-modal" hide-footer title="GAME OPTIONS">
      <div class="d-block text-left"> 
        <!-- category box -->
        <b-card
        border-variant="warning"
        header="Select Category"
        header-bg-variant="transparent"
        align="left"
        >
        <b-card-text>
          <b-form-group label="" v-slot="{ ariaDescribedby }">
            <b-form-radio-group
              v-model="categorySelected"
              :options="optionsCategory"
              :aria-describedby="ariaDescribedby"
              name="radios-category"
              stacked
            ></b-form-radio-group>
          </b-form-group>
           <div class="mt-3">Selected: <strong>{{ categorySelected }}</strong></div> 
        </b-card-text>
      </b-card>

      <!-- mode box -->
        <b-card
        border-variant="warning"
        header="Select Game Mode"
        header-bg-variant="transparent"
        align="left"
        >
        <b-card-text>
          <b-form-group label="" v-slot="{ ariaDescribedby2 }">
            <b-form-radio-group
              v-model="modeSelected"
              :options="optionsMode"
              :aria-describedby="ariaDescribedby2"
              name="radios-mode"
              stacked
            ></b-form-radio-group>
          </b-form-group>
           <div class="mt-3">Selected: <strong>{{ modeSelected }}</strong></div> 
        </b-card-text>
      </b-card>




      </div>
      <b-button class="mt-3" variant="danger" block @click="getOptions">PLAY</b-button>
      
    </b-modal>
  </div> 
 
</template>

<script>
  export default {
    data() {
      return { 
        categorySelected: '', 
        modeSelected: '',
       
        optionsCategory: [
          { text: 'History & Geography', value: 'HG' },
          { text: 'New Testament', value: 'NT' },
          { text: 'Old Testament', value: 'OT' },
          { text: 'Plant & Animals', value: 'PA' },
          { text: 'Prophets & Prophecies', value: 'PP' },
          { text: 'People', value:'P' },
          { text: 'Wisdom', value:'W' }
        ],
        optionsMode: [
          { text: 'Time Based', value: 'Time' },
          { text: 'Number Based', value: 'Number' } 
        ]
      }   
      
    },
     methods: {
      showModal() {
        this.$refs['my-modal'].show()
      },
      getOptions() {
        this.$emit('gameOptions',this.categorySelected, this.modeSelected) 
        
        this.$refs['my-modal'].hide()
      }, 
    }
  }
</script>
<style scoped>

.text-big {
  font-size: 1.5rem;
}

#button {
	position: absolute; 
	width: 257px;
	right: 189px;
	top: 326px;
	overflow: visible;
    font-family: Gotham;
	font-style: normal; 
	font-size: 10px;
    }
 .button {
    display: inline-block;
    border-radius: 4px;
    background-color: #f4511e;
    border: none;
    color: #FFFFFF;
    text-align: center;
    font-size: 20px;
    padding: 10 70px;
    width: 240px; 
	height: 50px;
    transition: all 0.5s;
    cursor: pointer;
    margin: 5px;
    }

.button span {
  cursor: pointer;
  display: inline-block;
  position: relative;
  transition: 0.5s;
}

.button span:after {
  content: '\00bb';
  position: absolute;
  opacity: 0;
  top: 0;
  right: -30px;
  transition: 0.5s;
}

.button:hover span {
  padding-right: 25px;
}

.button:hover span:after {
  opacity: 1;
  right: 0;
}


@media only screen and (max-width: 1024px) {
.sign {  
    right: 100px;  
    }
#button { 
	right: 89px; 
    }
#android { 
  	right: 222px; 
    }
#apple { 
  	right: 92px; 
    }
#available_text {
	right: 240px; 
    }

}

@media only screen and (max-width: 768px) {
#logo { 
    top: 183.289px; 
    }
#game_description { 
	left: 185px;
	top: 326.533px; 
    }
 #credit {
	left: 192px;
	top: 380px;
    }
.sign {  
    left: 280px;  
    top: 500px;
    }
#button {  
	top: 450px;
	left: 271px; 
    }
#android { 
    top: 600px;
  	left: 290px; 
    }
#apple { 
    top: 600px;
  	left: 420px; 
    }
#available_text {
    top: 580px;
	left: 340px; 
    } 
}

@media only screen and (max-width: 540px) {
#logo { 
    left: 100px;
    top: 183.289px; 
    width: 337.333px;
    }
#game_description { 
	left: 85px;
	top: 326.533px; 
    }
 #credit {
	left: 85px;
	top: 380px;
    }
.sign {  
    left: 160px;  
    top: 500px;
    }
#button {  
	top: 450px;
	left: 151px; 
    }
#android { 
    top: 600px;
  	left: 170px; 
    }
#apple { 
    top: 600px;
  	left: 300px; 
    }
#available_text {
    top: 580px;
	left: 220px; 
    } 
}
</style>>

</style>