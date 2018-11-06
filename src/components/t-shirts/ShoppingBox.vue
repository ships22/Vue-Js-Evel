<template>
<div class="main">

    <h1>Shooping Box</h1>
    <div class="customise">
        <h2> Customise t-shirts </h2>
        <div class="price_range">
            <h4>Select by price range</h4>
            <p> Max price: {{ range }}€ </p>
            <input type="range" min="20" max="100" v-model="range">    
        </div>
        <div class="brands">
            <h4>Select by brand name</h4>
            
            <select name="brands" id="brands" v-model="brands" placeholder="Select brand">
                <option value="Nike">Nike</option>
                <option value="Puma">Puma</option>
                <option value="Adidas">Adidas</option>
                <option value=''>All brands</option>
            </select>
            <p v-show="brands"> Selected: {{ brands }}</p>
        </div>
        <div class="colour">
            <h4>Select by colour</h4>
            
            <div class="red colour_box" data-value="red" @click="funcClr($event)"></div>
            
            <div class="black colour_box" data-value="black" @click="funcClr($event)"></div>
            <div class="orange colour_box" data-value="orange" @click="funcClr($event)"></div>
            <div class="blue colour_box" data-value="blue" @click="funcClr($event)"></div>
            <div class="yellow colour_box" data-value="yellow" @click="funcClr($event)"></div>
            <button @click="clearColor"> All colour </button>
            
           
           
        </div> 
    </div>
    
    <div class="display">
        <h2> T-shirts display </h2>
        
        <div class="t-shirt" v-for="(product, key) in filter" :key="key" v-if="product.Price <= range">
            <span>{{ key+1 }}</span>
                <ul>
                    <li>Name: {{ product.Name }}</li>
                    <li>Brand: {{ product.Brand }}</li>
                    <li width="200px" height="220px" v-html="product.Img" ></li>
                
                    <li>Price: {{ product.Price }}€</li>
                </ul>   
        </div>
    </div>
</div>
</template>
<script>
export default {
    props: ['products'],
    data(){
        return {
            range: 100,
            brands: '',
            color: [],
        }
    },
    methods: {
        funcClr: function(e){
            this.clearColor();
            var selectedColor = e.target.getAttribute("data-value");
            this.listingClr(selectedColor);
            
        },
        listingClr: function(clr){
            var x = this.products;
            if(!this.color.includes(clr)){
                this.color.push(clr);
            
                
            } else if(this.color) {
                
                this.color.push(clr);
                
                
            }
                
        },
        clearColor: function(){
            this.color = [];
        }
    },
    computed: {
        filter: function(){
            
            if(this.brands) {
                return this.products.filter((products) => {
                return products.Brand.match(this.brands);
                 });
                 
            };
            
            if(this.color){
                return this.products.filter((products) => {
                    return products.Color.match(this.color);
                 }); 
            }
            
            else {
                return this.products;
            };
            
        }
    }
}
                
</script>
<style scopped>
    *{
        margin: 0;
        padding: 0;
    }
    div.main {
        padding: 20px;
        text-align: center;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: center;
    }
    div.main h1 {
        flex-grow: 1;
        width: 100%;
        margin-bottom: 40px;
        padding: 20px;
        background: rgb(242, 239, 239);
    }
    div.customise {
        border: 2px solid rgb(94, 91, 91);
        border-radius: 5px;
        width: 25%;
        flex-direction: column;
        display: flex;
        flex-wrap: wrap;
        text-align: center;
        padding: 10px;
        margin-right: 3%;
    }
    div.customise h2 {
        flex-grow: 1;
        background: rgb(94, 91, 91);
        color: white;
        border-left: 5px solid rgb(62, 175, 18);
        margin-bottom: 20px;
        padding-top: 10px;
    }
    div.price_range, div.brands, div.colour {
        flex-grow: 1;
        background: rgb(242, 239, 239);
        padding: 20px;
        border-left: 5px solid rgb(62, 175, 18);
        margin-bottom: 5px;
        height: 80px;
    }
    div.price_range p, div.brands p {
        margin: 10px;
    }
    div.price_range input, div.brands select {
        width: 100%;
    }
    .colour_box {
        height: 25px;
        width: 25px;
        margin: 15px 5px 0px 5px;
        display: inline-block;
    }
    .red {
        background: red;
    }
    .black {
        background: black;
    }
    .orange {
        background: orange;
    }
    .blue {
        background: blue;
    }
    .yellow {
        background: yellow;
    }
    button {
        height: 30px;
        width: 170px;
        background: white;
        color: black;
        transition: .4s;
        margin-top: 10px;
    }
    button:hover {
        background: rgb(238, 236, 236);
        cursor: pointer;
    }
        
    /*---- Display ----*/
      div.display {
        border: 2px solid rgb(94, 91, 91);
        border-radius: 5px;
        width: 65%;
        flex-direction: row;
        display: flex;
        flex-wrap: wrap;
        padding: 10px;
        overflow: scroll;
        height: 500px;
       
    }
    div.display h2 {
        flex-grow: 1;
        width: 100%;
        height: 60px;
        line-height: 60px;
        color: white;
        background: rgb(94, 91, 91);
        border-left: 5px solid rgb(62, 175, 18);
    }
    div.display div.t-shirt {
        width: 25%;
        margin: auto;
        height: 240px;
        margin-top: 20px;
        padding-top: 10px;
        border: 2px solid rgb(209, 209, 205);
        box-shadow: 2px 5px 10px rgb(216, 211, 211);
        
    }    
    div.display div.t-shirt ul {
        list-style: none;
        display: block;
    }
    div.display div.t-shirt ul li {
        margin-top: 10px;
        color: black;
    }
    div.display div.t-shirt ul li:nth-child(3) {
        height: 100px;
        width: 120px;
        margin: 15px auto 10px;
    }
    div.display div.t-shirt ul li:nth-child(3) img{
        height: 100%;
        width: 100%;
    }
    select  {
        height: 40px;
        font-size: 18px;
        margin-top: 10px;
    }
        
</style>
            
  

            
                
            
       
       
        

                   
                       

                 
                    
                    
                    
                    
                        
                
                       
                
            
        
        
        
            
                
       
    
    

        

        
        
               
                
    
        
       
                    

        
        
        

        
        

        
        
        

            
       


