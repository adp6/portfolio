<template>
    <footer>
        <div class="container row">
            <div>
                <h3>Kucherenko Volodymyr</h3>
                <h4>
                    Front-end developer
                </h4>
            </div>
            <div>
                <div>
                    <h4>
                        Email
                    </h4>
                    <div>
                       <span>
                            mcdegan244@gmail.com
                        </span> 
                    </div>
                    
                </div>
                
            </div>
        </div>
    </footer>
</template>

<style scoped>
    .row{
        display: grid;
        grid-template-columns: auto auto;
    }
    .row div:nth-child(2), .row div:nth-child(2) h4{
        width: 100%;
        text-align: end;
    }
    footer{
        padding-top: 100px;
        padding-bottom: 100px;
        background-color: rgb(29, 27, 27);
        text-align: center;
        font-size: 2em;
        font-weight: 600;
    }
    div{
        text-align: left;
    }
    h3{
        color: rgb(199, 155, 78);
    }
    h4{
        font-size: 0.8em;
        color: rgb(209, 209, 209);
    }
    span{
        font-size: 0.6em;
        color: rgba(255, 255, 255, 0.546);
    }

    @media screen and (max-width:1300px) {
        .row{
            grid-template-columns: auto;
        }
        .row div:nth-child(2) h4{
            text-align: left;
            margin-top: 60px;
        }
        .row div:nth-child(2), .row div:nth-child(2) h4{
            width: 100%;
            text-align: left;
        }
    }
</style>

<script>
export default {
    name:'FooterVue'
}
</script>