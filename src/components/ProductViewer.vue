<template>
    <div class="product-viewer">
        <div class="big-item" ref="container">
            <a href="#">
                
                <vue-h-zoom :image="images[currentItem]"
  :image-full="images[currentItem]"
  :zoom-level="2"></vue-h-zoom>
                <!-- <img ref="img" :src="images[currentItem]" @mousemove="zoomIn($event); previewActive = true" @mouseleave="coord = '50% 50%'; previewActive = false"> -->
                
            </a>
        </div>
        <div class="items">

            <a href="#" v-for="(i, index) in images" :style="{backgroundImage: 'url(' + i + ')'}" @click.prevent="currentItem = index" :class="{'is-active': currentItem == index }"></a>
        </div>
        <transition name="fade">
        
        </transition>
    </div>
</template>


<script>
    /**
     * Componente creado por Ignacio Del Nardo
     * contacto ignacioguerra111@gmail.com
     */
    export default {
        props: {
            images: {
                required: true,
                type: Array
            }
        },
        data: () => ({
            currentItem: 0,
            coord: '50% 50%',
            previewActive: false,
        }),
        methods: {
            zoomIn(e) {
                let img = this.$refs.img;
                let offset = img.getBoundingClientRect();
                let posX = - (e.pageX  - offset.left);
                let posY = - (e.pageY - offset.top);
                this.coord = `${Math.round(posX)}px ${Math.round(posY)}px`;
            },
        }
    }
</script>
<style lang="scss" scoped>
    .product-viewer {
        line-height: 0;
        font-size: 0;
        background: #eee;
        border: 5px solid #eee;
        border-radius: 3px;
        position: relative;
        margin: 0 25px 15px 0;
     //   overflow: hidden;
        max-width: 90%;
        .preview {
            position: absolute;
            width: 100%;
            height: 100%;
            left: 103%;
            top: 0;
            border: 5px solid #eee;
            border-radius: 3px;
            overflow: hidden;

            .preview-img {
                display: block;
                width: 100%;
                height: 100%;
                background-position: center center;
                background-repeat: no-repeat;
                transition: all ease-out .3s;
                transform: scale(1.1);
            }

        }
        .items {
            display: inline-flex;
            flex-direction: row;

            .is-active {
                opacity: 1 !important;
                position: relative;
            }
            a:link,
            a:visited {
                width: 50px;
                height: 50px;
                overflow: hidden;
                opacity: .3;
                display: inline-flex;
                justify-content: left;
                align-items: center;
                background-size: cover;
                background-position: center;
                transition: all .2s ease-out;
            }
        }
        .big-item {
            //position: relative;
        //    overflow: hidden;
            
            a {
                
                img:hover {
                    cursor: crosshair;

                }
            }
        }
    }
    .fade-enter-active, .fade-leave-active {
        transition: opacity .5s
    }
    .fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
        opacity: 0
    }

</style>