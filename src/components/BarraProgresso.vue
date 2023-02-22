<template>
    <div class="cell-12 progress-bar">
        <div class="progress" role="progressbar" aria-label="Basic example" 
            aria-valuenow="0" aria-valuemin="0" aria-valuemax="100" style="height: '20px'">
                <div class="progress-bar" :style="{width: progressWidth + '%'}">
                    {{progressWidth}}%
                </div>
        </div>
    </div>
</template>
<script>
export default {
    props: ['progressWidth']
}
</script>
<style>
    
</style>