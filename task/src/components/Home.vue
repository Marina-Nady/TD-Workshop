<template>
    <div class="page" >
        <Header/>
        <div class="nav-bar">
            <ul class="dis-flex" id="navbar">
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
            <div class="section container-fluid px-0 pb-5 pt-2" id="section1">
                <FirstSection/>
            </div>
            <div class="second-section section" id="section2">
                <SecondSection/>
            </div>

            <div class="third-section section" id="section3">
                <h1>Section 3</h1>
                <Carousel/>
            </div>
        </div>
        <Footer/>
    </div>
</template>

<script>
import '@fortawesome/fontawesome-free/css/all.css'
import '@fortawesome/fontawesome-free/js/all.js'
import Carousel from "./Carousel";
import Header from './Header.vue'
import FirstSection from './FirstSection.vue'
import SecondSection from './SecondSection.vue'
import Footer from './Footer.vue'

export default {
    data : () => ({
        album: [],      
    }),
    components: {
		Carousel,
        Header,
        FirstSection,
        SecondSection,
        Footer
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

            while (index > 0 && window.scrollY < sections[index-1].offsetTop) {
                --index
                links.forEach((link) => link.classList.remove('active'));
                links[index].classList.add('active');

            }
        },
    },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  },
};
</script>

<style>
    html {
    scroll-behavior: smooth;
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
    .dis-flex{
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
    .second-section{
        padding: 2rem 0;
        border-top: 1px solid #ddd;
        border-bottom: 1px solid #ddd;
    }
    .third-section h1{
        font-family: 'Merriweather', serif;
        text-align: center;
        margin-bottom: 2rem;
    }
    .third-section{
        padding: 2rem 0 0 0;
    }
    @media (max-width: 800px) {
    .flex-item {
        flex: 100%;
    }
    .content {
        padding: 2rem;
    }
    .header h4{
            padding: 0.6rem 0 0 0;
        }
    }

</style>
