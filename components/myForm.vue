<template>
        <form method="post" class="new-comment">
            <slot></slot>
            <textarea name="comment-content" placeholder="写下你的评论"></textarea>
            <div class="write-function-block">
                <div class="emoji-modal-wrap">
                    <a href="#" class="emoji">
                        <i class="fa fa-smile-o"></i>
                    </a>
                    <div class="emoji-modal"></div>
                </div>
                <div class="hint">Ctrl+Enter发送</div>
                <a href="#" class="btn-send">发送</a>
                <a href="#" class="btn-cancle">取消</a>
            </div>
        </form>
</template>
<script>
export default {
  name:'myForm',
}
</script>
