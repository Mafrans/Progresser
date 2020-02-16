<template>
    <v-app>
        <progress-card v-for="(bar, i) in bars" :key="i" :title="bar.title" :subtitle="bar.subtitle" :value="bar.value"/>
    </v-app>
</template>

<script>
import ProgressCard from './components/ProgressCard'

export default {
    name: 'App',

    components: {
        ProgressCard
    },

    data: () => ({
        bars: [
            {
                title: 'Custom Project',
                subtitle: `Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam`,
                value: 30,
            }
        ]
    }),
};
</script>
