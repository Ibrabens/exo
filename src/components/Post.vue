<template>

<div class="card post text-center" style="width: 25rem;">
  <img :src="[getHref]" class="card-img-top" >
  <div class="card-body">
    <h2 class="card-header" style=" font-weight: bold;">{{getTitle}}</h2>
    <h4 class="card-text" style=" font-weight: bold;">{{getDescription}}</h4>
    <p class="card-text">{{getText}}</p>
  </div>
</div>

</template>

<script>
export default {
    data() {
    return {
       posts:
     [
    { id: 1, title : "MongoDB", description : "blabla", text: "un texte plus long", href: "/mongo.png" },
    { id: 2, title : "MySQL", description : "blabla", text: "un texte plus long",href: "/mysql.png" },
    { id: 3,  title : "PHP", description : "blabla", text: "un texte plus long",href: "/php.png" },
    { id: 4,title : "Pyhton", description : "blabla", text: "un texte plus long",href: "/python.png" },
    { id: 5,title : "Docker", description : "blabla", text: "un texte plus long",href: "/docker.jpg" },
     ],
    };
  },


    computed:{
        getTitle(){
            return this.posts.find(item => item.id === parseInt(this.$route.params.id)).title
        },
        getDescription(){
            return this.posts.find(item => item.id === parseInt(this.$route.params.id)).description
        },
        getHref(){
            return this.posts.find(item => item.id === parseInt(this.$route.params.id)).href
        },
         getText(){
            return this.posts.find(item => item.id === parseInt(this.$route.params.id)).text
        },
        
    }
}
</script>

<style scoped>
.post{
    margin: auto;
}
img {
   border-bottom: 1px solid rgb(0, 0, 0);
}
.card{
    border: 3px solid rgb(0, 0, 0)
}
.card-body
{
  background-color: rgb(90, 90, 90);
}
.card-header
{
  background-color: rgb(255, 255, 255);
}
.card-text
{
  margin-top: 15px;
  color: aliceblue;
}
</style>
