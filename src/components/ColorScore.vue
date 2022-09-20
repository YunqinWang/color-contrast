<script>
    import * as a from "wcag-contrast";

    export default {
        data: function () {
            return {
            text: '#000',
            color: '#fff',
            comment:"",
         }},
        props: {
            scoreTextColor:{
                type: String,
            },
            scoreBackColor:{
                type: String,
            }
        },
        methods:{
            updateComment(){
                console.log( document.getElementById("color-comment"))
                if(this.score == "Fail"){
                    this.comment = "Bad Match :(";
                }
                else{
                    this.comment = "Great Match!";
                }
            },
            calRatio(){
                this.text= this.scoreTextColor;
                this.color = this.scoreBackColor;
                return a.hex(this.text, this.color);
            },
            calScore(){
                this.score = a.score(a.hex(this.text, this.color));
                this.updateComment();
                return this.score;
            },
        }
    }
</script>

<template>
    <div align = "center">
        <p><b>Contrast Ratio: </b>{{calRatio()}}</p>
        <p><b>Contrast Grade: </b>{{calScore()}}</p>
        <p id="color-comment"> {{comment}}</p>
    </div>
</template>

<style>
    #color-comment{
        font-weight: 900;
        font-size: 24px;
    }
    b{
        font-weight: 500;
    }
</style>
