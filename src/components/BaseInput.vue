<template>
    <label>{{ label }}</label>
    <input 
        :placeholder="label" 
        :value="modelValue" 
        @input="$emit('update:modelValue', $event.target.value)" 
        v-bind="$attrs"
    >
    <!--
        Ya se que hace le @input.
        $event.target devuelve un objeto, el objeto es el mismo elemento, se devuelve a si mismo.
        .value, siguiendo la premisa anterior, input tiene una propiedad value, que es el valor que tendrá el elemento,
        Si sabemos que target devuelve el elemento, entonces estamos accediendo al valor dentro del elemento.
        Nota: especulo que modelValue se ocupa en Vue para el v-model
        Por lo tanto, cada vez que se actualiza el campo al ingresar un dato, se emite un evento update que contiene el valor de input.
        Ya lo comprobé, para que funcione el v-model debe llamarse modelValue
     -->

     <!-- 
        v-bind="$attrs" permite que, propiedades del elemento HTML, 
        como el input, y que no fueron declaradas en el defineProps, puedan linkearse al elemento.  
    -->
</template>

<script setup>
defineProps({
    label: {
        // Esto es una especie de declaración para saber que valores admite
        type: String,
        default: ""
    },
    modelValue: {
        type: [String, Number],
        default: ""
    },
    // type: {
    //     type: String,
    //     default: ""
    // }
    // No se usa porque el elemento tiene el v-bind
});
</script>