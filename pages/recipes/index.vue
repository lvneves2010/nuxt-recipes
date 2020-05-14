<template>
  <section class="recipes">
      <Recipe
      v-for="recipe in recipes" :key="recipe.id"
      :id="recipe.id"
      :title="recipe.title"
      :previewText="recipe.previewText"
      :thumbnail ="recipe.thumbnail"  />
  </section>
</template>

<script>
import Recipe from '../../components/Recipe'

export default {
    components: { Recipe },
    asyncData() {
        return new Promise((res, err) => {
            setTimeout(() => {
                res({
                    recipes: [
                        {
                            id:'1',
                            title: 'Feijoada',
                            previewText: 'receita de feijoada fácil e rápida',
                            thumbnail: 'https://redesuldenoticias.com.br/content/uploads/2018/05/feijoada-receita-1024x651.jpg'
                        },
                        {
                            id:'2',
                            title: 'Macarrão ao Vongole',
                            previewText: 'Deliciosa receita de macarrão com frutos do mar',
                            thumbnail: 'https://www.comidaereceitas.com.br/wp-content/uploads/2010/07/espaguete_molho_vongole.jpg'
                        }
                    ]
                })
            }, 1500 )
        } )
    },
}
</script>

<style scoped>
.recipes {
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    align-items: center;
}
</style>