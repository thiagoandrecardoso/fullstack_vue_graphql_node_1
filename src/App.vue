<template>
    <div>
        <div id="slogan" class="text-center">
            <h1>TopsTonNameGator</h1>
            <br/>
            <h6 class="text-secondary">Gerador de nomes, utilizando Vue,js, GraphQL e Node</h6>
        </div>
        <div id="smain">
            <div class="container">
                <div class="row">
                    <div class="col-md">
                        <h5>Prefixo <span class="badge badge-info">{{prefixes.length}}</span></h5>
                        <div class="card">
                            <div class="card-body">
                                <ul class="list-group">
                                    <li class="list-group-item" v-for="prefix in prefixes" v-bind:key="prefix">
                                        {{prefix}}
                                    </li>
                                </ul>
                                <br/>
                                <div class="input-group">
                                    <input class="form-control" type="text" v-model="prefix" placeholder="Digite o prefixo"/>
                                    <div class="input-group-append">
                                        <button class="btn btn-info" v-on:click="addPrefix(prefix)"><span class="fa fa-plus"></span></button>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="col-md">
                        <h5>Sufixo <span class="badge badge-info">{{sufixes.length}}</span></h5>
                        <div class="card">
                            <div class="card-body">
                                <ul class="list-group">
                                    <li class="list-group-item" v-for="sufix in sufixes" v-bind:key="sufix">
                                        {{sufix}}
                                    </li>
                                </ul>
                                <br/>
                                <div class="input-group">
                                    <input class="form-control" type="text" v-model="sufix" placeholder="Digite o sufixo"/>
                                    <div class="input-group-append">
                                        <button class="btn btn-info" v-on:click="addSufix(sufix)"> <span class="fa fa-plus"></span></button>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <br/>
                <h5>Dominios <span class="badge badge-info">{{domains.length}}</span></h5>
                <div class="card">
                    <div class="card-body">
                        <li class="list-group-item" v-for="domain in domains" v-bind:key="domain.name">
                            {{ domain }}
                        </li>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import "bootstrap/dist/css/bootstrap.css"
    import "font-awesome/css/font-awesome.css"

    export default {
        name: 'app',
        data: function () {
            return {
                prefix: "",
                sufix: "",
                prefixes: ['Coisa', 'Lira'],
                sufixes: ['nte', 'ntson'],
                domains: ['Lirante', 'Coisantson', 'Lirantson']
            };
        },
        methods: {
            addPrefix(prefix){
                this.prefixes.push(prefix);
                this.prefix = "";
            },
            addSufix(sufix){
                this.sufixes.push(sufix);
                this.sufix = ""
            }
        }
    }
</script>

<style>
    #slogan {
        margin-top: 30px;
        margin-bottom: 30px;
    }

    #smain {
        background-color: #F1F1F1;
        padding-top: 30px;
        peeding-bottam: 20px;
    }
</style>
