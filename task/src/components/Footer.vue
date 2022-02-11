<template>
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
</template>
<style scoped>
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
