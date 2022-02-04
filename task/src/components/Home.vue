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
                    <a href="#section1">Section 1</a>
                </li>
                <li class="flex-item">
                    <a href="#section2">Section 2</a>
                </li>
                <li class="flex-item">
                    <a href="#section3">Section 3</a>
                </li>
            </ul>
        </div>
        <div class="content">
            <div class="first-section d-flex" id="section1">
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
            <div class="second-section" id="section2">
                <h1>Section 2</h1>
                <div class="timeline">
                    <ul>
                        <li>
                            <h3>1778</h3>               
                            <i class="fa fa-arrow-right" aria-hidden="true"></i>
                            <p>
                                Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                                Placeat dolores tenetur est voluptatem enim? Provident recusandae 
                                ipsa dolorem ad sit incidunt repellat magnam adipisci repudiandae a, unde quis minus ut?
                            </p>
                        </li>
                        <li>
                            <h3>1779</h3>
                            <i class="fa fa-arrow-right" aria-hidden="true"></i>
                            <p>
                                Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                                Placeat dolores tenetur est voluptatem enim? Provident recusandae 
                                ipsa dolorem ad sit incidunt repellat magnam adipisci repudiandae a, unde quis minus ut?
                            </p>
                        </li>
                        <li>
                            <h3>1789</h3>
                            <i class="fa fa-arrow-right" aria-hidden="true"></i>
                            <p>
                                Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                                Placeat dolores tenetur est voluptatem enim? Provident recusandae 
                                ipsa dolorem ad sit incidunt repellat magnam adipisci repudiandae a, unde quis minus ut?
                            </p>
                        </li>
                        <li>
                            <h3>1820</h3>
                            <i class="fa fa-arrow-right" aria-hidden="true"></i>
                            <p>
                                Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                                Placeat dolores tenetur est voluptatem enim? Provident recusandae 
                                ipsa dolorem ad sit incidunt repellat magnam adipisci repudiandae a, unde quis minus ut?
                            </p>
                        </li>
                        <li>
                             <h3>1830</h3>
                            <i class="fa fa-arrow-right" aria-hidden="true"></i>
                            <p>
                                Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                                Placeat dolores tenetur est voluptatem enim? Provident recusandae 
                                ipsa dolorem ad sit incidunt repellat magnam adipisci repudiandae a, unde quis minus ut?
                            </p>
                        </li>
                    </ul>
                </div>
            </div>

            <div class="third-section d-flex" id="section3">
                <h1>Section 3</h1>
                <ul id="example-1">
                <li v-for="image in album" :key="image.id">
                    <img v-bind:src='image.thumbnailUrl'>
                </li>
                </ul>

            </div>
        </div>
    </div>
</template>

<script>
import axios from "axios";
import '@fortawesome/fontawesome-free/css/all.css'
import '@fortawesome/fontawesome-free/js/all.js'

export default {
    data : () => ({
        album: null
    }),
  created() {
    axios.get('https://jsonplaceholder.typicode.com/photos?albumId=1').then((result) => {
        this.album = result.data
    })
  }
};
</script>

<style>
    html {
    scroll-behavior: smooth;
    }
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
        /* border-bottom: 1px solid #c7c7c7; */
        /* padding: 0 0 4rem 0; */
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
.text h1, .second-section h1, .third-section h1, .timeline ul li h3{
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
.timeline{
    border-left: 1px solid #d9d9d9;
    padding: 0 0 0 0.9rem;
}
.timeline ul li svg{
    color: #0a527b ;
}
.timeline ul{
    padding: 0;
    color: #b5b5b5;
}
.timeline ul li h3{
    display: inline-block;
    color: #0a527b;
    cursor: pointer;
    padding: 0 1rem 0 0;
}
.timeline ul li p{
    color: #000;
    display: none;
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
