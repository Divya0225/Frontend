<template>
    

    <div  :class="product.inventory >80 ? 'green': 'red' ">

                        <h2>{{product.name}}</h2>
                        <h4> {{product.category}}</h4>
                        <h4> {{product.price}}</h4>
                        <h4> {{product.color}}</h4>
                        <h4> {{product.brand}}</h4>
                        <h4> {{product.inventory}}</h4>
    </div>
</template>

<script>

export default{
    name: 'SingleClothing',
    props:{
        product: Array
    }
}
</script>

<style scoped>

.green{
    background-color: green;
}

h4{
    margin: 2px;
}

div{
    background-color: #ffb89e;
    color: black;
    padding: 1em;
    text-align: center;
    width: 80%;
    margin: auto;
    

}

.red{
background-color: orangered !important;

}


</style>