<script>
    
</script>
<template>
    <div class="greets">
        <div class="card">
            <h1>Happy anniversary, sweetie</h1><br>
            <p>you are the apple of my eye <i class="fa-solid fa-heart"></i></p>
        </div>
    </div>
</template>
<style scoped>
    .greets{
        position: absolute;
        display: flex;
        justify-content: center;
        align-items: center;
        z-index: 1;
        width: 100%;
        height: 100vh;
        background-color: rgba(0, 0, 0, 0.137);
    }

    .greets .card{
        position: relative;
        display: block;
        background-color: white;
        text-align: center;
        z-index: 3;
        padding: 30px;
        border-radius: 8px;
    }
    
    .greets .card h1{
        margin-bottom: -10px;
        font-family: 'Great Vibes', cursive;
        font-weight: lighter;
        font-size: 4rem;
    }

    .greets .card p{
        font-size: 18px;
    }

    .greets .card p i{
        color: red;
    }

</style>