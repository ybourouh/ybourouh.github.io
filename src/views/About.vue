<template>
  <div style="margin-bottom: 80px;">
    <h1>Hello!</h1>
    
    <div class="paragraph">
      <div>
        I'm <strong>Yanis Bourouh</strong>, a computer graphics student, game developper and artist.<br/>
        I enjoy talking about the process of making games and art, and I like to share my knowledge and experience with others when I can.
      </div>

      <div style="margin-top: 20px;">I've worked on multiple <router-link to="/game-projects">projects</router-link>, ranging from 3D softwares to commercial and non-commercial games.</div>

      <div style="margin-top: 40px;">I'm <strong>currently looking for an internship</strong> as a game developer. You can reach me at <a href="mailto:yanis.bourouh@gmail.com">yanis.bourouh@gmail.com</a> or <router-link to="/contact">through here</router-link>.</div>
    
    </div>
    <div class="photo">
      <img src="img/avatar.png" alt="Avatar of Yanis" /> 
    </div>

    <div style="clear:both"></div>

  </div>
</template>

<style scoped>
.paragraph {
  max-width: 700px;
  margin-bottom: 20px;
}

.photo {
  margin-top: 10px;
  text-align: center;
}

@media only screen and (min-width: 620px){
  .paragraph {
    float: left;
  }

  .photo {
    float: left;
    padding: 10px;
    padding-left: 80px;
  }
}

</style>