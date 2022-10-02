<template>
    <div class="card m-3 text-center">
        <h5 class="card-header">Tag</h5>
        <div class="card-body">
            <h3 class="card-title">
                {{ cardElement.name }}
            </h3>
            <a href="#" class="btn btn-primary">
                View posts with this tag
            </a>
        </div>
    </div>
</template>

<script>
export default {
    name: 'GenericCard',
    props: {
        'cardElement' : Object,
    }
}
</script>

<style>

</style>