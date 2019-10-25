<template>
    <table v-if="messages.length > 0" class="table table-inbox table-hover">
        <tbody>
            <tr>
                <td><input type="checkbox"></td>
                <td></td>
                <td>[MESSAGE NAME]</td>
                <td>[SUBJECT]</td>
                <td></td>
                <td class="text-right">[MESSAGE DATE]</td>
            </tr>
        </tbody>
    </table>

    <p v-else>No messages here yet.</p>
</template>
<script>
export default {
    
}
</script>