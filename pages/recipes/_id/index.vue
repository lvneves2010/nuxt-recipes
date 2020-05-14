<template>
    <section class="single-recipe">
        <h1> {{ recipe.title }} </h1>
        <div>
            <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title">
        </div>
        <p> {{ recipe.descriptionText }} </p>
    </section>
</template>

<script>
export default {
    asyncData(context) {
        return new Promise((res, err) => {
            setTimeout(() => {
                res({
                    recipe: [
                        {
                            id:'1',
                            title: 'Feijoada',
                            previewText: 'receita de feijoada fácil e rápida',
                            descriptionText: 'Aqui vai a receita completa',
                            thumbnail: 'https://redesuldenoticias.com.br/content/uploads/2018/05/feijoada-receita-1024x651.jpg'
                        },
                        {
                            id:'2',
                            title: 'Macarrão ao Vongole',
                            previewText: 'Deliciosa receita de macarrão com frutos do mar',
                            descriptionText: 'Aqui vai a receita completa',
                            thumbnail: 'https://www.comidaereceitas.com.br/wp-content/uploads/2010/07/espaguete_molho_vongole.jpg'
                        }
                    ].find(el => el.id === context.params.id)
                })
            }, 1500 )
        } )
    },

}
</script>

<style scoped>
.single-recipe {
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 30px;
}

.recipe-image {
    width: 40%;
}
</style>