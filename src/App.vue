<template>
  <div id="app">
    <header>
      <h1>
        <router-link to="/" >
          Intro to Coding For Designers
        </router-link>
      </h1>
      <nav>
        <ul>
          <li>
           <router-link :to="{ name: 'list', params: { list: 'about' }}" >
            About
          </router-link> 
          </li>
          <li>
           <router-link :to="{ name: 'list', params: { list: 'lectures' }}" >
            Lectures
          </router-link> 
          </li>
          <li>
           <router-link :to="{ name: 'list', params: { list: 'assignments' }}" >
            Assignments
          </router-link> 
          </li>
          <li>
           <router-link :to="{ name: 'list', params: { list: 'students' }}" >
            Students
          </router-link> 
          </li>
          <li>
           <router-link :to="{ name: 'list', params: { list: 'resources' }}" >
            Resources
          </router-link> 
          </li>
        </ul>
      </nav>
    </header>
    
    <router-view :link="link"></router-view>
    <router-view name="demos"></router-view>
    <router-view name="list"></router-view>
    <router-view name="assignments"></router-view>
  </div>
</template>

<script>


export default {
  name: 'app',
  data: function(){
    return {
      link: [
      "Syllabus",
      "/PUCD_2126_I_Eigler-Harding_SP20.pdf"
      ]
    }
  },
  components: {
    
  }
}
</script>

<style>

*{
  padding: 0;
  margin: 0;
}

html, body{
  width: 100%;
  font-size: 15px;
}

@media(max-width: 768px){
  html, body{
    font-size: 11px;
  }
}

@media(min-width: 1600px){
  html{
    font-size: 1vw;
  }
}

#app {
  font-family: 'Arial Rounded', Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
}

ul{
  list-style: none;
}

h1{
  margin-top: 0.5rem;
}


small{
  font-size: 1.25rem;
}

header{
  position: sticky;
  top: 0;
  background-color: rgba(255,255,255,0.9);
  padding-bottom: 0.5rem;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}

header h1{
  flex-basis: 50%;
  padding-left: 0.5rem;
  padding-right: 0.5rem;
  box-sizing: border-box;
  text-align: right;
  margin-right: 0;
  margin-left: 0;
}

header nav{
  margin-top: 1rem;
  flex-basis: 100%;
}

header nav ul{
  display: flex;
  flex-wrap: wrap;
}

header nav ul li{
  margin-right: 0.5rem;
  margin-bottom: 0.25rem;
}

@media(max-width: 768px){
  header{
    flex-wrap: wrap;
  }
  header h1{
    flex-basis: 100%;
  }
}

header h1:first-of-type{
  text-align: left;
}

h1, h2, h3, h4, p, ul{
  margin-left: 0.5rem;
  font-weight: normal;
  font-size: 2rem;
  letter-spacing: -1px;
  line-height: 1.3;
}

p + h1, p + h2, p + h3,
ul + h1, ul + h2, ul + h3, pre + h2, pre + h3{
  margin-top: 2rem;
}

p + h4, ul + h4{
  margin-top: 1rem;
}

p + p{
  text-indent: 2rem;
}

a{
  color: #FC1D95;
  background-color: white;
  box-sizing: border-box;
  border: solid 1px #00F2B8;
  padding-left: 0.25rem;
  padding-right: 0.25rem;
  text-decoration: none;
}

a.router-link-exact-active{
  background-color: #FCA31D;
  border: solid 1px #FC1D95;
  color: white;
}

@media(any-hover: hover){
  a:hover{
    background-color: #FCA31D;
    color: white;
  }

  header h1:not(:first-of-type) a:hover{
    background-color: pink;
    color: white; 
  }
}

main{
    margin: 0 auto;
    margin-top: 1rem;
    width: calc(100% - 1rem);
  }


@media(max-width: 768px){
  main{
    width: calc(100% - 1.5rem);
  } 
}

.Post{
  margin-top: 2rem;
  padding-bottom: 4rem;
  border-top: 1px solid #00F2B8;
}

