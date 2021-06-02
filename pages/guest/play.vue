<template>
    <div>
        <b-img id="logo" src="~/assets/images/logo.png" alt="logo" />
        <div id="game_description">
            <h1>Guest Play</h1>
            <span style="color:white">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Quas, mollitia.
                    {{ this.$router.params }}
                </span>
             
    </div> 
        
    </div>
</template>

<script>
export default {
    data() {
        return {
           
        }
    }
}
</script>

<style>

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
</style>