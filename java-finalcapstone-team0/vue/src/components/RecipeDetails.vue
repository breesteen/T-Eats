<template>
  <div id="body" class = "main">


     <!-- <h1 id='desc'>{{recipe}}</h1> -->
     <!-- <div v-for="(recipe,index) in $store.state.recipes" v-bind:key="index"> -->
          <!-- <li v-for="(instruct, index) in recipe.instructions" :key="index"> -->
    <h1 id= "recipeName" class="recipe-name">{{recipe.recipeName}}</h1>
    <h4 id = "type" class="recipe-type">{{recipe.recipeType}}</h4>
    <h3 id = "descripy" class= "recipe-details">{{recipe.recipeDescription}}</h3>
<div id = "bothII">
    <div id="power-bottom">
    <label id="ingredient-label">
      Ingredients:
      <ul>
        <ul v-for="ingredient in recipe.ingredients" :key="ingredient.index">
          <li id = "ingredient-list"> {{ingredient.quantity}} {{ingredient.unit}} {{ingredient.name}} </li>

          
        </ul>
      </ul>
    </label>
    <label id = "instruction-label">
          Instructions:
      <ul>
        <ul v-for="instruction in recipe.instructions" :key="instruction.index">
        <li id = "instruction-list">{{instruction.stepNumber}}: {{instruction.details}}</li>
          
        </ul>
      </ul>
    </label>
    </div >
    <div class="adjust">
    <!-- <button id = "DeleteButton">Delete</button>&nbsp;
      <router-link
      class="edit-recipe-btn"
      v-bind:to="{ name: 'updateRecipe', params: { id: recipe.id } }"
      tag="button"
      >Edit Recipe</router-link
    > -->
    </div>
     </div>
     </div>
  
</template>

<script>
export default {
  name: 'recipe-details',
 
 computed: {
      recipe(){
        return this.$store.state.recipes.find(recipe => recipe.recipeId === this.$route.params.recipeId);
      }
    }
  }


</script>

<style scoped>

.adjust{
  display: flex;
  margin-top: 1.5%;

}

.ingredient-label ul {
  padding: 0px;
}

#type{
color: rgba(83, 131, 68, 0.404);
margin-top: -2%;
}

#recipeName{
  color: rgb(82, 194, 120);
  padding-top: 8%;
}
#bothII{
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.main {
      background-image: url("../images/BackgroundFood.webp");
      background-repeat: no-repeat;
      background-size: 100% auto;
      min-height: 1000px;
    }
#descripy{
  width: 65%;
  font-weight: normal;
  color: rgb(45, 73, 12);
  font-size:80%;
  padding-bottom: 5%;
}

#body{
  display: flex;
  flex-direction: column;
  align-items: center;
}
#power-bottom{
  display: flex;
  flex-direction: column;
}
#ingredient-label{

text-align: center;
display: flex;
flex-direction: column;
border: 10px solid #71bed1a9;
background-color: rgba(157, 199, 212, 0.336);
border-radius: 10px;
padding-top: 30px;
padding-left: 40px;
padding-right: 40px;
width: 100%;
margin-left: -10px
}

#ingredient-list{
  display: flex;
  flex-direction: row;
 border: 4px solid rgb(255, 255, 255);
  border-radius: 10px;
  padding-top: 10px;
  padding-left: 40px;
  padding-right: 40px;
  padding-bottom: 10px;
  align-content: flex-start;
  width: 80%;
  justify-content: center;
}

#instruction-label{
  border: 10px solid rgba(113, 190, 209, 0.664);
  background-color: rgba(157, 199, 212, 0.336);
  border-radius: 10px;
  padding-top: 30px;
  padding-left: 40px;
  padding-right: 40px;
  /* margin-left: 100px; */
  width: 100%;
  color: rgb(45, 73, 12);
  margin-top: 10%;
  justify-content: center;
}

#instruction-list{
  display: flex;
  border: 4px solid rgb(255, 255, 255);
  flex-direction: row;
  border-radius: 10px;
  padding-top: 10px;
  padding-left: 50px;
  padding-right: 40px;
  padding-bottom: 10px;
  width: 500px;
}
</style>