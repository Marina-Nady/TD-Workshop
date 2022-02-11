<template>
  <h1>Section 2</h1>
  <div class="timeline">
    <ul>
      <li>
        <h3 v-on:click="showDetails" class="circle circle-default title">1778</h3>
        <i class="fa fa-arrow-right hidden" aria-hidden="true"></i>
        <p id="1778" class="hidden visible">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Placeat
          dolores tenetur est voluptatem enim? Provident recusandae ipsa dolorem
          ad sit incidunt repellat magnam adipisci repudiandae a, unde quis
          minus ut?
        </p>
      </li>
      <li>
        <h3 v-on:click="showDetails" class="circle-default">1779</h3>
        <i class="fa fa-arrow-right" aria-hidden="true"></i>
        <p id="1779" class="hidden">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Placeat
          dolores tenetur est voluptatem enim? Provident recusandae ipsa dolorem
          ad sit incidunt repellat magnam adipisci repudiandae a, unde quis
          minus ut?
        </p>
      </li>
      <li>
        <h3 v-on:click="showDetails" class="circle-default">1789</h3>
        <i class="fa fa-arrow-right" aria-hidden="true"></i>
        <p id="1789" class="hidden">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Placeat
          dolores tenetur est voluptatem enim? Provident recusandae ipsa dolorem
          ad sit incidunt repellat magnam adipisci repudiandae a, unde quis
          minus ut?
        </p>
      </li>
      <li>
        <h3 v-on:click="showDetails" class="circle-default">1820</h3>
        <i class="fa fa-arrow-right" aria-hidden="true"></i>
        <p id="1820" class="hidden">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Placeat
          dolores tenetur est voluptatem enim? Provident recusandae ipsa dolorem
          ad sit incidunt repellat magnam adipisci repudiandae a, unde quis
          minus ut?
        </p>
      </li>
      <li>
        <h3 v-on:click="showDetails" class="circle-default">1830</h3>
        <i class="fa fa-arrow-right" aria-hidden="true"></i>
        <p id="1830" class="hidden">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Placeat
          dolores tenetur est voluptatem enim? Provident recusandae ipsa dolorem
          ad sit incidunt repellat magnam adipisci repudiandae a, unde quis
          minus ut?
        </p>
      </li>
    </ul>
  </div>
</template>
<script>
import '@fortawesome/fontawesome-free/css/all.css'
import '@fortawesome/fontawesome-free/js/all.js'

export default {
    methods : {
        showDetails : function(e){
            let year = e.target.innerText
            let title = e.target
            let details = document.getElementById(year)
            let arrow = e.target.nextSibling
            details.classList.toggle('visible')
            arrow.classList.toggle('hidden')
            title.classList.toggle('title')
            title.classList.toggle('circle')
        }
    },
};
</script>

<style scoped>
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
    margin: 0.5rem 0;
}
.title{
    font-size: 23pt !important;
}
.timeline ul li p{
    color: #000;
    /* display: none; */
}
.circle-default::before{
    content: '';
    position: absolute;
    width: 9px;
    height: 9px;
    left: -19px;
    background-color: #ddd;
    top: 15px;
    border-radius: 50%;
    z-index: 5;
}
.circle::before {
    content: '';
    position: absolute;
    width: 17px;
    height: 17px;
    left: -23px;
    background-color: #fff;
    border: 1px solid #0a527b;
    top: 18px;
    border-radius: 50%;
    z-index: 1;
}
.circle::after{
    content: '';
    position: absolute;
    width: 7px;
    height: 7px;
    left: -18px;
    background-color: #0a527b;
    top: 23px;
    border-radius: 50%;
    z-index: 5;
}
table{
    border-spacing: 1rem;
}
h1, .timeline ul li h3{
    font-family: 'Merriweather', serif;
}
.visible{
  display: block !important;
}
.hidden{
  display: none;
}
.first{
  display: inline-block;
}
</style>
