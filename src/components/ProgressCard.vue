<template>
    <v-card class="card">
        <v-list-item two-line>
            <v-list-item-content>
                <v-list-item-title class="headline mb-1">
                    {{ title }}
                </v-list-item-title>
                <v-list-item-subtitle>{{ subtitle }}</v-list-item-subtitle>
            </v-list-item-content>
        </v-list-item>
        <div class="bar">
            <v-tooltip bottom v-if="tooltip">
                <template v-slot:activator="{ on }">
                    <v-progress-linear
                        v-on="on"
                        rounded
                        :height="height"
                        :value="value"
                        :color="color"
                        :indeterminate="indeterminate"
                    >
                        <span class="caption" v-text="label" />
                    </v-progress-linear>
                </template>
                <span>{{ tooltip }}</span>
            </v-tooltip>

            <v-progress-linear
                v-if="!tooltip"
                rounded
                :height="height"
                :value="value"
                :color="color"
                :indeterminate="indeterminate"
            >
                <span class="caption" v-text="label" />
            </v-progress-linear>
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
        tooltip: {
            default: "",
            type: String,
        },
        color: {
            default: "blue",
            type: String,
        },
        indeterminate: {
            default: false,
            type: Boolean,
        },
    },
};
</script>

<style scoped>
.bar {
    padding: 0 16px 16px 16px;
}

.card {
    margin-bottom: 16px;
}
</style>

<style>
.v-progress-linear__background {
    width: 100% !important;
    left: 0 !important;
}
</style>