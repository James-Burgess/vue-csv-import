<template>
    <div id="app">
        <div class="container">
            <div class="row mt-5 text-center">
                <div class="col-6 offset-3">
                  <h1>vue-csv-loader demo</h1>
                    <a href="assets/csv-sample.csv" target="_blank">Download Example CSV</a>
                </div>
            </div>
            <section class="py-5">
                <div class="row mt-5">
                    <div class="col-8 offset-2">
                        <vue-csv-import
                            v-slot="{file}"
                            v-model="csv"
                            :fields="fields"
                        >
                            <vue-csv-errors/>
                            <br>
                            <vue-csv-input/>
                            <br>
                            <vue-csv-toggle-headers/>
                            <br>
                            <vue-csv-table-map :auto-match="true"></vue-csv-table-map>
                            <!-- <vue-csv-map :auto-match="true"></vue-csv-map> -->
                            <br>
                            <vue-csv-submit v-if="csv" url="/"></vue-csv-submit>
                        </vue-csv-import>
                        <pre class="mt-15" v-if="csv"><code>{{ csv }}</code></pre>
                    </div>
                </div>
            </section>
        </div>
    </div>
</template>

<script>
    export default {
        name: "App",
        data() {
            return {
                csv: null,
                fields: {name: {required: false, label: 'Name'}, age: {required: true, label: 'Age'}}
            };
        }
    };
</script>

<style>
#app {
    font-family: "Avenir", Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}

.container {
    text-align: left;
}

code {
    background-color: #eee;
    border: 1px solid #999;
    display: block;
    padding: 20px;
}

#app .form {
    text-align: left;
}

</style>
