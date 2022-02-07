<template>
    <div class="container" >
        <div class="header">
            <img src="../assets/header.jpg"/>
            <h1>What it's like to travel to Hawaii right now</h1>
            <h4>Free flights to remote workers</h4>
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
                        <li v-on:click="showDetails" class="circle">
                            <h3 style="font-size:23pt" class="top-circle">
                                1778
                            </h3>   
                            <i class="fa fa-arrow-right" aria-hidden="true" style="display:none"></i>            
                            <p id="1778" style="display:block">
                                Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                                Placeat dolores tenetur est voluptatem enim? Provident recusandae 
                                ipsa dolorem ad sit incidunt repellat magnam adipisci repudiandae a, unde quis minus ut?
                            </p>
                        </li>
                        <li v-on:click="showDetails" class="circle-default">
                            <h3>1779</h3>
                            <i class="fa fa-arrow-right" aria-hidden="true"></i>
                            <p id='1779'>
                                Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                                Placeat dolores tenetur est voluptatem enim? Provident recusandae 
                                ipsa dolorem ad sit incidunt repellat magnam adipisci repudiandae a, unde quis minus ut?
                            </p>
                        </li>
                        <li v-on:click="showDetails" class="circle-default">
                            <h3>1789</h3>
                            <i class="fa fa-arrow-right" aria-hidden="true"></i>
                            <p id='1789'>
                                Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                                Placeat dolores tenetur est voluptatem enim? Provident recusandae 
                                ipsa dolorem ad sit incidunt repellat magnam adipisci repudiandae a, unde quis minus ut?
                            </p>
                        </li>
                        <li v-on:click="showDetails"  class="circle-default">
                            <h3>1820</h3>
                            <i class="fa fa-arrow-right" aria-hidden="true"></i>
                            <p id="1820">
                                Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                                Placeat dolores tenetur est voluptatem enim? Provident recusandae 
                                ipsa dolorem ad sit incidunt repellat magnam adipisci repudiandae a, unde quis minus ut?
                            </p>
                        </li>
                        <li v-on:click="showDetails"  class="circle-default">
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

            <div class="third-section section" id="section3">
                <h1>Section 3</h1>
                <Carousel/>

            </div>

        </div>
        <div class="footer">
            <p>All rights reserved.Copyright © 2021</p>
            <ul>
                <li>
                    <a href="#">Sitemap</a>
                </li>
                <li>
                    <a href="#">Terms and conditions</a>
                </li>
                <li>
                    <a href="#">Privacy</a>
                </li>
                <li>
                    <a href="#">Help</a>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
import '@fortawesome/fontawesome-free/css/all.css'
import '@fortawesome/fontawesome-free/js/all.js'
import Carousel from "./Carousel";

export default {
    data : () => ({
        album: [],      
    }),
    components: {
		Carousel
	},
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
            let li = e.currentTarget
            console.log(e.currentTarget)
            if(details.display === 'block' ){
                details.display = 'none'
                title.style.fontSize = '16pt'
                e.target.nextSibling.style.display = 'inline'
                li.classList.remove('circle')
                title.classList.remove('top-circle')
                li.classList.add('circle-default')
            }else{
                details.display = 'block'
                title.style.fontSize = '23pt'
                e.target.nextSibling.style.display = 'none'
                li.classList.remove('circle-default')
                li.classList.add('circle')
                title.classList.add('top-circle')

            }

        }
    },
  created() {
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
        top: 9%;
        left: 5%;
        color: #fff;
        width: 20vw;
        font-family: 'Ibarra Real Nova', serif;
        font-weight: 400;
        font-size: 3vw;
        margin: 0;
    }
     .header h4{
        top: 70%;
        left: 5%;
        color: #fff;
        font-family: 'Ibarra Real Nova', serif;
        font-weight: 400;
        font-size: 1.3vw;
        padding: 1rem 0 0 0;
        margin: 0;
        border-top: 1px solid #e5e2e2;
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
.first-section{
    padding: 0 0 4rem 0;
}
.second-section{
        padding: 1rem 0 2rem 0;
    border-top: 1px solid #ddd;
    border-bottom: 1px solid #ddd;
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

.circle::after {
      content: '';
    position: absolute;
    width: 17px;
    height: 17px;
    left: -24px;
    background-color: #fff;
    border: 1px solid #0a527b;
    top: 38px;
    border-radius: 50%;
    z-index: 1;
}
.top-circle::after{
    content: '';
    position: absolute;
    width: 7px;
    height: 7px;
    left: -18px;
    background-color: #0a527b;
    top: 44px;
    border-radius: 50%;
    z-index: 5;
}
.circle-default::after{
    content: '';
    position: absolute;
    width: 9px;
    height: 9px;
    left: -19px;
    background-color: #ddd;
    top: 30px;
    border-radius: 50%;
    z-index: 5;
}
.third-section{
    padding: 1rem 0;
}
.third-section h1{
    text-align: center;
}
.footer{
    background: #000;
    color: #fff;
    padding: 0 0.7rem;
    display: flex;
}
.footer p {
    display: inline-block;
    width: 50%;
    padding: 0 0 0 5rem;
}
.footer ul{
    list-style: none;
    display: inline-block;
    width: 50%;
}
.footer ul li{
    display: inline-block;
    margin: 0 2rem;
}
.footer ul li a{
    display: inline-block;
    color: #fff;
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
 .header h4{
        padding: 0.6rem 0 0 0;

    }
    .footer {
    display: block;
}
.footer p {
    padding: 0 0 0 1rem;
    text-align: center;
    width: 100%;
}
.footer ul {
    list-style: none;
    width: 100%;
    text-align: center;
    padding: 0;
    margin-top: 0;
}
.footer ul li {
    display: block;
    margin: 0.5rem 0;
}

}

</style>
