
<template>
    <section class="catalog_wrapper">
        <div class="catalog_top_container">
            <h3>Catalog</h3>
            <div class="catalog_products_container">
                <div class="catalog_product">
                    <img src="@/assets/img/1trapeciya-1.png">
                    <p>Trapezoid rule</p>
                </div>
                <div class="catalog_product">
                     <img src="@/assets/img/1trapeciya-1.png">
                    <p>Rectangular rule</p>
                </div>
                <div class="catalog_product">
                     <img src="@/assets/img/1trapeciya-1.png">
                    <p>Aluminum levels</p>
                </div>
                <div class="catalog_product">
                     <img src="@/assets/img/1trapeciya-1.png">
                    <p>Construction triangle</p>
                </div>
                <div class="catalog_product">
                     <img src="@/assets/img/1trapeciya-1.png">
                    <p>Aluminum construction ruler</p>
                </div>
            </div>
        </div>
        <hr>
        <section class="catalog_filter_wrapper">
            <div class="catalog_filter">
                <h3>Filter</h3>
                <div class="filter_category">
                    <ul>
                        <li class="category">Trapezoid rule</li>
                        <li class="category">Rectangular rule</li>
                        <li class="category">Aluminum levels</li>
                        <li class="category">Construction triangle</li>
                        <li class="category">Aluminum construction ruler</li>
                    </ul>
                     <hr>
                </div>
                <h3>Subcategory</h3>
            </div>
            <div class="catalog_results">
                <div class="results_search">
                    <h3>Results</h3>
                    <div class="search">
						<div class="search-wrapper">
							<input type="text"  v-model="search" placeholder="Search title.."/>
						</div>
						<!-- <div class="search-btn">
							<button>Search</button>
						</div> -->
					</div>
                </div>
                <div class="results">
                     <!-- <div class="product_card" v-for="post in filteredList" :key="post">
                         <a v-bind="post.link" target="_blank">
                             <img v-bind:src='post.img'/>
                             <p>{{post}}</p>
                         </a>
                     </div>    -->
                     <div class="catalog_product" v-for="post in postList" key="post">
                         {{ Post }}
                     </div>
                </div>
            </div>
        </section>
    </section>
</template>

<script>
import catalogfilter from '@/services/catalogfilter'
export default {

    head: {
        title: 'Catalog page 🚀'
    },

    
    data: () =>({

        search: '',
        postList : [
                 post(
                    'Vue.js', 
                    'https://vuejs.org/', 
                    'Chris', 
                    'https://vuejs.org//images/logo.png'
                ),
                 Post(
                    'React.js', 
                    'https://facebook.github.io/react/', 
                    'Tim',
                    'https://daynin.github.io/clojurescript-presentation/img/react-logo.png'
                ),
                
        ]
    })


}
   

</script>

<style scoped>
.catalog_products_container {
    display: flex;
    justify-content: space-between;
}
.catalog_product {
   text-align: center;
   /* margin-right: 10px; */
}

ul {
    list-style-type:none;
    padding: 0;

}

.catalog_filter_wrapper {
    display: flex;
    justify-content: space-between;
}

.catalog_filter {
    flex-grow: 1;
}

.filter_category hr{
    width: 52%;
}

.catalog_results {
    flex-grow: 2;
}

.results_search {
    display: flex;
    justify-content: space-between;
}
.search{
    display: flex;
}

.results {
    display: grid;
    /* grid-template-columns: 1fr 1fr 1fr 1fr; */
    grid-template-areas: "catalog_product catalog_product catalog_product catalog_product"
                         "catalog_product catalog_product catalog_product catalog_product";   
}   
</style>