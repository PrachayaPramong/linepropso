<template>
    <v-card class="mx-auto" :class="active === true ? 'active': ''" max-width="390">
        <v-img class="white--text align-end" height="200px" :src="session.image"> 
            <div class="more-detail" @click="$emit('moreDetail')">More Detail</div>
        </v-img>
            <div class="card-content">
                <div> 
                    <v-card-text class="text--primary">
                        <h1>{{session.title}}</h1>
                    </v-card-text>
                    <v-card-subtitle class="pt-0">Passive Selling Online</v-card-subtitle>
                </div>
                    <v-btn class="circle" @click="$emit('chooseWorkshop')"><v-icon>check</v-icon></v-btn>
            </div>
    </v-card>
</template>

<script>
export default {
    props: ['active' , 'session']
}
</script>

<style lang="scss" scoped>
    .circle {
        border-radius: 50%;
        height: 32px !important;
        width: 32px !important;
        min-width: auto !important;
        color: #FFF;
        background: rgba($color: #1723be, $alpha: 0.3) !important; 
        align-self: center;    
    }
    .card-content{
        display: flex;
        justify-content: space-between;
        padding: 15px;
    }
    .more-detail {
        font-size: 12px;
        color: #1723be;
        border-radius: 25px;
        padding: 10px 20px;
        background: white;
        font-weight: bold;
        display: inline;
        position: absolute;
        bottom: 11px;
        right: 11px;
    }
    .v-card__subtitle{
        padding: 0;
    }
    .v-card__text{
        padding: 0;
        padding-bottom: 5px;
        .h1{
            font-size: 24px;
        }
    }
    .v-card+.v-card{
        margin-top: 30px;
    }
    .v-card.active{
        .circle{
             background: rgba($color: #1723be, $alpha: 1) !important; 
        }
        .v-image{
            &::before{
                content: 'Selected';
                font-weight: bold;
                font-size: 24px;
                height: 100%;
                width: 100%;
                display: flex;
                align-items: center;
                justify-content: center;
                background: rgba($color: #1723be, $alpha: 1) !important; 
            }
        }
    }
</style> 