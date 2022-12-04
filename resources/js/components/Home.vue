<template>
    <div>
        <componentB></componentB>
        <div style="display:flex;justify-content: end;">
            <button style="width:150px;height:40px;margin: 10px;">Cancel</button>
            <button style="width:150px;height:40px; border: 1px solid black;margin: 10px; background-color: white;">Save as Draft</button>
            <button style="color:white;width:150px;height:40px;margin: 10px;background-color: #04bcbc;">Submit</button>
        </div>
    </div>
</template>

<script>
import componentB from "./ComponentB.vue"
    export default {
        components : {
            componentB : componentB
        }
    }
</script>
