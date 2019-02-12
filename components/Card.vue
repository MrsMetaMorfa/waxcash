<template>
    <div v-show="!(loggedFirst)" onclick="this.classList.toggle('selected')" class="card">
        <div class="line container container--justify">
            <div v-show="productTypeVGO && !productSale" class="shabbiness">FN</div>
            <div v-show="(productTypeShoes || productTypeWears) && !productSale" class="size">9.5</div>
            <div v-show="(productTypeElectronics || productTypeStickers) && !productSale" class="indicator">
                <img src="~assets/images/electron.png" alt=""></div>
            <div v-show="productSale" class="sale-size container">
                <img src="~assets/icons/sale2.svg" alt="Sale"> -{{ productSaleSize }}%
            </div>

            <div class="quantity">x7</div>
        </div>

        <div class="line product-image">
            <img src="~assets/images/skin1.png" alt="">
        </div>

        <p class="title">AK-47 | Bloodsport</p>
        <p class="price">$ 278.43</p>

        <div class="block-selected">
            <img src="~assets/images/select.png" alt="">
            <p>Выбрано</p>
        </div>
    </div>

</template>

<script>
    export default {
        name: "Card",
        props: {
            loggedFirst: {
                type: Boolean,
                required: true
            },
            productTypeVGO: {
                type: Boolean,
                required: false
            },
            productTypeWears: {
                type: Boolean,
                required: false
            },
            productTypeShoes: {
                type: Boolean,
                required: false
            },
            productTypeElectronics: {
                type: Boolean,
                required: false
            },
            productTypeStickers: {
                type: Boolean,
                required: false
            },
            productSale: {
                type: Boolean,
                required: false,
            },
            productSaleSize: {
                type: Number,
                required: false
            },
            productHighPrice: {
                type: Boolean,
                required: false
            },
            productSelected: {
                type: Boolean,
                required: false
            },
        },
    }
</script>

<style lang="less">
    .card {
        position: relative;
        background-color: rgb(39, 41, 56);
        border-radius: 2px;
        padding: 14px;
        margin: 0 7px 14px;
        display: flex;
        flex-direction: column;
        cursor: pointer;
        flex-grow: 1.5;
        flex-shrink: 0.5;
        flex-basis: 160px;
        .line {
            margin-bottom: 14px;
            padding: 0!important;
            div {
                line-height: 25px;
            }
            img {
                margin: 0 auto;
                max-width: 100%;
            }
            &.image {
                 margin: auto 0;
            }
            &.product-image {
                img {
                    filter: drop-shadow(0 7px 4px rgba(0,0,0,.75));
                }
            }
        }
        p {
            text-align: center;
            font-size: 15px;
            margin-bottom: 7px;
            &.title {
                color: #cddaec;
            }
            &.price {
                color: #37d759;
                font-weight: 700;
            }
        }
        .block-selected {
            visibility: hidden;
            opacity: 0;
            position: absolute;
            top: 0;
            bottom: 0;
            left: 0;
            right: 0;
            text-align: center;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            border: 2px solid transparent;
            border-radius: 2px;
            background: rgba(39,41,56,.85);
            border-image: linear-gradient(-128deg, #08aeea 0%, #2af598 100%);
            border-image-slice: 1;
            transition: all 0.15s ease-out;
            svg {
                height: 30px;
                margin-bottom: 14px;
                path {
                    fill: white;
                }
            }
        }
        &.sale {
             background: url("~assets/images/card-bg-sale.jpg") no-repeat center;
             background-size: cover;
            .line {
                .sale-size {
                    padding: 0!important;
                    font-size: 19px;
                    font-family: "MarkPro", sans-serif;
                    font-weight: 700;
                    color: #00B7CF;
                    line-height: 23px;
                    text-align: center;
                    align-items: flex-start;
                    margin-top: 1px;
                    text-shadow: 1px -1px 1px #066b91,
                                 1px -1px 1px #066b91,
                                 -1px 1px 1px #066b91,
                                 -1px 1px 1px #066b91,
                                 2px -2px 1px #066b91,
                                 2px -2px 1px #066b91,
                                 -2px 2px 1px #066b91,
                                 -2px 2px 1px #066b91;
                    img {
                        width: 25px;
                        height: 25px;
                    }
                }
            }
        }
        &.high_price {
             background: url("~assets/images/card-bg-high.jpg") no-repeat center;
             background-size: cover;
         }
        &.shoes, &.wears {
            p.price {
                color: #22d3fd;
            }
        }
        &.electronics, &.stickers {
            p.price {
                color: #ffe33b;
            }
            &.high_price {
                 background-image: url("~assets/images/card-bg-high2.jpg")
            }
        }
        &.selected {
            .block-selected {
                visibility: visible;
                opacity: 1;
            }
        }
    }
    @media screen and (max-width: 480px) {
        .card {
            flex-basis: 125px;
        }
    }
</style>