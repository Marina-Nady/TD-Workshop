<template>
    <div class="container">
        <div class="header">
            <img src="../assets/header.jpg"/>
            <!-- <h1>What it's like to travel to Hawaii right now</h1>
            <hr/>
            <h4>Free flights to remote workers</h4> -->
        </div>
        <div class="nav-bar">
            <ul class="d-flex">
                <li class="flex-item active" >
                    <a href="#">Section 1</a>
                </li>
                <li class="flex-item">
                    <a href="#">Section 2</a>
                </li>
                <li class="flex-item">
                    <a href="#">Section 3</a>
                </li>
            </ul>
        </div>
        <div class="content">
            <div class="first-section d-flex">
                <div class="image">
                    <img src="../assets/section1.jpg">
                </div>
                <div class="text">
                    <h1>Section 1</h1>
                    <table>
                        <tr>
                            <td class="title">Population</td>
                            <td>Total (1,415,872), Rank (40th)</td>
                        </tr>
                        <tr>
                            <td class="title">Dimensions</td>
                            <td>Length 1,522 mi (2,450 km) . Width n/a mi (n/a km)</td>
                        </tr>                        
                        <tr>
                            <td class="title">Language</td>
                            <td>Offcial languages English, Hawaiian</td>
                        </tr>                        
                        <tr>
                            <td class="title">Largest city</td>
                            <td>The capital (Honolulu)</td>
                        </tr>                        
                        <tr>
                            <td class="title">Largest metro </td>
                            <td>The largest metro in Island of O'ahu</td>
                        </tr>                        
                        <tr>
                            <td class="title">Elevation</td>
                            <td>Highest elevation 13,796 ft (4,205.0 m)</td>
                        </tr>
                    </table>
                    
                </div>
            </div>
        </div>
    </div>
</template>

<script>

</script>

<style>
    .header img, .image img {
        width: 100%;
        height: auto;
    }
    .header{
        position: relative;
    }
    .header h1,h4,hr{
        position: absolute;
    }
    .header h1{
        top: 15%;
        left: 5%;
        color: #fff;
        width: 19rem;
        font-family: 'Ibarra Real Nova', serif;
        font-weight: 400;
        font-size: 28pt;
    }
    .header hr{
        top: 70%;
        left: 5%;
        width: 15%;
        color: #818181;
    }
     .header h4{
        top: 70%;
        left: 5%;
        color: #fff;
        font-family: 'Ibarra Real Nova', serif;
        font-weight: 400;
    }
  .nav-bar ul li a{
        text-decoration: none;
        color: #515151;
    }
    .nav-bar ul {
        list-style: none;
        text-align: center;
        padding: 0;
        margin: 0;
    }
    .d-flex{
        display: flex;
        flex-wrap: wrap;
    }
    .flex-item {
  background-color: #fff;
  padding: 20px;
  flex: 30%;
}

.active{
    border-bottom: 3px solid #2e297b;
    color: #2e297b;
}
.content{
    background: #f9f6f6;
    padding: 3rem;
}
.text h1{
    font-family: 'Merriweather', serif;
}
.text{
    padding: 0 2rem;
}
.text, .image{
    flex: 47%;
}
.title{
    color: #707070;
    font-weight: 600;
    font-size: 10pt;
    padding: 0.5rem 2rem 1rem 0;

}

@media (max-width: 800px) {
  .flex-item, .text, .image {
    flex: 100%;
  }
  .text{
      padding: 0;
  }
  .title{
      padding: 0;
  }
  .content {
    padding: 2rem;
}
table{
    border-spacing: 1rem;
}
}

</style>
