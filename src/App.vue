<template>
    <v-app>
        <v-content>
            <v-container>
                <progress-card
                    v-for="(bar, i) in bars"
                    :key="i"
                    :title="bar.title"
                    :subtitle="bar.subtitle"
                    :value="bar.value"
                    :label="bar.label"
                    :height="bar.height"
                    :tooltip="bar.tooltip"
                    :color="bar.color"
                />

                <progress-card
                    v-if="bars.length === 0"
                />
            </v-container>
        </v-content>
    </v-app>
</template>

<script>
import ProgressCard from "./components/ProgressCard";

export default {
    name: "App",

    components: {
        ProgressCard,
    },

    data: () => ({
        bars: [],
    }),

    beforeMount() {
        const input = window.location.search.substring(1);
        const decoded = decodeURIComponent(input);
        try {
            this.bars = JSON.parse(decoded);
        } catch(e) { /* do nothing */ }
    }
};
</script>
