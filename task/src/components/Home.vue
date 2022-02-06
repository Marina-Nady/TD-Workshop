<template>
    <div class="container" >
        <div class="header">
            <img src="../assets/header.jpg"/>
            <!-- <h1>What it's like to travel to Hawaii right now</h1>
            <hr/>
            <h4>Free flights to remote workers</h4> -->
        </div>
        <div class="nav-bar">
            <ul class="d-flex" id="navbar">
                <a href="#section1" class="flex-item active nav-item links" v-on:click="active">
                    <li>
                        Section 1
                    </li>
                </a>
                <a href="#section2" class="flex-item nav-item links"  v-on:click="active">
                    <li>
                        Section 2
                    </li>
                </a>
                <a href="#section3" class="flex-item nav-item links"  v-on:click="active">
                    <li>
                        Section 3
                    </li>
                </a>
            </ul>
        </div>
        <div class="content">
            <div class="first-section d-flex section" id="section1">
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
            <div class="second-section section" id="section2">
                <h1>Section 2</h1>
                <div class="timeline">
                    <ul>
                        <li v-on:click="showDetails">
                            <i class="fas fa-circle bullet"></i>
                            <i class="far fa-dot-circle bullet-dot"></i>
                            <h3>1778</h3>   
                            <i class="fa fa-arrow-right" aria-hidden="true"></i>            
                            <p id="1778">
                                Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                                Placeat dolores tenetur est voluptatem enim? Provident recusandae 
                                ipsa dolorem ad sit incidunt repellat magnam adipisci repudiandae a, unde quis minus ut?
                            </p>
                        </li>
                        <li v-on:click="showDetails">
                            <i class="fas fa-circle bullet"></i>
                            <i class="far fa-dot-circle bullet-dot"></i>
                            <h3>1779</h3>
                            <i class="fa fa-arrow-right" aria-hidden="true"></i>
                            <p id='1779'>
                                Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                                Placeat dolores tenetur est voluptatem enim? Provident recusandae 
                                ipsa dolorem ad sit incidunt repellat magnam adipisci repudiandae a, unde quis minus ut?
                            </p>
                        </li>
                        <li v-on:click="showDetails">
                            <i class="fas fa-circle bullet"></i>
                            <i class="far fa-dot-circle bullet-dot"></i>
                            <h3>1789</h3>
                            <i class="fa fa-arrow-right" aria-hidden="true"></i>
                            <p id='1789'>
                                Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                                Placeat dolores tenetur est voluptatem enim? Provident recusandae 
                                ipsa dolorem ad sit incidunt repellat magnam adipisci repudiandae a, unde quis minus ut?
                            </p>
                        </li>
                        <li v-on:click="showDetails">
                            <i class="fas fa-circle bullet"></i>
                            <i class="far fa-dot-circle bullet-dot"></i>
                            <h3>1820</h3>
                            <i class="fa fa-arrow-right" aria-hidden="true"></i>
                            <p id="1820">
                                Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                                Placeat dolores tenetur est voluptatem enim? Provident recusandae 
                                ipsa dolorem ad sit incidunt repellat magnam adipisci repudiandae a, unde quis minus ut?
                            </p>
                        </li>
                        <li v-on:click="showDetails">
                            <i class="fas fa-circle bullet"></i>
                            <i class="far fa-dot-circle bullet-dot"></i>
                             <h3>1830</h3>
                            <i class="fa fa-arrow-right" aria-hidden="true"></i>
                            <p id='1830'>
                                Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                                Placeat dolores tenetur est voluptatem enim? Provident recusandae 
                                ipsa dolorem ad sit incidunt repellat magnam adipisci repudiandae a, unde quis minus ut?
                            </p>
                        </li>
                    </ul>
                </div>
            </div>

            <div class="third-section d-flex section" id="section3">
                <h1>Section 3</h1>
            <div  v-for="image in album" :key="image.id"> 
                    <img v-bind:src='image.thumbnailUrl'>
            </div>
                <!-- <ul id="example-1">
                <li v-for="image in album" :key="image.id">
                    <img v-bind:src='image.thumbnailUrl'>
                </li>
                </ul> -->

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
        album: [],      
    }),
    methods : {
        active : function(e){
            let nav = document.getElementsByClassName('nav-item')
            for(let i=0 ; i < nav.length ; i++){
                nav[i].classList.remove('active')
            }
            e.currentTarget.classList.add('active')
        },
        handleScroll : function(){
            const links = document.querySelectorAll('.links');
            const sections = document.querySelectorAll('.section');

            let index = sections.length;

            while (index > 0 && window.scrollY + 50 < sections[index-1].offsetTop) {
                --index
                links.forEach((link) => link.classList.remove('active'));
                links[index].classList.add('active');

            }
        },
        showDetails : function(e){
            let year = e.target.innerText
            let title = e.target
            let details = document.getElementById(year).style
            let bullet = e.currentTarget.firstChild
            let bulletDot = bullet.nextElementSibling
            if(details.display === 'block' ){
                details.display = 'none'
                title.style.fontSize = '16pt'
                e.target.nextSibling.style.display = 'inline'
                bullet.style.display = 'inline'
                bulletDot.style.display = 'none'
            }else{
                details.display = 'block'
                title.style.fontSize = '23pt'
                e.target.nextSibling.style.display = 'none'
                bullet.style.display = 'none'
                bulletDot.style.display = 'inline'

            }

        }
    },
  created() {
    axios.get('https://jsonplaceholder.typicode.com/photos?albumId=1').then((result) => {
        this.album = result.data
    })
    window.addEventListener("scroll", this.handleScroll);

  },
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
    .nav-bar{
        position: sticky;
        top: 0;
        z-index: 9999;
    }
  .nav-bar ul a{
        text-decoration: none;
        color: #515151;
    }
    .nav-bar ul {
        list-style: none;
        text-align: center;
        padding: 0;
        margin: 0;
    }
    .nav-bar ul li{
        cursor: pointer;
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
    list-style: none;
}
.timeline ul li{
    position: relative;
}
.timeline ul li h3{
    display: inline-block;
    color: #0a527b;
    cursor: pointer;
    padding: 0 1rem 0 0;
    font-size: 16pt;

}
.timeline ul li p{
    color: #000;
    display: none;
}
.bullet{
    position: absolute;
    top: 38%;
    left: -1.5%;
    color: #ddd !important;
    font-size: 7pt;
    display: inline;
}
.bullet-dot{
    position: absolute;
    top: 27%;
    left: -1.9%;
    display: none;
    font-size: 14pt;

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
.bullet{
    top: 42%;
    left: -6.5%;
}
.bullet-dot{
    top: 18%;
    left: -7.9%;

}
}

</style>
