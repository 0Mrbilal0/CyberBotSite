<template>
   <table>
    <thead>
        <tr>
            <th>
                Commandes
            </th>
            <th>
                Descriptions
            </th>
        </tr>
    </thead>
    <tbody>
        <tr v-for= "(colonne, columns) in colonnes" :key="columns" >
            <td>
                {{ colonne.names }}
            </td>
            <td>
                {{ colonne.descriptions }}
            </td>
        </tr>
    </tbody>
    </table>
</template>

<script>
const sequelize = require('../models/index')

export default {
    
    data() {
        return{
            colonnes: [
                
            ],
        }
    },
    head: {
        titleTemplate: '%s - Commandes'
    },
    mounted() {
        
        console.log(this.colonnes);
    }
}
</script>

<style>
table {
    margin: auto;
    align-items: center;
}

td,th {
    border: 1px solid rgb(190, 190, 190);
    padding: 10px 100px 10px 100px;
}

td {
    text-align: center;
}

tr:nth-child(even) {
    background-color: #eee;
}

th[scope="col"] {
    background-color: #696969;
    color: #fff;
}

th[scope="row"] {
    background-color: #d7d9f2;
}

caption {
    padding: 10px;
    caption-side: bottom;
}

table {
    border-collapse: collapse;
    border: 2px solid rgb(200, 200, 200);
    letter-spacing: 1px;
    font-family: sans-serif;
    font-size: .8rem;
}
</style>