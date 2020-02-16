<template>
    <v-card>
        <v-list-item two-line>
            <v-list-item-content>
                <v-list-item-title class="headline mb-1">
                    {{ title }}
                </v-list-item-title>
                <v-list-item-subtitle>{{ subtitle }}</v-list-item-subtitle>
            </v-list-item-content>
        </v-list-item>
        <div class="bar">
            <v-progress-linear rounded :height="height" :value="value">{{
                label
            }}</v-progress-linear>
        </div>
    </v-card>
</template>

<script>
export default {
    props: {
        value: {
            default: 50,
            type: Number,
        },
        title: {
            default: "Example Project",
            type: String,
        },
        subtitle: {
            default: `This is an example progress bar that doesnt really mean anything. But hey, it's something ¯\\_(ツ)_/¯`,
            type: String,
        },
        label: {
            default: "",
            type: String,
        },
        height: {
            default: 10,
            type: Number,
        },
    },
};
</script>

<style scoped>
.bar {
    padding: 0 16px 16px 16px;
}
</style>
