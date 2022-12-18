<template>
   <table>
    <thead>
        <tr>
            <th v-for="(capitalize, columns) in capitalizes" :key="columns">
                {{ capitalize }}
            </th>
        </tr>
    </thead>
    <tbody>
        <tr v-for="(entry, row) in entrys" :key="row">
            <td v-for="(colonne, columns) in colonnes" :key="columns" >
                {{ entry[colonne] }}
            </td>
        </tr>
    </tbody>
    </table>
</template>

<script>
export default {
    data() {
        return{
            capitalizes: [
                'Commandes',
                'Descriptions',
                // 'Roles'
            ],
            entrys: 0,
            colonnes: [
                {names: 'un name', descriptions: 'une description'},
                {names: 'deux name', descriptions: 'deux descrtipions'},
                {names: 'trois name', descriptions: 'trois descriptions'},
                {names: 'quatre name', descriptions: 'quatre descriptions'},
            ],
        }
    },
    head: {
        titleTemplate: '%s - Commandes'
    },
    mounted() {
        console.log(colonnes[entrys]['names']);
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