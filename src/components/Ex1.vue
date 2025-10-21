<script>
    export default { 
        // Add Code Here to complete the task
        // Note: DO NOT USE "eval()". In security, "eval" is considered "evil"!!!
            data() {
        return {
            x: 0,
            y: 0,
            operators: ['+', '-', '*', '/'],
            selectedOp: '+'
        }
    },
    computed: {
        result() {
            const a = Number(this.x)
            const b = Number(this.y)
            switch (this.selectedOp) {
                case '+': return a + b
                case '-': return a - b
                case '*': return a * b
                case '/': return b === 0 ? '∞' : a / b
                default: return NaN
            }
        }
    }
    }
</script>

<template>
    <p>x <input v-model.number="x"></p>
    <select v-model="selectedOp">
        <option v-for="op in operators" >{{ op }}</option>
    </select>
    <p>y <input v-model.number="y"></p>
    
    <p>---------------------</p>

    <p>= {{result}}</p>
</template>

<style scoped>
    p, input { font-family: monospace; }
    p { white-space: pre; }

</style>
