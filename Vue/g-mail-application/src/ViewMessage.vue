<template>
     <div class="inbox-body">
        <div class="mail-option">
            <button class="btn btn-primary">
                <i class="fa fa-arrow-left" aria-hidden="true"></i>&nbsp; Back
            </button>

            <button class="btn btn-danger">
                <i class="fa fa-trash-o"></i>&nbsp; {{ data.message.isDeleted ? 'Deleted' : 'Delete' }}
            </button>

            <template>
                <button class="btn btn-primary">
                    <i class="fa fa-envelope-open" aria-hidden="true"></i>&nbsp; Mark as unread
                </button>

                <button class="btn btn-primary">
                    <i class="fa fa-envelope" aria-hidden="true"></i>&nbsp; Mark as read
                </button>
            </template>
        </div>

        <p><strong>Date:</strong></p>
        <p><strong>From:</strong> [NAME] AND [EMAIL]</p>
        <hr>

        <div class="message"></div>

        <div class="attachments">
            <h4>Attachments</h4>

            <ul>
                <li >
                </li>
            </ul>
        </div>
    </div>
</template>
<script>
export default {
    
}
</script>