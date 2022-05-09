<template>
    <div class="Backdrop">        
        <ul class="animes">
            <li v-for="anime in animes" :key="anime.id">

                <a :href="anime.url"> <img :src="anime.img" :alt="anime.title" class="animeImg"> </a>

                <pre> <p>{{ anime.title }}       {{ anime.author }} </p></pre>

                <p @click="toggleFav(anime)" class="favButton">
                    <span v-if="anime.isFav"><img :src="favIcon" alt="fav"></span>
                    <span v-else><img :src="notFavIcon" alt="notfav"></span>
                </p>

            </li>
        </ul>
    </div>
</template>

<script>
export default {
    data() {
        return {
        favIcon: require("../assets/icons/favHeart.svg"),
        notFavIcon: require("../assets/icons/notFavHeart.svg"),
        animes: [
            {   title: 'Naruto',
                author: 'Masashi Kishimoto',
                img: require("../assets/images/naruto.jpg"),
                url: 'https://en.wikipedia.org/wiki/Naruto',
                info: "Lorem ipsum",
                isFav: true 
            },
            {   title: 'Jujutsu Kaisen',
                author: 'Gege Akutami',
                img: require("../assets/images/jujutsu.jpg"),
                url: 'https://en.wikipedia.org/wiki/Jujutsu_Kaisen',
                info: "Lorem ipsum",

                isFav: true 
            },
            {   title: 'Boruto',
                author: 'Masashi Kishimoto',
                img: require("../assets/images/boruto.jpg"),
                url: 'https://en.wikipedia.org/wiki/Boruto:_Naruto_Next_Generations',
                info: "Lorem ipsum",
                isFav: false 
            },
            {   title: 'Black Clover',
                author: 'Yuki Tabata',
                img: require("../assets/images/blackClover.jpg"),
                url: 'https://en.wikipedia.org/wiki/Black_Clover',
                info: "Lorem ipsum",
                isFav: true 
            },
            {   title: 'One Piece',
                author: 'Eiichiro Oda',
                img: require("../assets/images/onePiece.jpg"),
                url: 'https://en.wikipedia.org/wiki/One_Piece',
                info: "Lorem ipsum",
                isFav: true 
            },
            {   title: 'Tokyo Ghoul',
                author: 'Sui Ishida',
                img: require("../assets/images/tokyoGhoul.jpg"),
                url: 'https://en.wikipedia.org/wiki/Tokyo_Ghoul',
                info: "Lorem ipsum",
                isFav: true 
            }
            ]
        }
    },
    methods: {
        toggleFav(anime) {
            anime.isFav = !anime.isFav
        }
    }
}
</script>

<style>
    .animes {
        padding: 40px;
    }

    .animes li {
        display: inline-block;
        background-color: cornsilk;
        list-style-type: none;
        padding: 10px;
        margin: 5px;
        border: 2px solid #000;
        align-content: center;
        text-align: center;
        transition: 0.5s;
    }

    .animes li:hover {
        padding: 10px;
        margin: 15px;
    }

    .animeImg {
        cursor: pointer;
        width: 350px;
        height: 500px;
        border: 1px solid #000;
        transition: 0.5s;
    }

    .animeImg:hover {
        width: 400px;
        height: 550px;
    }

    .animes li pre {
        margin-top: 0%;
    }

    .animes li p {
        font-size: larger;
        font-weight: 600;
        font-style: oblique;
        font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    }

    .showButtons {
        position: relative;
        display: block;
        left: 50%;
    }

    .favButton span img {
        width: 30px;
    }
</style>
