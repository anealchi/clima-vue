<script setup>
    import useClima from '../composables/useClima';
    
    const { formatearTemp } = useClima()

    defineProps({
        clima: {
            type: Object,
            required: true
        }
    })
</script>

<template>
    <div class="resultado">
        <h2>Clima de: {{ clima.name }}</h2>
        <p class="actual">{{ formatearTemp(clima.main.temp) }} &deg;C</p>
        <div class="temperaturas">
            <p>Min: <span>{{ formatearTemp(clima.main.temp_min) }} &deg;C</span></p>
            <p>Max: <span>{{ formatearTemp(clima.main.temp_max) }} &deg;C</span></p>
        </div>
    </div>
</template>