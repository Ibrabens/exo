<template>
   <div id="show-posts">
        <h1>All Posts</h1>
        <div v-for="post in posts" class="single-post">
            <router-link v-bind:to="'/post/' + post.id"><h2>{{ post.title }}</h2></router-link>
        </div>
    </div>
</template>

<script >

export default {
    data () {
        return {
          posts: [
             { id: 1, title : "MongoDB", description : "blabla", text: "un texte plus long" },
           { id: 2, title : "MySQL", description : "blabla", text: "un texte plus long" },
           { id: 3,  title : "PHP", description : "blabla", text: "un texte plus long" },
         { id: 4,title : "Pyhton", description : "blabla", text: "un texte plus long" },
         { id: 5,title : "Docker", description : "blabla", text: "un texte plus long" },
          ],
        }
    },
    
}



</script>

<style scoped>
#show-posts{
    max-width: 800px;
    margin: 0px auto;
}
.single-post{
    padding: 20px;
    margin: 20px 0;
    box-sizing: border-box;
    background: #eee;
}

#show-post a{
    color: #444;
    text-decoration: none;
}
</style>
