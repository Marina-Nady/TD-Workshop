<template>
    <div class="header">
        <!-- <img src="../assets/header.jpg"/> -->
        <div class="text-header">
            <h1>What it's like to travel to Hawaii right now</h1>
            <h4>Free flights to remote workers</h4>
        </div>
    </div>
</template>

<style>
    .header{
        position: relative;
        background-image: linear-gradient(to right, rgba(0, 0, 0, 0.726) , transparent), 
        url(../assets/header.jpg);
        background-size: cover;
        width: 100%;
        height: 15rem;
        padding: 3rem 0 0 3rem;
    }
    .text-header{
        display: flex;
        justify-content: flex-start;
        align-items: center;
        position: absolute;
        flex-wrap: wrap;
    }
    .header h1{
        color: #fff;
        font-family: 'Ibarra Real Nova', serif;
        font-weight: 400;
        font-size: 3vw;
        width: 100%;
    }
     .header h4{
        color: #fff;
        font-family: 'Ibarra Real Nova', serif;
        font-weight: 400;
        font-size: 1.3vw;
        padding: 1rem 0 0 0;
        border-top: 1px solid #e5e2e2;
        margin-top: 1rem;
    }
    @media (max-width: 700px) {
    .header {
        height: 7rem;
        padding: 1rem 0 0 1rem;
    }
    .header h4 {
        margin-top: 0;
    }
    }
</style>