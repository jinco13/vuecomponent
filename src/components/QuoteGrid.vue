<template>
  <div>
    <slot name="title"></slot>
    <slot name="content"></slot>
    <ul>
        <li v-for="quote in quotes">
            {{ quote }}
        </li>
    </ul>
  </div>
</template>

<script>
export default {
    props: ['quotes'],
}
</script>

<style>
</style>
