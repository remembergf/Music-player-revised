<template>
    <div class="search-list">
        <ul>
            <li class="search-item" v-for="item in searches" @click="selectItem(item)">
                <span class="text" >{{ item }}</span>
                <span class="icon" @click.stop="deleteItem(item)">
                    <i class="icon-delete"></i>
                </span>
            </li>
        </ul>
    </div>
</template>


<script>
    export default {
        props: {
            searches: {
                type: Array,
                default: []
            }
        },
        methods: {
            selectItem(item) {
                this.$emit('select', item)
            },
            deleteItem(item) {
                this.$emit('delete', item)
            }
        }
    }
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
    @import './../../common/stylus/variable.styl'

    .search-item
        display: flex
        align-items: center
        padding: 0px 20px
        margin: 0px
        height: 40px
        overflow: hidden
    .text
        flex: 1
        color: $color-text-l
    .icon
        extend-click()
    .icon-delete
        font-size: $font-size-small
        color: $color-text-d
</style>