.Post button{
  cursor: pointer;
  margin-top: 0.5rem;
  margin-bottom: 0.5rem;
  -webkit-appearance: none;
  -moz-appearance: none;
  border: solid 2px black;
  color: white;
  background-color: black;
  border-radius: 0.3rem;
  padding: 0.25rem;
  font-size: 2rem;
  font-family: arial;

}

.Post h1, .Post h2, .Post h3, .Post h4, .Post h5,
.Post p, .Post ul, .Post ol, .Post pre{
  max-width: 60rem;
}

  .Post .presentation{
    min-height: 80vh;
    box-sizing: border-box;
    border: solid 1px #FCA31D;
    padding: 1rem;
    margin-bottom: 1rem;
  }

  .Post img{
    max-width: 30rem;
    width: 100%;
    margin-top: 1rem;
    margin-bottom: 1rem;

  }

  @media(max-width: 768px){
    .Post img{
      max-width: 100%;
    }
  }

  @media(any-hover: hover){
    .Post img:hover{
      position: fixed;
      max-width: 100%;
      width: 90vw;
      height: 97vh;
      box-sizing: border-box;
      background-color: white;
      border: solid 1px black;
      padding: 2rem;
      object-fit: contain;
      object-position: center;
      bottom: 0;
      left: 0;
      right: 0;
      margin-left: auto;
      margin-right: auto;
    }
  }


  .Post p + p img{
    margin-left: -2rem;
  }


  .Post h1{
    text-transform: uppercase;
    color: #FC1D95;
  }

  .Post h2{
    text-transform: uppercase;
    color: #FCA31D;
    text-indent: 2rem;
  }

  .Post h3{
    text-transform: uppercase;
    text-indent: 2rem;
  }

  .Post h4{
    color: #FCA31D;
    text-indent: 2rem;
  }

  .Post blockquote{
    margin-left: 2rem;
    margin-top: 1rem;
    margin-bottom: 1rem;
    color: gray;
  }


  .Post ul{
    margin-top: 1rem;
    margin-bottom: 2rem;
  }

  .Post h2 + ul, .Post h3 + ul{
    margin-top: 0;
  }

  .Post ul ul{
    margin-top: 0;
    margin-bottom: 0; 
    margin-left: 1.75rem;
  }

  .Post ul li:before{
    content: "✺";
    color: #FCA31D;
    margin-right: 0.25rem;
  }

  .Post ul li:nth-of-type(2n + 1):before{
    content: "✹";
    color: #FC1D95;
  }

  .Post ul li:nth-of-type(3n):before{
    content: "✦";
    color: #00F2B8;
  }

  @media(max-width: 768px){
    .Post li{
      margin-bottom: 0.25rem;
    }
  }

  .Post pre{
    box-sizing: border-box;
    background-color: lavender;
    padding: 0.5rem;
    padding-top: 1.5rem;
    padding-bottom: 2rem;
    padding-left: 1rem;
    margin-top: 0.5rem;
    margin-bottom: 0.5rem;
    border-radius: 0.25rem;
    white-space: pre-wrap;       /* Since CSS 2.1 */
    white-space: -moz-pre-wrap;  /* Mozilla, since 1999 */
    white-space: -pre-wrap;      /* Opera 4-6 */
    white-space: -o-pre-wrap;    /* Opera 7 */
    word-wrap: break-word;     
    max-width: 60rem;
  }

  
  .Post code{
    font-size: 1.25rem;
    background-color: lavender;
    padding-left: 0.5rem;
    padding-right: 0.5rem;
    border-radius: 0.25rem;
  }

  .Post pre code{
    padding: 0;
    border-radius: none;
    overflow-wrap: break-word;
    word-break: break-all;

  }

  .Post hr{
    border: none;
    height: 1px;
    background-color: #00F2B8;
    max-width: 60rem;
    margin-top: 4rem;
    margin-bottom: 2rem;
  }

</style>
