<template>
    <v-card>
        <v-list-item two-line>
            <v-list-item-content>
                <v-list-item-title class="headline mb-1">Project Name</v-list-item-title>
                <v-list-item-subtitle>Lorem ipsum dolor sit amet</v-list-item-subtitle>
            </v-list-item-content>
        </v-list-item>
        <div class="bar">
            <v-progress-linear rounded :height="8" :value="25">wow</v-progress-linear>
        </div>
    </v-card>
</template>

<script>
export default {

}
</script>

<style scoped>
.bar {
    padding: 0 16px 16px 16px;
}
</style>