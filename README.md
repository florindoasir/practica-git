<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css"
        integrity="sha384-JcKb8q3iqJ61gNV9KGb8thSsNjpSL0n8PARn9HuZOnIxN0hoP+VmmDGMN5t9UJ0Z" crossorigin="anonymous">

    <title>Examen Segunda evaluación</title>
</head>

<body>
    <div id="app" class="container">
        <div v-for="series in jsonObject">
            <h2>{{series.show.name}}<br><li></li>{{series.show.genres}}<br>{{series.show.language}}</h2>
            <h3>{{series.show.previousepisode}}</h3>
            <p v-if="series.score>=13"><small style="color: rgb(0, 255, 149)">{{series.score}}</small></p>
            <p v-else><small style="color: rgb(255, 0, 55)">{{series.score}}</small></p>
            
            
        </div>    
        <div v-for="series in jsonObject">
            <ol>{{series.show.genres}}</ol>
            <img src="series.show.image.medium}}">
        </div>
                    
    </div>
    
</body>


<script>

    const App = new Vue({
        el: '#app',
        data: {
            jsonObject: {}
        },
        methods: {
            init() {
                fetch("http://api.tvmaze.com/search/shows?q=sports")
                    .then(response => response.json())
                    .then(data => (this.jsonObject = data));
            }
        },
        mounted() {
            this.init()
        }
    })
</script>

</html>