<template>
<b-container> 
   <b-img id="logo" src="~/assets/images/logo.png" alt="logo" />
    <div id="game_description">
        <svg class="line_up" viewBox="0 0 408.976 3.503">
            <path id="line_up" d="M 0 0 L 408.9759521484375 3.503005981445313">
            </path>
        </svg> 
        <img id="game_description_j" src="~/assets/images/game_description_j.png" /> 
        <svg class="line_down" viewBox="0 0 408.976 3.503">
		    <path id="line_down" d="M 0 0 L 408.9759521484375 3.503005981445313">
		    </path>
	    </svg> 
    </div> 
      
            <category @gameOptions="handleOptions" />
   
    <div class="sign">
        <div>
            <b-button variant="outline-primary"  class="bttn">SIGN-UP </b-button> 
        </div>
        <div>
         <b-button variant="outline-primary"  class="bttn">LOGIN</b-button>
        </div>
        <div> 
  </div>
    </div>
    <div id="available_text">
		<span>Will be available soon on</span> 
	</div> 
    <div>
        <img id="android" src="~/assets/images/android.png" srcset="~/assets/images/android.png 1x, ~/assets/images/android@2x.png 2x">
        <img id="apple" src="~/assets/images/apple.png" srcset="~/assets/images/apple.png 1x, ~/assets/images/apple@2x.png 2x">
	</div>
    <div id="credit"> 
		<span>
            Dwell in the Word (DWORD) Bible Game is originally created as a board game by Christ Centered Education before Indigitous made this web version.
        </span>
		<p>
			{{ selectedMode }}  {{ selectedCategory }}
		</p>
	</div> 
	<div class="ndgt_logo"> 
		<img src="~/assets/images/ndgt.png"> 
	</div> 

       
    
  </b-container> 
</template>

<script>
import category from './category.vue'
 

export default {
  components: { category },

    data() {
      return {
        selectedMode:'',
        selectedCategory: '',
        modalShow: false,
      }
    },
    methods: {
      handleOptions(modeSelected,categorySelected) {
          this.selectedMode = modeSelected
		  this.selectedCategory = categorySelected

		//   load game board 
		this.$router.push({
			path: 'guest/play',
			params: { modeSelected: this.selectedMode, 
			categorySelected: this.selectedCategory }
			
		})
      }
    }
}
</script>

<style> 
 
/* for the page */ 

.modalbody {
  background-color: #247776;
  font-size: calc(32px + (40 - 32)*(100vw - 320px)/ (1024 - 320));
  background-position: 100% 100%;
  color: #381803;
  display: flex;
  font: 1em Nunito, sans-serif;
  height: 100%;
  width: 100%;
  line-height: 1.5;
}

#logo {
    position: absolute;
    width: 437.333px;
    height: 130.487px;
    left: 171px;
    top: 283.289px;
    overflow: visible;
    }
#game_description {
	position: absolute;
	width: 409.426px;
	height: 62.178px;
	left: 185px;
	top: 426.533px;
	overflow: visible;
    }
#line_up {
	fill: transparent;
	stroke: rgba(255,255,255,1);
	stroke-width: 1px;
	stroke-linejoin: miter;
	stroke-linecap: butt;
	stroke-miterlimit: 4;
	shape-rendering: auto;
    }
.line_up {
	overflow: visible;
	position: absolute;
	width: 408.984px;
	height: 4.503px;
	left: 0.45px;
	top: -5px;
	transform: matrix(1,0,0,1,0,0);
    }
#line_down {
	fill: transparent;
	stroke: rgba(255,255,255,1);
	stroke-width: 1px;
	stroke-linejoin: miter;
	stroke-linecap: butt;
	stroke-miterlimit: 4;
	shape-rendering: auto;
    }
.line_down {
	overflow: visible;
	position: absolute;
	width: 408.984px;
	height: 4.503px;
	left: 0.45px;
	top: 45.675px;
	transform: matrix(1,0,0,1,0,0);
    }


#available_text {
	right: 340px;
	top: 460px;
	position: absolute;
	overflow: visible;
	width: 93px;
	white-space: nowrap;
	text-align: left;
	font-family: Gotham;
	font-style: normal;
	font-weight: normal;
	font-size: 11px;
	color: rgba(134,227,227,1);
}
#android {
	position: absolute;	 
  	right: 322px;
	top: 480px;
	overflow: visible;
}
#apple {
	position: absolute;	 
  	right: 192px;
	top: 480px;
	overflow: visible;
    }
 #credit {
	left: 192px;
	top: 480px;
	position: absolute;
	overflow: visible;
	width: 423px;
	height: 37px;
	text-align: left;
	font-family: Gotham;
	font-style: normal;
	font-weight: normal;
	font-size:11px;
	color: rgb(194, 228, 228); 
    }

.ndgt_logo { 
	position: absolute;
	width: 26px;
	height: 26px;
	left: 171px;
	top: 37px;
	overflow: visible;
	transition: all 0.3s snap;
	--web-animation: fadein 0.3s snap;
	--web-action-type: view;
	--web-action-target: Web_1366__53;
	cursor: pointer;
    }
.sign {
    position: absolute; 
    display: flex;  
    right: 160px; 
	top: 380px; 
}

.sign > div {  
  padding: 20px; 
}

.sign .bttn {
    border: 2px solid #4CAF50; /* Green */
    opacity: 0.8;   
	width: 80px;
	white-space: nowrap;
	text-align: left;
	font-family: Gotham; 
	font-size: 13px;
	color: rgba(134,227,227,1);
    transition-duration: 0.4s;
}

.bttn:hover {
  background-color: #4CAF50; /* Green */
  color: white;
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
</style>