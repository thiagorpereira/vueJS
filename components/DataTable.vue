<template>
    <div v-if="posts">
        <v-data-table
        v-model:items-per-page="itemsPerPage"
        :headers="headers"
        :items="data"
        item-value="userId"
        class="elevation-1"
        >
        </v-data-table>
    </div>
</template>

<script>
import {VDataTable} from 'vuetify/components'
import getAllPosts from '../services/getAllPosts.js'

export default {

    component: {
        VDataTable
    },

    setup() {
        const { posts, error, load } = getAllPosts()
        load()
        return {posts, error, load, itemsPerPage: 10, headers: [{
            title: 'User Id',
            align: 'start',
            sortable: false,
            key: 'userId'
        },
        {
            title: 'Title',
            align: 'start',
            sortable: false,
            key: 'title'
        },
        {
            title: 'Body',
            align: 'start',
            sortable: false,
            key: 'body'
        }
        ],
        data: posts
        }
    }
}

</script>