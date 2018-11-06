<template>
    <Tshirts :products="products" ></Tshirts>
</template>
<script>
import Tshirts from '@/components/t-shirts/ShoppingBox.vue'
export default {
    components: {
        Tshirts
    }, 
    data() {
        return {
        
            products: [

                { Name: 'Polo neck', 
                Price: 23, 
                Img: '<img src="https://kickz.akamaized.net/en/media/images/p/600/nike-BACKBOARD_DROPTAIL_T_Shirt-UNIVERSITY_RED_UNIVERSITY_RED_WHITE-1.jpg">', 
                Brand: 'Nike',
                Color: 'red'},

                { Name: 'Round neck', 
                Price: 45, 
                Img: '<img src="http://mindleaders.org.za/wp-content/uploads/2016/02/tshirts-001-3-1.jpg">', 
                Brand: 'Puma', 
                Color: 'green'},

                { Name: 'Straight', 
                Price: 25, 
                Img: '<img src="http://mindleaders.org.za/wp-content/uploads/2016/02/tshirts-001-5-1-1.jpg">', 
                Brand: 'Adidas',
                Color: 'blue' },

                { Name: 'Rough neck', 
                Price: 55, 
                Img: '<img src="https://s3.gsxtr.com/i/pr/t-shirt-adidas-originals-original-trefoil-t-shirt-blue-85392-674-1.jpg">', 
                Brand: 'Adidas',
                Color: 'blue' },

                { Name: 'Skinny round neck', 
                Price: 35, 
                Img: '<img src="https://dimg.dillards.com/is/image/DillardsZoom/main/nike-dry-short-sleeve-beast-training-tee/05402928_zi_black.jpg">', 
                Brand: 'Nike',
                Color: 'black' },

                { Name: 'Round neck', 
                Price: 80, 
                Img: '<img src="https://assets.jassets.com/h_600,q_95,w_440/v1/assets/images/productImage/2018/4/19/11524118405416-1.webp">', 
                Brand: 'Adidas',
                Color: 'blue' },

                { Name: 'Round neck', 
                Price: 45, 
                Img: '<img src="https://photos6.spartoo.co.uk/photos/832/8329811/8329811_500_A.jpg">', 
                Brand: 'Nike',
                Color: 'orange' },

                { Name: 'Straight neck', 
                Price: 49, 
                Img: '<img src="https://ae01.alicdn.com/kf/HTB1PSLUQpXXXXcGapXXq6xXFXXXs/Original-New-Arrival-2017-PUMA-Archive-Graphic-Logo-Tee-Men-s-T-shirts-short-sleeve-Sportswear.jpg_640x640.jpg">', 
                Brand: 'Puma',
                Color: 'black' },

                { Name: 'Rough neck', 
                Price: 55, 
                Img: '<img src="https://assets.jassets.com/h_600,q_95,w_440/v1/assets/images/productImage/2018/5/2/11525235047895-1.jpg">', 
                Brand: 'Adidas',
                Color: 'red' },

                { Name: 'Skinny fashion', 
                Price: 65, 
                Img: '<img src="http://www.mosgielstation.co.nz/images/cxs/Designs%20Men%20s%20Puma%20-%20No%201%20Logo%20T%20Shirt%20Lime%20Punch.jpg">', 
                Brand: 'Puma',
                Color: 'yellow' }
            ]
        }
        
    }
}
</script>

            
